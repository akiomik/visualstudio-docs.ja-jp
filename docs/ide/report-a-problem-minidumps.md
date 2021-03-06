---
title: すべての呼び出し履歴を含むミニダンプを作成する
description: すべての呼び出し履歴に関する情報が含まれる Visual Studio プロセスのミニダンプを作成する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 06/27/2019
ms.topic: how-to
helpviewer_keywords:
- minidumps for Visual Studio issues"
author: corob-msft
ms.author: corob
manager: jmartens
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.description: Collect minidumps to send to Microsoft for help with troubleshooting issues with Visual Studio
ms.openlocfilehash: 44ab0873580c7c541fc5e7fdde56cc1780929b75
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99970778"
---
# <a name="create-minidumps-for-a-visual-studio-process-with-all-call-stacks"></a>すべての呼び出し履歴を含む Visual Studio プロセスのミニダンプを作成する

Microsoft から、すべての呼び出し履歴の情報を含む実行中の Visual Studio プロセスのミニダンプの提供をお願いされる場合があります。 この情報を収集するには、以下の手順を実行します。

## <a name="create-the-minidump-file"></a>ミニダンプ ファイルの作成

1. Visual Studio の新しいインスタンスを起動します。
1. メイン メニューから、 **[デバッグ]**  >  **[プロセスにアタッチ]** の順に選択します。
1. 関連する **[マネージド]** と **[ネイティブ]** チェック ボックスをオンにして、**[アタッチ]** を押します。

   ![プロセスにアタッチする](../ide/media/attach-to-process.png)

1. 実行中のプロセスの一覧から、アタッチする別の Visual Studio インスタンスを選択します。
1. メイン メニューから、 **[デバッグ]**  >  **[すべて中断]** の順に選択します。
1. メイン メニューから、 **[デバッグ]**  >  **[名前を付けてダンプを保存]** の順に選択します。

## <a name="get-the-call-stacks-from-the-minidump"></a>ミニダンプから呼び出し履歴を取得する

1. Visual Studio でダンプ ファイルを開きます。
1. **[ツール]**  >  **[オプション]**  >  **[デバッグ]**  >  **[シンボル]** に移動し、 **[シンボル ファイル (.pdb) の場所]** 内で **[Microsoft シンボル サーバー]** がチェックされていることを確認します。
1. **[コマンド]** ウィンドウを開きます (**[ビュー]** > **[その他のウィンドウ]** > **[コマンド ウィンドウ]**)
1. 「~*k」と入力します。 すべてのスレッドの呼び出し履歴がウィンドウに表示されます。
1. [コマンド ウィンドウ] からすべてのテキストをコピーし、テキスト ファイルに保存します。
1. その txt ファイルをバグに添付します。
