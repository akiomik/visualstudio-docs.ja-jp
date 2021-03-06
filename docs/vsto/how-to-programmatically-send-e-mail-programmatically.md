---
title: '方法: プログラムによって電子メールを送信する'
description: Microsoft Outlook からプログラムによって電子メールを送信するには、Visual Studio を使用します。 この例では、ドメイン名が example.com の連絡先に電子メールメッセージを送信します。
ms.custom: SEO-VS-2020
ms.date: 08/14/2019
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: c2b702d2986315ce32a9ab489db239f2c784f3e6
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99877864"
---
# <a name="how-to-programmatically-send-email"></a>方法: プログラムによって電子メールを送信する
  この例では、電子メールアドレスにドメイン名 **example.com** がある連絡先に電子メールメッセージを送信します。

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="example"></a>例
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]

## <a name="compile-the-code"></a>コードのコンパイル
 この例で必要な要素は次のとおりです。

- メールアドレスにドメイン名が **example.com** されている連絡先。

## <a name="robust-programming"></a>信頼性の高いプログラミング
 ドメイン名 **example.com** を検索するフィルターコードは削除しないでください。 フィルターを削除すると、ソリューションからすべての連絡先に電子メールメッセージが送信されます。

## <a name="see-also"></a>関連項目
- [メールアイテムの操作](../vsto/working-with-mail-items.md)
- [方法: プログラムによって電子メールアイテムを作成する](../vsto/how-to-programmatically-create-an-e-mail-item.md)
- [方法: プログラムによって Outlook の連絡先にアクセスする](../vsto/how-to-programmatically-access-outlook-contacts.md)
- [方法: 電子メールメッセージを受信したときにプログラムによってアクションを実行する](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)
