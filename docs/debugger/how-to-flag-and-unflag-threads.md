---
title: スレッドに対するフラグの設定と解除 | Microsoft Docs
description: Visual Studio でのスレッドに対するフラグの設定と解除について学習します。 スレッド、複数のスレッド、またはすべてのスレッドに対してフラグを設定または解除します。 コードだけ、またはモジュールに関連付けられているものにフラグを設定します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: d5f31bb73b4a22a11235e471dfa1fa99545e422e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99877604"
---
# <a name="how-to-flag-and-unflag-threads-c-visual-basic-c"></a>方法: スレッドに対するフラグの設定と解除 (C#、Visual Basic、C++)

**[スレッド]** 、 **[並列スタック]** (スレッド ビュー)、 **[並列ウォッチ]** 、 **[GPU スレッド]** の各ウィンドウで、スレッドをアイコンでマークすることによって、特に注目するスレッドにフラグを設定できます。 このアイコンにより、フラグが設定されているスレッドをそれ以外のスレッドと簡単に区別できるようになります。

フラグが設定されたスレッドは、 **[デバッグの場所]** ツール バーの **[スレッド]** ボックスの一覧に加え、他のマルチスレッド デバッグ ウィンドウでも特別な扱いを受けます。 すべてのスレッドを表示することも、**スレッド** の一覧またはその他のウィンドウ内のフラグが設定されたスレッドだけを表示することもできます。

### <a name="to-flag-or-unflag-a-thread"></a>スレッドのフラグを設定または設定解除するには

- **[スレッド]** ウィンドウまたは **[並列ウォッチ]** ウィンドウで、注目しているスレッドを見つけ、フラグ アイコンをクリックして、フラグをオンまたはオフにします。
- **[並列スタック]** ウィンドウで、スレッドまたはスレッド グループを右クリックし、 **[フラグ設定 / \<thread>]** または **[フラグ解除 / \<thread>]** を選択します。

### <a name="to-unflag-all-threads"></a>すべてのスレッドのフラグを解除するには

- **[スレッド]** ウィンドウで、いずれかのスレッドを右クリックし、 **[すべてのスレッドのフラグを解除]** をクリックします。
- **[並列ウォッチ]** ウィンドウで、フラグが設定されたすべてのスレッドを選択し、右クリックして、 **[フラグ解除]** を選択します。

### <a name="to-display-only-flagged-threads"></a>フラグが設定されたスレッドのみ表示するには

- マルチスレッド デバッグ ウィンドウのいずれかで、 **[フラグが設定されているスレッドのみを表示]** を選択します。

### <a name="to-flag-just-my-code"></a>マイ コードのみにフラグを設定するには

1. **[スレッド]** ウィンドウの上部にあるツール バーで、フラグ アイコンをクリックします。

2. ドロップダウン リストで、 **[マイ コードのみにフラグを設定]** をクリックします。

### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>選択したモジュールに関連するスレッドにフラグを設定するには

1. **[スレッド]** ウィンドウのツール バーで、フラグ アイコンをクリックします。

2. ドロップダウン リストで、 **[カスタム モジュール選択にフラグを設定]** をクリックします。

3. **[モジュールの選択]** ダイアログ ボックスで、目的のモジュールを選択します。

4. (省略可能) **[検索]** ボックスに、特定のモジュールを検索するための文字列を入力します。

5. **[OK]** をクリックします。

## <a name="see-also"></a>関連項目
- [マルチスレッド アプリケーションのデバッグ](../debugger/debug-multithreaded-applications-in-visual-studio.md)
- [マルチ スレッド アプリケーションのデバッグの開始](../debugger/get-started-debugging-multithreaded-apps.md)
- [チュートリアル: [スレッド] ウィンドウを使用したマルチスレッド アプリケーションのデバッグ](../debugger/how-to-use-the-threads-window.md)