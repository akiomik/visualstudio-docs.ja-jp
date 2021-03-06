---
title: '方法: プログラムによって特定の連絡先を検索する'
description: Visual Studio を使用して、Microsoft Outlook で特定の連絡先をプログラムで検索する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- contacts [Office development in Visual Studio], searching
- searching contacts
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: afe17292db70f2d2fdd16e7c7b388343fbf9db9c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99841949"
---
# <a name="how-to-programmatically-search-for-a-specific-contact"></a>方法: プログラムによって特定の連絡先を検索する
  この例では、Outlook の連絡先フォルダーから、姓と名前を指定して特定の連絡先を検索します。 この例では、 **John Evans** という名前の連絡先が連絡先フォルダーに存在することを前提にしています。

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>例
 [!code-csharp[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/CSharp/trin_outlook_rl_searchforcontact/thisaddin.cs#1)]
 [!code-vb[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/VisualBasic/trin_outlook_rl_searchforcontact/thisaddin.vb#1)]

## <a name="see-also"></a>関連項目
- [連絡先アイテムの操作](../vsto/working-with-contact-items.md)
- [VSTO アドインのプログラミングの概要](../vsto/getting-started-programming-vsto-add-ins.md)
