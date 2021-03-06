---
title: 'IDebugObject:: GetManagedDebugObject |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8fec87a2294524c915116929f2ac2c991170c5ed
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99920877"
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
デバッグエンジンのアドレス空間にマネージオブジェクトのコピーを作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetManagedDebugObject( 
   IDebugManagedObject** ppObject
);
```

```csharp
int GetManagedDebugObject(
   out IDebugManagedObject ppObject
);
```

## <a name="parameters"></a>パラメーター
`ppObject`\
入出力新しく作成されたマネージオブジェクトを表す [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は S_OK を返します。それ以外の場合は、エラーコードを返します。 この [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) がマネージ値クラスのインスタンスを表していない場合は E_FAIL を返します。

## <a name="remarks"></a>解説
 この [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) オブジェクトは、インスタンスなどのマネージ値クラスのインスタンスを表す必要があり `System.Decimal` ます。 ローカルコピーを用意することで、 [Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) 呼び出しのオーバーヘッドが解消されます。

## <a name="see-also"></a>関連項目
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)
