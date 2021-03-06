---
title: ピクチャ ビューアー アプリを実行して他の機能を試す
description: ピクチャ ビューアーの作成チュートリアルでピクチャ ビューアー アプリを実行し、その他の機能を試します。
ms.date: 09/11/2019
ms.custom: SEO-VS-2020
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
author: ornellaalt
ms.author: ornella
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 1a4488c212cabe95d73f75246fb297c17ce073b4
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99950901"
---
# <a name="step-11-run-your-picture-viewer-app-and-try-other-features"></a>手順 11: ピクチャ ビューアー アプリを実行して他の機能を試す

ピクチャ ビューアー アプリが完成し、実行する準備ができました。 アプリを実行して <xref:System.Windows.Forms.PictureBox> の背景色を設定できます。 さらに詳しく学習するには、フォームの色の変更、ボタンとチェック ボックスのカスタマイズ、フォームのプロパティの変更などを行って、アプリケーションを改善してみてください。

## <a name="how-to-run-your-app-and-set-the-background-color"></a>アプリを実行して背景色を設定する方法

1. **F5** キーを押すか、メニュー バーで **[デバッグ]** > **[デバッグ開始]** の順にクリックします。

1. ピクチャを開く前に、**[Set the background color]** ボタンをクリックします。 **[色]** ダイアログ ボックスが表示されます。

     ![[色] ダイアログ ボックス](../ide/media/express_colordialog.png)<br/>
* **[色]** ダイアログ ボックス*

1. 色を選択して PictureBox の背景色を設定します。 `backgroundButton_Click()` (または、`BackgroundButton_Click()`) メソッドを詳しく調べて動作を確認します。

    > [!NOTE]
    > ピクチャは、**[ファイルを開く]** ダイアログ ボックスに URL を貼り付けることでインターネットから読み込むことができます。 背景色の表示を確認するには、背景が透明な画像を探してみてください。

1. **[Clear the picture]** ボタンをクリックして、ピクチャが消去されることを確認します。 次に、**[閉じる]** ボタンをクリックしてアプリを終了します。

## <a name="try-other-features"></a>その他の機能を試す

* **BackColor** プロパティを使用して、フォームとボタンの色を変更します。

* **Font** プロパティと **ForeColor** プロパティを使用して、ボタンとチェック ボックスをカスタマイズします。

* フォームの **FormBorderStyle** プロパティと **ControlBox** プロパティを変更します。

* フォームの **AcceptButton** プロパティと **CancelButton** プロパティを使用して、ユーザーが **Enter** キーまたは **Esc** キーを押したときに自動的にそれらのボタンが選択されるようにします。 ユーザーが **Enter** キーを押したときには **[ファイルを開く]** ダイアログ ボックスが開き、**Esc** キーを押したときには閉じるように、アプリを設定します。

## <a name="next-steps"></a>次の手順

詳細については、引き続き以下のチュートリアルをご覧ください。

> [!div class="nextstepaction"]
> [チュートリアル 2: 制限時間ありの計算クイズの作成](../ide/tutorial-2-create-a-timed-math-quiz.md)

チュートリアルの前の手順に戻るには、「[手順 10: その他のボタンおよびチェック ボックスに対するコードの記述](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md)」を参照してください。

## <a name="see-also"></a>関連項目

* [その他の C# のチュートリアル](../get-started/csharp/index.yml)
* [その他の Visual Basic のチュートリアル](../get-started/visual-basic/index.yml)
* [C++ チュートリアル](/cpp/get-started/tutorial-console-cpp)