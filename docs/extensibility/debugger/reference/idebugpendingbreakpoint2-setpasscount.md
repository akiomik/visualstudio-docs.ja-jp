---
title: 'IDebugPendingBreakpoint2:: Setpass Count |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2::SetPassCount
helpviewer_keywords:
- SetPassCount method
- IDebugPendingBreakpoint2::SetPassCount method
ms.assetid: 08ddd328-57eb-42e0-baa9-8424dcd1bf04
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 37aebea3e5dfa9e4693de8ed5b4b6b4b08557a2a
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99893881"
---
# <a name="idebugpendingbreakpoint2setpasscount"></a>IDebugPendingBreakpoint2::SetPassCount
保留中のブレークポイントに関連付けられているパスカウントを設定または変更します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetPassCount( 
   BP_PASSCOUNT bpPassCount
);
```

```csharp
int SetPassCount( 
   BP_PASSCOUNT bpPassCount
);
```

## <a name="parameters"></a>パラメーター
`bpPassCount`\
からパスカウントを格納している [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) 構造体。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。 `E_BP_DELETED`ブレークポイントが削除されている場合は、を返します。

## <a name="remarks"></a>解説
 保留中のブレークポイントに関連付けられていたパスカウントは失われます。 この保留中のブレークポイントからバインドされたすべてのブレークポイントは、パスカウントをパラメーターに設定するために呼び出され `bpPassCount` ます。

## <a name="see-also"></a>関連項目
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)
