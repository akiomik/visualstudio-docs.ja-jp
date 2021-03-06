---
title: '方法: プログラムによってテキストファイルをブックとして開く'
description: Visual Studio を使用して、Microsoft Excel ブックとしてテキストファイルをプログラムで開く方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 47582718128fc9818bb42571e3f33c0190a32d9e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99888746"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>方法: プログラムによってテキストファイルをブックとして開く
  テキストファイルをブックとして開くことができます。 開くテキストファイルの名前を渡す必要があります。 解析を開始する行番号やファイル内のデータの列の形式など、いくつかの省略可能なパラメーターを指定できます。

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>例
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]

## <a name="compile-the-code"></a>コードのコンパイル
 この例では、次のコンポーネントが必要です。

- 少なくとも `Test.txt` 3 行のテキストを含むという名前のコンマ区切りのテキストファイル。

- `Test.txt`ドライブ C に格納するテキストファイル。

## <a name="see-also"></a>関連項目
- [ブックの操作](../vsto/working-with-workbooks.md)
- [方法: プログラムによってブックを開く](../vsto/how-to-programmatically-open-workbooks.md)
- [方法: プログラムによって新しいブックを作成する](../vsto/how-to-programmatically-create-new-workbooks.md)
- [方法: プログラムによってブックを保存する](../vsto/how-to-programmatically-save-workbooks.md)
- [方法: プログラムによってブックを閉じる](../vsto/how-to-programmatically-close-workbooks.md)
- [Office ソリューションの省略可能なパラメーター](../vsto/optional-parameters-in-office-solutions.md)
