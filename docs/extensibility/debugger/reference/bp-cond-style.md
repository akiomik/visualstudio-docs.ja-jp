---
title: BP_COND_STYLE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_COND_STYLE
helpviewer_keywords:
- BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4f98f02e7e756a744d8042a9955802165065d54d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99862163"
---
# <a name="bp_cond_style"></a>BP_COND_STYLE
保留中のブレークポイントとバインドされたブレークポイントのブレークポイントの条件スタイルを指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
typedef DWORD BP_COND_STYLE;
```

```csharp
public enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
```

## <a name="fields"></a>フィールド
`BP_COND_NONE`\
ブレークポイントの位置に達したときにブレークポイントを発生させます。 ブレークポイント条件が指定されていません。

`BP_COND_WHEN_TRUE`\
ブレークポイントに関連付けられている条件式がと評価された場合にのみ、ブレークポイントを発生させ `true` ます。

`BP_COND_WHEN_CHANGED`\
ブレークポイントに関連付けられている条件式の値が以前の評価から変更された場合にのみ、ブレークポイントを発生させます。

## <a name="remarks"></a>解説
`styleCondition` [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)構造体のメンバーに使用されます。

## <a name="requirements"></a>要件
ヘッダー: msdbg. h

名前空間: VisualStudio。

アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)
