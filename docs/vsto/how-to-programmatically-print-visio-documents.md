---
title: '方法: プログラムによって Visio 図面を印刷する'
description: 完全な Microsoft Visio 図面を印刷する方法、またはそのドキュメント内の特定のページだけを印刷する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], printing Visio documents
- documents [Office development in Visual Studio], printing Visio documents
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: df2cd5137f05caaf7b8437fb2d903aeecc7d3e9c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99933038"
---
# <a name="how-to-programmatically-print-visio-documents"></a>方法: プログラムによって Visio 図面を印刷する
  Microsoft Office Visio 図面の全体または特定のページだけを印刷することができます。

 印刷メソッドの詳細については、 [Microsoft.Office.Interop.Visio.Document.Print](/office/vba/api/Visio.Document.Print) メソッドと [Microsoft.Office.Interop.Visio.Page.Print](/office/vba/api/Visio.Page.Print) メソッドの VBA リファレンス ドキュメントを参照してください。

## <a name="print-a-visio-document"></a>Visio 図面を印刷する

### <a name="to-print-a-complete-document"></a>図面全体を印刷するには

- 印刷する `Microsoft.Office.Interop.Visio.Document.Print` オブジェクトの `Microsoft.Office.Interop.Visio.Document` メソッドを呼び出します。

     アクティブ文書を印刷するコード例を次に示します。 この例を使用するには、プロジェクトの `ThisAddIn` クラスからコードを実行します。

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#8)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#8)]

## <a name="print-a-page-of-a-visio-document"></a>Visio 図面のページを印刷する

### <a name="to-print-a-page-of-a-document"></a>特定のページの図面を印刷するには

- 印刷する `Microsoft.Office.Interop.Visio.Pages.Print` オブジェクトの `Microsoft.Office.Interop.Visio.Pages` メソッドを呼び出します。

     アクティブ文書の最初のページを印刷するコード例を次に示します。 この例を使用するには、プロジェクトの `ThisAddIn` クラスからコードを実行します。

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#9)]

## <a name="see-also"></a>関連項目
- [Visio ソリューション](../vsto/visio-solutions.md)
- [Visio オブジェクトモデルの概要](../vsto/visio-object-model-overview.md)
- [方法: プログラムによって新しい Visio 図面を作成する](../vsto/how-to-programmatically-create-new-visio-documents.md)
- [方法: プログラムによって Visio 図面を開く](../vsto/how-to-programmatically-open-visio-documents.md)
- [方法: プログラムによって Visio 図面を閉じる](../vsto/how-to-programmatically-close-visio-documents.md)
- [方法: プログラムによって Visio 図面を保存する](../vsto/how-to-programmatically-save-visio-documents.md)
