---
title: メニューコマンドのテキストを変更する |Microsoft Docs
description: IMenuCommandService サービスを使用してメニューコマンドのテキストラベルを変更する方法については、このコード例を確認してください。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- menus, changing text
- text, menus
- commands, changing text
ms.assetid: 5cb676a0-c6e2-47e5-bd2b-133dc8842e46
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: e2d812dbee833358f682b5227785c78322efe44a
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99911242"
---
# <a name="change-the-text-of-a-menu-command"></a>メニューコマンドのテキストを変更する
次の手順は、サービスを使用してメニューコマンドのテキストラベルを変更する方法を示して <xref:System.ComponentModel.Design.IMenuCommandService> います。

## <a name="changing-a-menu-command-label-with-the-imenucommandservice"></a>IMenuCommandService を使用してメニューコマンドのラベルを変更する

1. `MenuText` **ChangeMenuText** という名前のメニューコマンドを使用して、という名前の VSIX プロジェクトを作成します。 詳細については、「 [メニューコマンドを使用して拡張機能を作成](../extensibility/creating-an-extension-with-a-menu-command.md)する」を参照してください。

2. 次の例に示すように、 *vsct* ファイルで、 `TextChanges` メニューコマンドにフラグを追加します。

    ```xml
    <Button guid="guidChangeMenuTextPackageCmdSet" id="ChangeMenuTextId" priority="0x0100" type="Button">
        <Parent guid="guidChangeMenuTextPackageCmdSet" id="MyMenuGroup" />
        <Icon guid="guidImages" id="bmpPic1" />
        <CommandFlag>TextChanges</CommandFlag>
        <Strings>
            <ButtonText>Invoke ChangeMenuText</ButtonText>
        </Strings>
    </Button>
    ```

3. *ChangeMenuText.cs* ファイルで、メニューコマンドが表示される前に呼び出されるイベントハンドラーを作成します。

    ```csharp
    private void OnBeforeQueryStatus(object sender, EventArgs e)
    {
        var myCommand = sender as OleMenuCommand;
        if (null != myCommand)
        {
            myCommand.Text = "New Text";
        }
    }
    ```

    また、オブジェクトの、、の各プロパティを変更することで、このメソッドのメニューコマンドの状態を更新することもでき <xref:System.ComponentModel.Design.MenuCommand.Visible%2A> <xref:System.ComponentModel.Design.MenuCommand.Checked%2A> <xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> ます。

4. ChangeMenuText コンストラクターで、元のコマンド初期化と配置コードを、メニューコマンドを表す (ではなく) を作成するコードに置き換えて、 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> `MenuCommand` イベントハンドラーを追加し、メニューコマンド <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> をメニューコマンドサービスに渡します。

    次のようになります。

    ```csharp
    private ChangeMenuText(AsyncPackage package, OleMenuCommandService commandService)
    {
        this.package = package ?? throw new ArgumentNullException(nameof(package));
        commandService = commandService ?? throw new ArgumentNullException(nameof(commandService));
        
        var menuCommandID = new CommandID(CommandSet, CommandId);
        var menuItem = new OleMenuCommand(this.Excute, menuCommandID);
        menuItem.BeforeQueryStatus += new EventHandler(OnBeforeQueryStatus);
        commandService.AddCommand(menuItem);
    }
    ```

5. プロジェクトをビルドし、デバッグを開始します。 Visual Studio の実験用インスタンスが表示されます。

6. [ **ツール** ] メニューに、 **Invoke ChangeMenuText** という名前のコマンドが表示されます。

7. コマンドをクリックします。 **Menuitemcallback** が呼び出されたことを示すメッセージボックスが表示されます。 メッセージボックスを閉じると、[ツール] メニューのコマンドの名前が **新しいテキスト** になっていることがわかります。
