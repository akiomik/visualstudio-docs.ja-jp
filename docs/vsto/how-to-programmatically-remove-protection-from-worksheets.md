---
title: '方法: プログラムによってワークシートから保護を削除する'
description: Visual Studio を使用して、Microsoft Excel ワークシートからプログラムによって保護を削除する方法について説明します。
ms.custom: SEO-VS-2020
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 85f659248528d0d7cf4357ffe2d1c2c5f88df9e9
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99906763"
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>方法: プログラムによってワークシートから保護を削除する
  プログラムを使用して、Microsoft Office Excel ワークシートから保護を削除できます。

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 次の例では、変数 `getPasswordFromUser`を使用して、ユーザーから取得したパスワードを格納します。

## <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>ドキュメント レベルのカスタマイズでワークシートの保護を解除するには

1. ワークシートのメソッドを呼び出し、必要に応じて <xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A> パスワードを渡します。 この例では、 `Sheet1`という名前のワークシートを操作していると仮定します。

     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]

## <a name="to-unprotect-a-worksheet-in-a-vsto-add-in"></a>VSTO アドインでワークシートの保護を解除するには

1. <xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A>アクティブなワークシートのメソッドを呼び出し、必要に応じてパスワードを渡します。

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]

## <a name="see-also"></a>関連項目
- [ワークシートを操作する](../vsto/working-with-worksheets.md)
- [方法: プログラムによってワークシートを保護する](../vsto/how-to-programmatically-protect-worksheets.md)
- [方法: プログラムによってブックを保護する](../vsto/how-to-programmatically-protect-workbooks.md)
- [方法: プログラムによってワークシートを非表示にする](../vsto/how-to-programmatically-hide-worksheets.md)
- [Office プロジェクト内のオブジェクトへのグローバルアクセス](../vsto/global-access-to-objects-in-office-projects.md)
