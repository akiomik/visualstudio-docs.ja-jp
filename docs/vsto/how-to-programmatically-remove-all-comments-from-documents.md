---
title: '方法: プログラムによって文書からすべてのコメントを削除する'
description: Visual Studio を使用して、Microsoft Word 文書からすべてのコメントをプログラムで削除する方法について説明します。
ms.custom: SEO-VS-2020
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], removing comments
- comments, removing from documents
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 8cb4e2e8fe51dfe6596f58470c714e8ef2412d46
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99968867"
---
# <a name="how-to-programmatically-remove-all-comments-from-documents"></a>方法: プログラムによって文書からすべてのコメントを削除する
  `DeleteAllComments` メソッドを使用して、Microsoft Office Word 文書からすべてのコメントを削除します。

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-remove-all-comments-from-a-document-that-is-part-of-a-document-level-customization"></a>ドキュメント レベルのカスタマイズの一部であるドキュメントから、すべてのコメントを削除するには

1. プロジェクトの <xref:Microsoft.Office.Tools.Word.Document.DeleteAllComments%2A> クラスの `ThisDocument` メソッドを呼び出します。 このコード例を使用するには、 `ThisDocument` クラスからコードを実行します。

     [!code-vb[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#119)]

## <a name="to-remove-all-comments-from-a-document-by-using-a-vsto-add-in"></a>VSTO アドインを使用してドキュメントからすべてのコメントを削除するには

1. コメントを削除する <xref:Microsoft.Office.Interop.Word._Document.DeleteAllComments%2A> から <xref:Microsoft.Office.Interop.Word.Document> メソッドを呼び出します。

     次に示すコード例では、アクティブ ドキュメントからすべてのコメントを削除します。 このコード例を使用するには、プロジェクトの `ThisAddIn` クラスからコードを実行します。

     [!code-vb[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#119)]

## <a name="see-also"></a>関連項目
- [方法: プログラムによって文書内のテキストにコメントを追加する](../vsto/how-to-programmatically-add-comments-to-text-in-documents.md)
- [ドキュメントホスト項目](../vsto/document-host-item.md)
