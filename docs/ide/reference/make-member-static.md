---
title: メンバーを静的にする
description: '[クイック アクションとリファクタリング] メニューを使用し、メンバーを静的にする方法について説明します。'
ms.custom: SEO-VS-2020
ms.date: 02/19/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jmartens
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 5478e85d89d4ea44d34e0a5ae9170aaffb3836f7
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99919448"
---
# <a name="make-member-static"></a>メンバーを静的にする

このリファクタリングは以下に適用されます。

- C#

**概要:** メンバーを静的にします。

**条件:** 静的でないメンバーを静的にしたいとき。

**理由:** 静的メンバーを使用すると読みやすさが向上します。特定のコードが分離されていることを把握することで、理解、再読み取り、再利用が容易になります。 

## <a name="how-to"></a>操作方法

1. メンバー名にキャレットを配置します。

2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 (ピリオド) **[クイック アクションとリファクタリング]** メニューがトリガーされます。

   ![メンバーを静的にする](media/make-member-static.png)

3. **[静的にする]** を選択します。

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
