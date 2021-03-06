---
title: マネージコード用のカスタムコード分析チェックインポリシー
ms.date: 11/04/2016
description: カスタマイズされたコード分析チェックインポリシーを作成する方法について説明します。 「Visual Studio マネージコードが Azure DevOps プロジェクトポリシーに準拠していることを確認する方法」を参照してください。
ms.custom: SEO-VS-2020
ms.topic: how-to
f1_keywords:
- vs.code.analysis.selecttfsrulesets
- vs.code.analysis.browsefortfsruleset
- vs.code.analysis.policyeditor
ms.assetid: fd029003-5671-4b24-8b6f-032e0a98b2e8
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- dotnet
ms.openlocfilehash: 8e682c3d3312be5c4f4639fc2642a398e321fc78
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99859880"
---
# <a name="implement-custom-code-analysis-check-in-policies-for-managed-code"></a>マネージド コード用のカスタム コード分析チェックイン ポリシーを実装する

コード分析のチェックインポリシーでは、Azure DevOps プロジェクトのメンバーがバージョン管理にチェックインする前にソースコードで実行する必要がある一連の規則を指定します。 Microsoft では、コード分析ルールを機能領域にグループ化する一連の標準 *規則セット* を提供しています。 *カスタムチェックインポリシー規則セット* は、プロジェクトに固有のコード分析規則のセットを指定します。 規則セットは、ルールセットファイルに格納されます。

チェックインポリシーは、Azure DevOps プロジェクトレベルで設定され、バージョン管理ツリーのルールセットファイルの場所によって指定されます。 チームポリシーのカスタム規則セットのバージョン管理の場所に制限はありません。

コード分析は、各プロジェクトの [プロパティ] ウィンドウの個々のコードプロジェクトに対して構成されます。 コードプロジェクトのカスタム規則セットは、ローカルコンピューター上のルールセットファイルの物理的な場所によって指定されます。 コードプロジェクトと同じドライブにあるルールセットファイルが指定されている場合、Visual Studio はプロジェクト構成内のファイルへの相対パスを使用します。

Azure DevOps プロジェクトのカスタム規則セットを作成する場合は、コードプロジェクトの一部ではない特殊なフォルダーにチェックインポリシーのルールセットファイルを格納することをお勧めします。 専用のフォルダーにファイルを保存する場合は、規則ファイルを編集できるユーザーを制限するアクセス許可を適用できます。また、プロジェクトを含むディレクトリ構造を別のディレクトリまたはコンピューターに簡単に移動できます。

## <a name="create-the-project-custom-check-in-rule-set"></a>プロジェクトのカスタムチェックイン規則セットを作成する

Azure DevOps プロジェクトのカスタム規則セットを作成するには、まず **ソース管理エクスプローラー** でチェックインポリシー規則セット用の特別なフォルダーを作成します。 次に、規則セットファイルを作成し、ファイルをバージョン管理に追加します。 最後に、プロジェクトのコード分析チェックインポリシーとして規則セットを指定します。

> [!NOTE]
> Azure DevOps プロジェクトでフォルダーを作成するには、まず、プロジェクトのルートをローカルコンピューター上の場所にマップする必要があります。

### <a name="to-create-the-version-control-folder-for-the-check-in-policy-rule-set"></a>チェックインポリシー規則セットのバージョン管理フォルダーを作成するには

1. チームエクスプローラーで、プロジェクトノードを展開し、[ **ソース管理**] をクリックします。

2. [ **フォルダー** ] ウィンドウで、プロジェクトを右クリックし、[ **新しいフォルダー**] をクリックします。

3. メインソース管理ペインで、[ **新しいフォルダー**] を右クリックし、[ **名前の変更**] をクリックして、規則セットフォルダーの名前を入力します。

### <a name="to-create-the-check-in-policy-rule-set"></a>チェックインポリシー規則セットを作成するには

1. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[ファイル]** をクリックします。

2. [ **カテゴリ** ] ボックスの一覧の [ **全般**] をクリックします。

3. [ **テンプレート** ] ボックスの一覧で、[ **コード分析規則セット**] をダブルクリックします。

4. 規則セットに含める[規則を指定](../code-quality/how-to-create-a-custom-rule-set.md)してから、作成した規則セットフォルダーに規則セットファイルを保存します。

### <a name="to-add-the-rule-set-file-to-version-control"></a>ルールセットファイルをバージョンコントロールに追加するには

1. **ソース管理エクスプローラー** で、新しいフォルダーを右クリックし、[**フォルダーへの項目の追加**] をクリックします。

     詳細については、「 [Git と Azure Repos](/azure/devops/repos/git/overview?view=vsts&preserve-view=true)」を参照してください。

2. 作成したルールセットファイルをクリックし、[ **完了**] をクリックします。

     ファイルがソース管理に追加され、チェックアウトされます。

3. [ **ソース管理エクスプローラー** の詳細] ウィンドウで、ファイル名を右クリックし、[ **保留中の変更をチェックイン**] をクリックします。

4. [ **チェックイン** ] ダイアログボックスで、コメントを追加するオプションが表示されたら、[ **チェックイン**] をクリックします。

    > [!NOTE]
    > Azure DevOps プロジェクトに対してコード分析チェックインポリシーを既に構成していて、[ **チェックインを現在のソリューションに含まれるファイルのみを含める] を** 選択している場合は、ポリシーエラーの警告をトリガーします。 [ポリシーの失敗] ダイアログボックスで、[ **ポリシーエラーの上書き**] を選択して、チェックインを続行します。 必要なコメントを追加し、[ **OK]** をクリックします。

### <a name="to-specify-the-rule-set-file-as-the-check-in-policy"></a>規則セットファイルをチェックインポリシーとして指定するには

1. [ **チーム** ] メニューの [ **プロジェクトの設定**] をポイントし、[ **ソース管理**] をクリックします。

2. [ **チェックインポリシー**] をクリックし、[ **追加**] をクリックします。

3. [ **チェックインポリシー** ] の一覧で [ **コード分析**] をダブルクリックし、[ **マネージコードのコード分析を強制** する] チェックボックスがオンになっていることを確認します。

4. [ **この規則セットを実行** する] の一覧で、をクリックし **\<Select Rule Set from Source Control>** ます。

5. バージョン管理のチェックインポリシー規則セットファイルのパスを入力します。

     パスは、次の構文に従う必要があります。

     **$/** `TeamProjectName` **/** `VersionControlPath`

    > [!NOTE]
    > **ソース管理エクスプローラー** では、次のいずれかの手順を使用してパスをコピーできます。

    - [ **フォルダー** ] ウィンドウで、規則セットファイルが格納されているフォルダーをクリックします。 [ **ソース** ] ボックスに表示されているフォルダーのバージョンコントロールパスをコピーし、規則セットファイルの名前を手動で入力します。

    - [詳細] ウィンドウで、規則セットファイルを右クリックし、[ **プロパティ**] をクリックします。 [ **全般** ] タブで、[ **サーバー名**] の値をコピーします。

## <a name="synchronize-code-projects-to-the-check-in-policy-rule-set"></a>コードプロジェクトをチェックインポリシー規則セットと同期する

コードプロジェクトの [プロパティ] ダイアログボックスで、コードプロジェクト構成のコード分析規則セットとしてプロジェクトチェックインポリシー規則セットを指定します。 規則セットがコードプロジェクトと同じドライブにある場合、[ファイル] ダイアログボックスでパスを選択したときに規則セットを指定するために、相対パスが使用されます。 相対パスを使用すると、プロジェクトプロパティの設定を、類似したローカルバージョン管理構造を使用する他のコンピューターに移植できます。

### <a name="to-specify-a-project-rule-set-as-the-rule-set-of-a-code-project"></a>プロジェクト規則セットをコードプロジェクトの規則セットとして指定するには

1. 必要に応じて、チェックインポリシー規則セットのフォルダーとファイルをバージョン管理から取得します。

   [ルールセット] フォルダーを右クリックし、[**最新バージョンの取得**] をクリックすることで、**ソース管理エクスプローラー** でこの手順を実行できます。

2. **ソリューションエクスプローラー** で、コードプロジェクトを右クリックし、[**プロパティ**] をクリックします。

3. **[コード分析] をクリックし** ます。

4. 必要に応じて、[ **構成** ] と [ **プラットフォーム** ] の一覧で適切なオプションをクリックします。

::: moniker range="vs-2017"

5. 指定された構成を使用してコードプロジェクトがビルドされるたびにコード分析を実行するには、[ **ビルド時にコード分析を有効に** する] チェックボックスをオンにします。

::: moniker-end

::: moniker range=">=vs-2019"

5. 指定された構成を使用してコードプロジェクトがビルドされるたびにコード分析を実行するには、[**バイナリアナライザー** ] セクションの [**ビルドで実行**] を選択します。

::: moniker-end

6. [ **この規則セットを実行** する] の一覧で、をクリックし **\<Browse>** ます。

8. チェックインポリシー規則セットファイルのローカルバージョンを選択します。
