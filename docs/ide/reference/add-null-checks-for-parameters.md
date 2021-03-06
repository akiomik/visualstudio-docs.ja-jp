---
title: すべて (パラメーター) に対して null チェックを追加する
description: Null 許容の、チェックされていないすべてのパラメーターに対して、null かどうかをチェックする if ステートメントを作成し、コードに追加する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 09/17/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 5828a2bb28f7b3085cd5d43c452c520a730b8175
ms.sourcegitcommit: 935e4d9a20928b733e573b6801a6eaff0d0b1b14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "95870964"
---
# <a name="add-null-checks-for-all-parameters"></a>すべてのパラメーターに対して null チェックを追加する 

このリファクタリングは以下に適用されます。 

- C# 

**概要:** Null 許容の、チェックされていないすべてのパラメーターに対して、null かどうかをチェックする `if` ステートメントを作成して追加します。 

**条件:** すべての適用可能なメソッド パラメーターに対して null チェックをすばやく追加する必要があります。

**理由:** 多くのパラメーターに対して null チェックを記述することは、時間がかかり、反復的になることがあります。 このリファクタリングを使用すると、簡単でプログラムがより堅牢になります。  

## <a name="how-to"></a>方法 

1. メソッド内の任意のパラメーターにカーソルを置きます。

2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

   ![クイック アクションとリファクタリング](media/add-null-checks-for-all-parameters.png)
   
3. **[Add null checks for all parameters]\(すべてのパラメーターに対して null チェックを追加する\)** オプションを選択します。

   ![すべてに対して null チェックを追加する](media/add-null-checks-for-all.png) 

## <a name="see-also"></a>関連項目 

- [リファクタリング](../refactoring-in-visual-studio.md)
