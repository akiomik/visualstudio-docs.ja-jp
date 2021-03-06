---
title: BP_LOCATION_DATA_STRING |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_LOCATION_DATA_STRING
helpviewer_keywords:
- BP_LOCATION_DATA_STRING structure
ms.assetid: 445d6f3f-95b0-47ac-85e2-51b778240687
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
ms.openlocfilehash: ce47dc9a3fac9ee56b801e4d2681668f4467f532
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99902163"
---
# <a name="bp_location_data_string"></a>BP_LOCATION_DATA_STRING
統合開発環境 (IDE: integrated development environment) からユーザーが入力できる文字列に基づいてデータブレークポイントを設定するために使用されます。

## <a name="syntax"></a>構文

```cpp
typedef struct _BP_LOCATION_DATA_STRING {
    IDebugThread2* pThread;
    BSTR           bstrContext;
    BSTR           bstrDataExpr;
    DWORD          dwNumElements;
} BP_LOCATION_DATA_STRING;
```

## <a name="members"></a>メンバー
`pThread`\
ブレークポイントが発生したスレッドを表す [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) オブジェクト。

`bstrContext`\
コード内のブレークポイントのコンテキスト。通常は、呼び出し履歴に表示されるメソッドまたは関数の名前です。

`bstrDataExpr`\
ブレークポイントを設定するためにユーザーが入力するデータ文字列。

`dwNumElements`\
ブレークポイントが発生するデータ文字列内の要素の数。

## <a name="remarks"></a>解説
この構造体は、共用体の一部として [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 構造体のメンバーになります。

## <a name="requirements"></a>要件
ヘッダー: msdbg. h

名前空間: VisualStudio。

アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
