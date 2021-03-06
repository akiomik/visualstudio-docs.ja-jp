---
title: XAML ホット リロードのトラブルシューティング
description: XAML ホットリロードで発生する可能性のある問題を修正します。
ms.date: 09/04/2019
ms.topic: troubleshooting
helpviewer_keywords:
- xaml edit and continue, troubleshooting
- xaml hot reload, troubleshooting
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 4e13fd71c9d53ef49d7f7372986bfabc29c62747
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99890449"
---
# <a name="troubleshooting-xaml-hot-reload"></a>XAML ホット リロードのトラブルシューティング

このトラブルシューティングガイドでは、XAML ホットリロードが正常に動作しない原因となる問題を解決するための詳細な手順について説明します。

XAML ホットリロードは、WPF アプリと UWP アプリでサポートされています。 オペレーティングシステムとツールの要件の詳細については、「 [Xaml ホットリロードを使用した実行中の xaml コードの書き込みとデバッグ](xaml-hot-reload.md)」を参照してください。

## <a name="hot-reload-is-not-available"></a>ホットリロードは使用できません

アプリのデバッグ中に、アプリ内ツールバーの "ホットリロードが使用できません" というメッセージが表示された場合は、この記事で説明されている手順に従って問題を解決してください。

## <a name="verify-that-xaml-hot-reload-is-enabled"></a>XAML ホットリロードが有効になっていることを確認する

この機能は既定で有効になっています。 アプリのデバッグを開始するときに、アプリ内ツールバーが表示されていることを確認します。これにより、XAML ホットリロードが使用可能であることが確認できます。

![XAML ホットリロードを利用できます](../debugger/media/xaml-hot-reload-available.png)

アプリ内ツールバーが表示されない場合は、**デバッグ** オプションの [全般] を開き  >    >  ます。 [ **Xaml の UI デバッグツールを有効** にする] と [ **xaml ホットリロードを有効に** する] の両方が選択されていることを確認します。

![Visual Studio の [デバッグオプション] ウィンドウのスクリーンショット。 一般的なデバッグオプションが選択され、[XAML ホットリロードを有効にする] オプションがオンになっています。](../debugger/media/xaml-hot-reload-enable.png)

これらのオプションを選択した場合は、[ライブビジュアルツリー (  >  **Windows**  >  **live ビジュアルツリー** のデバッグ)] に移動し、[**ランタイムツールをアプリケーションツールバーに表示**] ボタン (左端) が選択されていることを確認します。

![ライブビジュアルツリーウィンドウの上部にあるツールバーのスクリーンショット。 [アプリケーションのランタイムツールを表示] ボタンが選択されています。](../debugger/media/xaml-hot-reload-show-runtime-tools.png)

## <a name="verify-that-you-use-start-debugging-rather-than-attach-to-process"></a>プロセスにアタッチするのではなく、デバッグの開始を使用することを確認します。

XAML ホットリロード `ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO` では、アプリケーションの起動時に環境変数が1に設定されている必要があります。 Visual Studio **は、デバッグ**  >  **開始デバッグ**(または **F5**) コマンドの一部として、これを自動的に設定します。   >  代わりに [**プロセスにアタッチ**] コマンドを使用して XAML ホットリロードを使用する場合は、環境変数を自分で設定します。

> [!NOTE]
> 環境変数を設定するには、[開始] ボタンを使用して "環境変数" を検索し、[ **システム環境変数の編集**] を選択します。 表示されるダイアログボックスで、[ **環境変数**] を選択し、ユーザー変数として追加して、値をに設定し `1` ます。 クリーンアップするには、デバッグが完了したら変数を削除します。

## <a name="verify-that-your-msbuild-properties-are-correct"></a>MSBuild プロパティが正しいことを確認する

既定では、ソース情報はデバッグ構成に含まれています。 これは、プロジェクトファイル (* .csproj など) の MSBuild プロパティによって制御されます。 WPF の場合、プロパティはです `XamlDebuggingInformation` 。これは、に設定する必要があり `True` ます。 UWP の場合、プロパティはです `DisableXbfLineInfo` 。これは、に設定する必要があり `False` ます。 次に例を示します。

WPF

`<XamlDebuggingInformation>True</XamlDebuggingInformation>`

UWP

`<DisableXbfLineInfo>False</DisableXbfLineInfo>`

## <a name="verify-that-you-are-using-the-correct-build-configuration-name"></a>正しいビルド構成名を使用していることを確認します

XAML ホットリロードをサポートするには、正しい MSBuild プロパティを手動で設定するか (前のセクションを参照)、既定のビルド構成名 (Debug) を使用する必要があります。 MSBuild プロパティを正しく設定しない場合、カスタムビルド構成名は機能しません。また、リリースビルドも実行されません。

## <a name="verify-that-your-xaml-file-has-no-errors"></a>XAML ファイルにエラーがないことを確認する

XAML ファイルで **エラー一覧** にエラーが表示されている場合、Xaml ホットリロードが機能しない可能性があります。

## <a name="see-also"></a>関連項目

[XAML ホットリロードを使用して実行中の XAML コードを記述およびデバッグする](xaml-hot-reload.md)
