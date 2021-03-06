---
title: Office Word の [キーボード] ([オプション] ダイアログボックス-[設定])
description: '[動的キーボードスキーム] を選択して、ドキュメントにフォーカスがあるときに Microsoft Word がショートカットキーコマンドを受け取るようにする方法について説明します。'
ms.custom: SEO-VS-2020
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Microsoft_Office_Tools.Microsoft_Office_Word.Keyboard
- VS.ToolsOptionsPages.Microsoft_Office_Keyboard_Settings.Microsoft_Office_Word_Keyboard
- VST.WordOptions.KeyboardMappingScheme
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- keyboard shortcuts, Office development in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 0138fcd73ddf07202a9111ec2b3d17dcc0fb7a0e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99879424"
---
# <a name="microsoft-office-word-keyboard-settings-options-dialog-box"></a>Microsoft Office Word のキーボードの設定、[オプション] ダイアログボックス
  Microsoft Office Word と Visual Studio の両方で、ショートカットキーが処理されます。 Word と Visual Studio では、同じショートカットキーの組み合わせを使用して、さまざまなコマンドを実行できます。 Word が Visual Studio のドキュメントレベルのプロジェクトで開かれている場合、一度に1つのアプリケーションだけがショートカットキーコマンドを受け取ります。 既定では、Visual Studio はすべてのショートカットキーコマンドを受け取りますが、[ **動的キーボードスキーム**] を選択して、ドキュメントにフォーカスがあるときに Word を受け取るようにすることができます。

 現在ショートカットキーを処理しているアプリケーションのコマンドに割り当てられていないショートカットキーを使用すると、ショートカットキーが他のアプリケーションに渡されます。

 選択したオプションは、変更するまで Word プロジェクトに対して有効なままになります。 選択内容は Microsoft Office Excel プロジェクトには影響しません。excel の Microsoft Office Excel のキーボードオプションを使用して、変更を加える必要があります。

## <a name="uielement-list"></a>UIElement の一覧
 **Visual Studio キーボードスキーム** Word 文書にフォーカスがある場合でも、Visual Studio はすべてのショートカットキーコマンドを受け取ります。 たとえば、ドキュメントにフォーカスがある状態でファンクションキー **F5** キーを押すと、Visual Studio によってソリューションのデバッグが開始されます。

 **動的キーボードスキーム** Visual Studio は、フォーカスがあるときにのみショートカットキーコマンドを受け取ります。 Word 文書にフォーカスがある場合、Word はすべてのショートカットキーコマンドを受け取ります。 たとえば、Word 文書にフォーカスがあるときにファンクションキー **F5** キーを押すと、word によって [ **検索と置換** ] ダイアログボックスが開き、[ **移動** ] タブが選択されます。 Visual Studio にフォーカスがあるときに **F5** キーを押すと、ソリューションのデバッグが開始されます。

## <a name="see-also"></a>関連項目
- [Microsoft Office Excel キーボード、Microsoft Office キーボード設定、[オプション] ダイアログボックス](../vsto/microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)
