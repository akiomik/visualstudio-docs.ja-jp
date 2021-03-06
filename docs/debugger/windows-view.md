---
title: ウィンドウ ビュー | Microsoft Docs
description: ウィンドウ ビューには、あらゆるウィンドウとコントロールがツリー形式で表示されます。 このツリーを、関心のあるウィンドウに関する情報を取得するための出発点として利用します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.externaltools.spyplus.windowsview
helpviewer_keywords:
- Windows view
ms.assetid: 154786ce-c803-4bfb-8198-f7962a900363
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 34a66e9c2728798330b52f87afe8ecdea8733508
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99906334"
---
# <a name="windows-view"></a>ウィンドウ ビュー
最初に Spy++ を開いたとき、ウィンドウ ビューには、システム内のすべてのウィンドウとコントロールのツリーが表示されます。 ウィンドウ ハンドルとクラス名が表示されます。 現在のデスクトップ ウィンドウがツリーの一番上にあります。 その他すべてのウィンドウはデスクトップの子であり、標準のウィンドウ階層に従って一覧表示されます。 兄弟ウィンドウは、その親の下でインデントされ、展開可能な一覧として表示されます。

 次の図は、最上位ノードが展開された一般的な Spy++ ウィンドウ ビューを示しています。

 ![Spy&#43;&#43; ウィンドウ ビュー](../debugger/media/spy--_windowsview.png "Spy++_WindowsView") Spy++ ウィンドウ ビュー

 現在のデスクトップ ウィンドウがツリーの一番上にあります。 その他すべてのウィンドウはデスクトップの子であり、兄弟ウィンドウが Z オーダーによって並べ替えられ、標準のウィンドウ階層に従って一覧表示されます。 ノードの横にある [+] または [-] をクリックすると、ツリーの親ノードを展開または折りたたむことができます。

 ウィンドウ ビューにフォーカスがある場合は、[[ウィンドウ検索] ダイアログ ボックス](../debugger/window-search-dialog-box.md)のファインダー ツールを使用して、システムで開いている任意のウィンドウの情報を表示できます。

## <a name="in-this-section"></a>このセクションの内容
 [方法: ファインダー ツールの使用](../debugger/how-to-use-the-finder-tool.md) このツールでプロパティまたはメッセージをウィンドウからスキャンする方法が表示されます。

 [方法: ウィンドウ ビューでのウィンドウの検索](../debugger/how-to-search-for-a-window-in-windows-view.md) ウィンドウ ビューで特定のウィンドウを検索する方法について説明します。

 [方法: [ウィンドウ プロパティ] の表示](../debugger/how-to-display-window-properties.md) [ウィンドウ プロパティ] ダイアログ ボックスを開くためのプロシージャ。

## <a name="related-sections"></a>関連項目
 [Spy++ ビュー](../debugger/spy-increment-views.md) ウィンドウ、メッセージ、プロセス、およびスレッドの Spy++ ツリー ビューについて説明します。

 [Spy++ の使用](../debugger/using-spy-increment.md) Spy++ ツールを紹介し、その使用方法について説明します。

 [[ウィンドウ検索] ダイアログ ボックス](../debugger/find-window-dialog-box.md) 特定のウィンドウからのプロパティまたはメッセージを表示するために使用されます。

 [[ウィンドウ検索] ダイアログ ボックス](../debugger/window-search-dialog-box.md) ウィンドウ ビューで特定のウィンドウのノードを検索するために使用されます。

 [[ウィンドウ プロパティ] ダイアログ ボックス](../debugger/window-properties-dialog-box.md) ウィンドウ ビューで選択したウィンドウのプロパティを表示するために使用します。

 [Spy++ リファレンス](../debugger/spy-increment-reference.md) Spy++ の各メニューとダイアログ ボックスについて説明するセクションが含まれています。