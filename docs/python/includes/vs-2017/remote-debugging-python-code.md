---
title: リモート Linux コンピューターでの Python コードのデバッグ
description: 必要な構成手順、セキュリティ、トラブルシューティングなど、Visual Studio を使ってリモート Linux コンピューターで動作する Python コードをデバッグします。
ms.date: 12/06/2018
ms.topic: how-to
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: a58af8098a49992e81380c6567755c31709d1dc3
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99916615"
---
Visual Studio は、Windows コンピューター上でローカルまたはリモートで Python アプリケーションを起動およびデバッグすることができます (「[Remote Debugging](../../../debugger/remote-debugging.md)」 (リモート デバッグ) をご覧ください)。 また、別のオペレーティング システム、デバイス、または CPython 以外の Python 実装を [ptvsd ライブラリ](https://pypi.python.org/pypi/ptvsd)を使用してリモートでデバッグすることもできます。

ptvsd を使用する場合、デバッグ対象の Python コードは Visual Studio がアタッチできるデバッグ サーバーをホストします。 このホストには、コードに小さな変更を加えてサーバーをインポートして有効にする必要があります。また、TCP 接続を許可するようにリモート コンピューター上でネットワークまたはファイアウォールを構成する必要が生じる場合があります。

![ビデオのムービー カメラ アイコン](../../../install/media/video-icon.png "ビデオを見る") リモート デバッグの概要については、「[Deep Dive: Cross-platform remote debugging](https://youtu.be/y1Qq7BrV6Cc)」(Deep Dive: クロスプラットフォーム リモート デバッグ) (youtube.com、6 分 22 秒) をご覧ください。Visual Studio 2015 および 2017 の両方に適用できる内容です。

## <a name="set-up-a-linux-computer"></a>Linux コンピューターを設定する

このチュートリアルを実行するには、次の項目が必要です。

- Mac OSX や Linux などのオペレーティング システムで Python を実行しているリモート コンピューター。
- そのコンピューターのファイアウォールで開いているポート 5678 (受信)。これはリモート デバッグの既定値です。

[Azure に Linux 仮想マシン](/azure/virtual-machines/linux/creation-choices)を簡単に作成し、Windows から[リモート デスクトップを使用してアクセス](/azure/virtual-machines/linux/use-remote-desktop)することができます。 VM に Ubuntu を使用すると、既定で Python がインストールされるので便利です。Ubuntu を使用しない場合、Python をダウンロードできるその他の場所については、「[Python インタープリターのインストール](../../installing-python-interpreters.md)」の一覧を参照してください。

Azure VM のファイアウォール ルールの作成の詳細については、「[Azure Portal を使用して仮想マシンへのポートを開く方法](/azure/virtual-machines/windows/nsg-quickstart-portal)」を参照してください。

## <a name="prepare-the-script-for-debugging"></a>デバッグのためにスクリプトを準備する

1. リモート コンピューターで、次のコードを使用して *guessing-game.py* という Python ファイルを作成します。

    ```python
    import random

    guesses_made = 0
    name = input('Hello! What is your name?\n')
    number = random.randint(1, 20)
    print('Well, {0}, I am thinking of a number between 1 and 20.'.format(name))

    while guesses_made < 6:
        guess = int(input('Take a guess: '))
        guesses_made += 1
        if guess < number:
            print('Your guess is too low.')
        if guess > number:
            print('Your guess is too high.')
        if guess == number:
            break
    if guess == number:
        print('Good job, {0}! You guessed my number in {1} guesses!'.format(name, guesses_made))
    else:
        print('Nope. The number I was thinking of was {0}'.format(number))
    ```

1. `pip3 install ptvsd` を使用して環境に `ptvsd` パッケージをインストールします。
   >[!NOTE]
   >トラブルシューティングが必要な場合に備えて、インストールされている ptvsd のバージョンを記録しておくことをお勧めします。[ptvsd 一覧](https://pypi.python.org/pypi/ptvsd)にも使用できるバージョンが記載されています。

1. 下のコードを他のコードよりも前の、*guessing-game.py* のできるだけ早い段階で追加して、リモート デバッグを有効にします。 (厳密な要件ではありませんが、`enable_attach` 関数を呼び出す前に起動されたバックグラウンド スレッドをデバッグすることはできません。)

   ```python
   import ptvsd
   ptvsd.enable_attach()
   ```

1. ファイルを保存して `python3 guessing-game.py` を実行します。 `enable_attach` を呼び出すとバックグラウンドで実行され、受信接続を待機します。それ以外の場合はプログラムと対話しています。 必要な場合は、`wait_for_attach` 関数を `enable_attach` の後に呼び出して、デバッガーがアタッチされるまでプログラムをブロックすることもできます。

> [!Tip]
> `enable_attach` と `wait_for_attach` に加えて、ptvsdにはヘルパー関数 `break_into_debugger` も用意されています。この関数は、デバッガーがアタッチされている場合にプログラムのブレークポイントとして機能します。 また、デバッガーがアタッチされている場合に `True` を返す `is_attached` 関数もあります (他の `ptvsd` 関数を呼び出す前にこの結果を確認する必要はありません)。

## <a name="attach-remotely-from-python-tools"></a>Python Tools からリモートでアタッチする

以下の手順では、リモート プロセスを停止する単純なブレークポイントを設定します。

1. ローカル コンピューターでリモート ファイルのコピーを作成し、Visual Studio で開きます。 ファイルの場所は任意ですが、名前はリモート コンピューターのスクリプト名と一致している必要があります。

1. (省略可能) ローカル コンピューター上の ptvsd 用に IntelliSense を使用するには、ptvsd パッケージを Python 環境にインストールします。

1. **[デバッグ]**  >  **[プロセスにアタッチ]** の順に選択します。

1. 表示される **[プロセスにアタッチ]** ダイアログで、 **[接続の種類]** を **[Python remote (ptvsd)]** (Python リモート (ptvsd)) に設定します (旧バージョンの Visual Studio では、これらのコマンドは **[トランスポート]** と **[Python リモート デバッグ]** という名称でした)。

1. **[接続先]** フィールド (旧バージョンでは **[修飾子]** ) に「`tcp://<ip_address>:5678`」と入力します。ここで、`<ip_address>` は、(明示的なアドレスまたは myvm.cloudapp.net のような名前を指定できる) リモート コンピューターの IP アドレスで、`:5678` はリモート デバッグ ポート番号です。

1. **Enter** キーを押すと、そのコンピューターで使用できる ptvsd プロセスの一覧が生成されます。

    ![接続のターゲットの入力とプロセスの一覧表示](../../media/remote-debugging-qualifier.png)

    この一覧の生成後にリモート コンピューターで別のプログラムを起動する場合は、 **[更新]** ボタンを選択します。

1. プロセスを選択してデバッグし、 **[アタッチ]** を選択するか、プロセスをダブルクリックします。

1. Visual Studio はデバッグ モードに切り替わり、スクリプトは引き続きリモート コンピューターで実行され、通常の[デバッグ](../../debugging-python-in-visual-studio.md)機能もすべて使用できます。 たとえば、`if guess < number:` 行のブレークポイントを設定し、リモート コンピューターに切り替え、別の推測を入力します。 その後、ローカル コンピューターの Visual Studio はそのブレークポイントで停止し、ローカル変数などが表示されます。

    ![Visual Studio でブレーク ポイントにヒットしたときにデバッグを一時停止する](../../media/remote-debugging-breakpoint-hit.png)

1. デバッグを停止すると、Visual Studio はプログラムからデタッチされますが、リモート コンピューターでは実行が継続されます。 また、ptvsd もデバッガーのアタッチを引き続きリッスンするので、いつでもプロセスに再アタッチできます。

### <a name="connection-troubleshooting"></a>接続のトラブルシューティング

1. **[接続の種類]** で **[Python remote (ptvsd)]** (Python リモート (ptvsd)) (旧バージョンでは **[トランスポート]** の **[Python remote debugging]** (Python リモート デバッグ)) を選択していることを確認します。
1. **[Connection Target]** (接続のターゲット) (または **[修飾子]** ) のシークレットがリモート コードのシークレットと完全に一致することを確認します。
1. **[接続先]** (または **[修飾子]** ) の IP アドレスがリモート コンピューターと一致することを確認します。
1. リモート コンピューターのリモート デバッグ ポートを開いていること、接続先に `:5678` などのポート サフィックスを含めていることを確認します。
    - 別のポートを使用する必要がある場合は、`enable_attach` の呼び出しで `ptvsd.enable_attach(address = ('0.0.0.0', 8080))` のように `address` 引数を使用して指定できます。 この場合、ファイアウォールでもそのポートを開きます。
1. `pip3 list` から返されたリモート コンピューターにインストールされている ptvsd のバージョンが、Visual Studio で使用している Python ツールのバージョンで使用されている ptvsd のバージョン (以下の表を参照してください) が一致することを確認します。 必要に応じて、リモート コンピューターの ptvsd を更新します。

    | Visual Studio のバージョン | Python ツール/ptvsd のバージョン |
    | --- | --- |
    | 2017 15.8 | 4.1.1a9 (レガシ デバッガー:3.2.1.0) |
    | 2017 15.7 | 4.1.1a1 (レガシ デバッガー:3.2.1.0) |
    | 2017 15.4、15.5、15.6 | 3.2.1.0 |
    | 2017 15.3 | 3.2.0 |
    | 2017 15.2 | 3.1.0 |
    | 2017 15.0, 15.1 | 3.0.0 |
    | 2015 | 2.2.6 |
    | 2013 | 2.2.2 |
    | 2012, 2010 | 2.1 |

## <a name="using-ptvsd-3x"></a>ptvsd 3.x を使用する

以下は、ptvsd 4.x では削除された特定の機能を含む、ptvsd 3.x を使用したリモート デバッグに限定した情報です。

1. ptvsd 3.x では、`enable_attach` 関数で、実行中のスクリプトへのアクセスを制限する "シークレット" を最初の引数として渡す必要がありました。 このシークレットは、リモート デバッガーをアタッチするときに入力します。 推奨はされませんが、`enable_attach(secret=None)` を使用するとすべてのユーザーに接続を許可することができます。

1. 接続のターゲット URL は `tcp://<secret>@<ip_address>:5678` です (ここで、`<secret>` は渡した文字列で、`enable_attach` は Python コードです)。

ptvsd 3.x のリモート デバッグ サーバーへの接続は、既定で、シークレットのみで保護されており、すべてのデータはプレーンテキストで渡されます。 ptvsd 3.x では、より高いセキュリティでの接続に `tcsp` を使用した SSL をサポートしています。設定手順は次のとおりです。

1. リモート コンピューターで、openssl を使用して別の自己署名証明書とキー ファイルを生成します。

    ```command
    openssl req -new -x509 -days 365 -nodes -out cert.cer -keyout cert.key
    ```

    openssl のプロンプトが表示されたら、 **[共通名]** のホスト名または IP アドレス (接続できればどちらでも可) を入力します

    (詳細については、Python `ssl` モジュール ドキュメントの「[Self-signed certificates](https://docs.python.org/3/library/ssl.html#self-signed-certificates)」(自己署名証明書) を参照してください。 これらのドキュメントのコマンドは、1 つの結合されたファイルのみを生成する点に注意してください)。

1. このコードで、`enable_attach` の呼び出しを修正し、値としてファイル名を使用して `certfile` 引数と `keyfile` 引数を含めます (これらの引数の意味は、標準の `ssl.wrap_socket` Python 関数の引数と同じです)。

    ```python
    ptvsd.enable_attach(secret='my_secret', certfile='cert.cer', keyfile='cert.key')
    ```

    また、ローカル コンピューターのコード ファイルでも同じ変更を加えることもできます。ただし、このコードは実際には実行されないので、厳密には必要ありません。

1. リモート コンピューターで Python プログラムを再起動し、デバッグできる状態にします。

1. Visual Studio がインストールされた Windows コンピューターの [信頼されたルート CA] にその証明書を追加して、チャネルをセキュリティで保護します。

    1. リモート コンピューターの証明書ファイルをローカル コンピューターにコピーします。
    1. **[コントロール パネル]** を開き、 **[管理ツール]**  >  **[コンピューター証明書の管理]** の順に移動します。
    1. 表示されるウィンドウで、左側の **[信頼されたルート証明機関]** を展開し、 **[証明書]** を右クリックして **[すべてのタスク]**  >  **[インポート]** の順に選択します。
    1. リモート コンピューターからコピーした *.cer* ファイルに移動して選択し、ダイアログの指示に従ってクリックしてインポートを完了します。

1. 前述の手順で Visual Studio のアタッチ プロセスを繰り返します。今回は、 **[Connection Target]** (接続のターゲット) (または **[修飾子]** ) として `tcps://` を使用します。

    ![SSL を使用するリモート デバッグ トランスポートの選択](../../media/remote-debugging-qualifier-ssl.png)

1. 後述のとおり、Visual Studio で SSL 接続を実行する場合、証明書で問題が発生する可能性があると表示されます。 この警告を無視して続行しても問題ありません。無視しても、man-in-the-middle 攻撃を受ける可能性がある傍受を防ぐために、チャネルは暗号化されます。

    1. 以下の "**リモート証明書は信頼されていません**" という警告が表示される場合、[信頼されたルート CA] に証明書が適切に追加されていないことを意味します。 追加手順を確認して、もう一度試してください。

        ![SSL 証明書の信頼の警告](../../media/remote-debugging-ssl-warning.png)

    1. 以下の "**リモート証明書名がホスト名と一致しません**" という警告が表示される場合、証明書の作成時に **[共通名]** として正しいホスト名や IP アドレスを指定していないことを意味します。

        ![SSL 証明書のホスト名の警告](../../media/remote-debugging-ssl-warning2.png)
