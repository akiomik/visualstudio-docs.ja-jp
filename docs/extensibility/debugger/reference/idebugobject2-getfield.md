---
title: 'IDebugObject2:: GetField |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::GetField
helpviewer_keywords:
- IDebugObject2::GetField method
ms.assetid: add6a6b5-e752-47dd-9613-29206ea809b0
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 54f692fa85cfd8fa290a7f5c697a91e0366f8224
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99953462"
---
# <a name="idebugobject2getfield"></a>IDebugObject2::GetField
このオブジェクトの型を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetField(
 IDebugField** ppField
);
```

```csharp
int GetField(
   out IDebugField ppField
);
```

## <a name="parameters"></a>パラメーター
`ppField`\
入出力Null 値でない場合は、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は S_OK を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>解説
 オブジェクトの種類を示すフィールドです。

## <a name="see-also"></a>関連項目
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
