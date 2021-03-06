---
title: Windows ユーザー向けの Visual Studio for Mac
description: Windows オペレーティング システムでの Visual Studio 使用に精通している開発者向けの Visual Studio for Mac 入門。
author: heiligerdankgesang
ms.author: dominicn
ms.date: 11/09/2020
ms.assetid: 61CB6883-08CE-470F-8599-6F7570DB756E
ms.openlocfilehash: 880811c675aac34a18a65c6eccb8ee10f3347d4c
ms.sourcegitcommit: 2cf3a03044592367191b836b9d19028768141470
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "94493375"
---
# <a name="visual-studio-for-mac-for-windows-users"></a>Windows ユーザー向けの Visual Studio for Mac

オペレーティング システム間の移行は困難な場合があります。 多くの場合、クロスプラットフォーム アプリケーションには、ユーザー インターフェイスからメニュー項目の分類まで、微妙な違いがあります。 ここでは、Visual Studio for Mac と Visual Studio for Windows の最もよく見られる相違点について説明します。 macOS と Windows 間のいくつかの異なる規則についても説明します。

## <a name="keyboard-shortcuts"></a>キーボード ショートカット

開発者の多くは、キーボードを使用してタスクやナビゲーションを行うことに慣れています。 キーボードのキーの一部は、Mac と Windows PC 間で共通しています。 コピーや貼り付けなどのキーボード操作には、同じキーの組み合わせが使用されているとお考えになるかもしれません。 常にそうであるとは限りません。 幸いなことに、Visual Studio for Mac でキー バインドを変更して、Windows での Visual Studio と厳密に一致させることができます。

初めて Visual Studio for Mac を実行すると、キーボード ショートカットの選択ウィンドウが表示されます。![キー バインド ウィンドウ](media/ide-tour-2019-keyboard-shortcut.png)

後でキー バインドを変更する場合は、次のようにユーザー設定で設定を確認できます。![キー バインドのユーザー設定](media/customizing-the-ide-image10a.png)

macOS では、システム全体で Windows とは異なるショートカットを使用していることに注意してください。 キー バインドのユーザー設定を変更すると、使い慣れた Windows のショートカットを Visual Studio for Mac で使用できるようになります。 ただし、macOS の他の領域では、macOS のショートカットに慣れておく必要があります。

macOS のコマンド (⌘) 修飾子キーは、一般的に Windows の Ctrl キーと置き換えることができます。 いくつかの例と、一般的に使用されるその他のショートカットを次に示します。

|タスク                   |Windows のショートカット         |macOS のショートカット      |
|-----------------------|-------------------------|--------------------|
|コピー                   |`Ctrl + C`               |`⌘ + C`             |
|貼り付け                  |`Ctrl + V`               |`⌘ + V`             |
|切り取り                    |`Ctrl + X`               |`⌘ + X`             |
|元に戻す                   |`Ctrl + Z`               |`⌘ + Z`             |
|やり直し                   |`Ctrl + Shift + Z`       |`⌘ + Shift + Z`     |
|カーソルの右を削除する |`Delete`                 |`fn + Backspace`    |
|単語を削除する            |`Ctrl + Delete`          |`fn + ⌥ + Backspace`|

> [!TIP]
> macOS のショートカット全体の一覧については、[Apple サポート Web サイト](https://support.apple.com/en-us/HT201236)を参照してください。

## <a name="menus"></a>メニュー

macOS のメニューは、Windows のメニューと構成が異なります。 Visual Studio for Mac も例外ではありません。 最も一般的なメニュー オプションをいくつか次に示します。

|タスク                   |Visual Studio (Windows)                                              |Visual Studio for Mac                |
|-----------------------|---------------------------------------------------------------------|-------------------------------------|
|ユーザー設定 (オプション)  |[ツール] > [オプション]                                                   |[Visual Studio] > [ユーザー設定]       |
|拡張機能             |[拡張機能] > [拡張機能の管理]                                       |[Visual Studio] > [拡張機能]        |
|Layouts                |[ウィンドウ] > [ウィンドウ レイアウトを適用] > (レイアウトを選択する)                       |[表示] > [レイアウト] > (レイアウトを選択する)               |
|更新プログラム                |[ヘルプ] > [更新プログラムのチェック]                                             |[Visual Studio] > [更新プログラムのチェック] |
|NuGet パッケージ マネージャー  |[ツール] > [NuGet パッケージ マネージャー] > [Manage NuGet Packages or Solution]\(NuGet パッケージまたはソリューションの管理\) |[プロジェクト] > [NuGet パッケージの管理]   |
|ツールを探す             |[編集] > [検索と置換] > (ツールを選択する)                              |[検索] > (ツールを選択する)               |
|Visual Studio について    |[ヘルプ] > [Microsoft Visual Studio のバージョン情報]                                 |[Visual Studio] > [Visual Studio のバージョン]  

> [!NOTE]
> Visual Studio for Mac の一般的な機能の概要については、[IDE のツアー](ide-tour.md)を参照してください。