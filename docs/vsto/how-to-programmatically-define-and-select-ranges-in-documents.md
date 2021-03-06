---
title: '方法: プログラムによって文書内の範囲を定義および選択する'
description: Range オブジェクトを使用して、Microsoft Word 文書内の範囲をプログラムによって定義および選択する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], selecting sentences
- documents [Office development in Visual Studio], ranges
- sentences, selecting in documents
- ranges, selecting in documents
- ranges, defining in documents
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: e9c703f4d4e747934d1bab458b75a9d499f0d439
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99963953"
---
# <a name="how-to-programmatically-define-and-select-ranges-in-documents"></a>方法: プログラムによって文書内の範囲を定義および選択する
  Microsoft Office Word 文書内に範囲を定義するには、<xref:Microsoft.Office.Interop.Word.Range> オブジェクトを使用します。 ドキュメント全体をいくつかの方法で選択できます。たとえば、 <xref:Microsoft.Office.Interop.Word.Range.Select%2A> オブジェクトのメソッドを使用する <xref:Microsoft.Office.Interop.Word.Range> か、 <xref:Microsoft.Office.Tools.Word.Document> クラス (ドキュメントレベルのカスタマイズの場合) またはクラス (VSTO アドインの場合) の Content プロパティを使用し <xref:Microsoft.Office.Interop.Word.Document> ます。

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="define-a-range"></a>範囲の定義
 次の使用例は、作業中の文書の最初の 7 文字 (非印刷文字を含む) で構成される新しい <xref:Microsoft.Office.Interop.Word.Range> オブジェクトの作成方法を示します。 次に、範囲内のテキストを選択します。

### <a name="to-define-a-range-in-a-document-level-customization"></a>ドキュメント レベルのカスタマイズで範囲を定義するには

1. 文書に範囲を追加するには、<xref:Microsoft.Office.Tools.Word.Document> クラスの <xref:Microsoft.Office.Tools.Word.Document.Range%2A> メソッドに開始文字と終了文字を渡します。 このコード例を使用するには、プロジェクトの `ThisDocument` クラスからコードを実行します。

     [!code-vb[Trin_VstcoreWordAutomation#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#18)]
     [!code-csharp[Trin_VstcoreWordAutomation#18](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#18)]

### <a name="to-define-a-range-by-using-a-vsto-add-in"></a>VSTO アドインを使用して範囲を定義するには

1. 文書に範囲を追加するには、<xref:Microsoft.Office.Interop.Word.Document> クラスの <xref:Microsoft.Office.Interop.Word._Document.Range%2A> メソッドに開始文字と終了文字を渡します。 作業中の文書に範囲を追加するコード例を次に示します。 このコード例を使用するには、プロジェクトの `ThisAddIn` クラスからコードを実行します。

     [!code-vb[Trin_VstcoreWordAutomationAddIn#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#18)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#18](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#18)]

## <a name="select-a-range-in-a-document-level-customization"></a>ドキュメントレベルのカスタマイズで範囲を選択する
 次の例は、<xref:Microsoft.Office.Interop.Word.Range> オブジェクトの <xref:Microsoft.Office.Interop.Word.Range.Select%2A> メソッドを使用して、または <xref:Microsoft.Office.Tools.Word.Document> クラスの <xref:Microsoft.Office.Tools.Word.Document.Content%2A> プロパティを使用して文書全体を選択する方法を示しています。

### <a name="to-select-the-entire-document-as-a-range-by-using-the-select-method"></a>Select メソッドを使用して文書全体を範囲として選択するには

1. 文書全体を含む <xref:Microsoft.Office.Interop.Word.Range> の <xref:Microsoft.Office.Interop.Word.Range.Select%2A> メソッドを使用します。 次のコード例を使用するには、プロジェクトの `ThisDocument` クラスから実行します。

     [!code-vb[Trin_VstcoreWordAutomation#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#19)]
     [!code-csharp[Trin_VstcoreWordAutomation#19](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#19)]

### <a name="to-select-the-entire-document-as-a-range-by-using-the-content-property"></a>Content プロパティを使用して文書全体を範囲として選択するには

1. <xref:Microsoft.Office.Tools.Word.Document.Content%2A> プロパティを使用して、文書全体を含む範囲を定義します。

    [!code-vb[Trin_VstcoreWordAutomation#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#20)]
    [!code-csharp[Trin_VstcoreWordAutomation#20](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#20)]

   また、他のオブジェクトのメソッドとプロパティを使用して範囲を定義することもできます。

### <a name="to-select-a-sentence-in-the-active-document"></a>作業中の文書の文を選択するには

1. <xref:Microsoft.Office.Interop.Word.Sentences> コレクション使用して範囲を設定します。 選択する文のインデックスを使用します。

    [!code-vb[Trin_VstcoreWordAutomation#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#21)]
    [!code-csharp[Trin_VstcoreWordAutomation#21](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#21)]

   文を選択するもう 1 つの方法として、範囲の開始値と終了値を手動で設定する方法があります。

### <a name="to-select-a-sentence-by-manually-setting-the-start-and-end-values"></a>開始値と終了値を手動で設定して文を選択するには

1. 範囲変数を作成します。

     [!code-vb[Trin_VstcoreWordAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#23)]
     [!code-csharp[Trin_VstcoreWordAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#23)]

2. ドキュメント内に少なくとも2つの文があるかどうかを確認し、範囲の *開始* と *終了* の引数を設定して、範囲を選択します。

     [!code-vb[Trin_VstcoreWordAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#24)]
     [!code-csharp[Trin_VstcoreWordAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#24)]

## <a name="select-a-range-by-using-a-vsto-add-in"></a>VSTO アドインを使用して範囲を選択する
 次の例は、<xref:Microsoft.Office.Interop.Word.Range> オブジェクトの <xref:Microsoft.Office.Interop.Word.Range.Select%2A> メソッドを使用して、または <xref:Microsoft.Office.Interop.Word.Document> クラスの <xref:Microsoft.Office.Interop.Word._Document.Content%2A> プロパティを使用して文書全体を選択する方法を示しています。

### <a name="to-select-the-entire-document-as-a-range-by-using-the-select-method"></a>Select メソッドを使用して文書全体を範囲として選択するには

1. 文書全体を含む <xref:Microsoft.Office.Interop.Word.Range> の <xref:Microsoft.Office.Interop.Word.Range.Select%2A> メソッドを使用します。 次のコード例では、作業中の文書の内容を選択します。 このコード例を使用するには、プロジェクトの `ThisAddIn` クラスからコードを実行します。

     [!code-vb[Trin_VstcoreWordAutomationAddIn#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#19)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#19](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#19)]

### <a name="to-select-the-entire-document-as-a-range-by-using-the-content-property"></a>Content プロパティを使用して文書全体を範囲として選択するには

1. <xref:Microsoft.Office.Interop.Word._Document.Content%2A> プロパティを使用して、文書全体を含む範囲を定義します。

    [!code-vb[Trin_VstcoreWordAutomationAddIn#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#20)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#20](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#20)]

   また、他のオブジェクトのメソッドとプロパティを使用して範囲を定義することもできます。

### <a name="to-select-a-sentence-in-the-active-document"></a>作業中の文書の文を選択するには

1. <xref:Microsoft.Office.Interop.Word.Sentences> コレクション使用して範囲を設定します。 選択する文のインデックスを使用します。

    [!code-vb[Trin_VstcoreWordAutomationAddIn#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#21)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#21](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#21)]

   文を選択するもう 1 つの方法として、範囲の開始値と終了値を手動で設定する方法があります。

### <a name="to-select-a-sentence-by-manually-setting-the-start-and-end-values"></a>開始値と終了値を手動で設定して文を選択するには

1. 範囲変数を作成します。

     [!code-vb[Trin_VstcoreWordAutomationAddIn#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#23)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#23](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#23)]

2. ドキュメント内に少なくとも2つの文があるかどうかを確認し、範囲の *開始* と *終了* の引数を設定して、範囲を選択します。

     [!code-vb[Trin_VstcoreWordAutomationAddIn#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#24)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#24](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#24)]

## <a name="see-also"></a>関連項目
- [Word オブジェクトモデルの概要](../vsto/word-object-model-overview.md)
- [方法: プログラムによって文書内の範囲を拡張する](../vsto/how-to-programmatically-extend-ranges-in-documents.md)
- [方法: プログラムによって範囲内の開始文字と終了文字を取得する](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)
- [方法: プログラムによって文書内の範囲を拡張する](../vsto/how-to-programmatically-extend-ranges-in-documents.md)
- [方法: プログラムによって Word 文書の範囲をリセットする](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)
- [方法: プログラムによって文書内の範囲または選択項目を折りたたむ](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)
- [方法: 範囲を作成するときにプログラムによって段落記号を除外する](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)
