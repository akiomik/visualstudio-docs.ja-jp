---
title: 'IDebugMemoryBytes2:: WriteAt |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryBytes2::WriteAt
helpviewer_keywords:
- IDebugMemoryBytes2::WriteAt method
- WriteAt method
ms.assetid: 61cc3704-47fa-4d9b-aa62-bb4585ac8fb1
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8ff77985bca8772d92c3b90e7a727c0077137e24
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99909901"
---
# <a name="idebugmemorybytes2writeat"></a>IDebugMemoryBytes2::WriteAt
指定したアドレスを開始位置として、指定したバイト数のメモリを書き込みます。

## <a name="syntax"></a>構文

```cpp
HRESULT WriteAt( 
   IDebugMemoryContext2* pStartContext,
   DWORD                 dwCount,
   BYTE*                 rgbMemory
);
```

```csharp
int WriteAt(
   IDebugMemoryContext2 pStartContext,
   uint                 dwCount,
   byte[]               rgbMemory
);
```

## <a name="parameters"></a>パラメーター
`pStartContext`\
からバイトの書き込みを開始する位置を指定する [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) オブジェクト。

`dwCount`\
から書き込むバイト数。

`rgbMemory`\
から書き込むバイト。 この配列のサイズは、少なくともバイトであると見なされ `dwCount` ます。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はを返し `S_FALSE` ます。すべてのバイトが書き込まれなかった場合、またはエラーコード (通常は) が返された場合はを返し `E_FAIL` ます

## <a name="remarks"></a>解説
 開始アドレスがこの [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) オブジェクトによって表されるメモリウィンドウ内にない場合、 `E_FAIL` 書き込みの量がメモリ空間に重複する場合でも、書き込みは行われず、のエラーコードが返されます。

## <a name="see-also"></a>関連項目
- [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
