---
title: 'IDebugFunctionObject:: CreateObjectNoConstructor |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreateObjectNoConstructor
helpviewer_keywords:
- IDebugFunctionObject::CreateObjectNoConstructor method
ms.assetid: 4e2bd6d5-f4bd-4c10-a998-3db451c9a0c8
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2c47f51fb0ddc47218b11fe5673e0ede8362ff89
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99921074"
---
# <a name="idebugfunctionobjectcreateobjectnoconstructor"></a>IDebugFunctionObject::CreateObjectNoConstructor
コンストラクターを持たないオブジェクトを作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT CreateObjectNoConstructor( 
   IDebugField*   pClassObject,
   IDebugObject** ppObject
);
```

```csharp
int CreateObjectNoConstructor(
   IDebugField      pClassField,
   out IDebugObject ppObject
);
```

## <a name="parameters"></a>パラメーター
`pClassObject`\
から作成するオブジェクトの型を表す [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) オブジェクト。

`ppObject`\
入出力新しく作成されたオブジェクトを表す [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) を返します。

## <a name="return-value"></a>戻り値
 成功した場合は S_OK を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>解説
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)インターフェイスによって表される関数のパラメーターである構造体または複合型のインスタンスを表すオブジェクトを作成するには、このメソッドを呼び出します。

 オブジェクトパラメーターにコンストラクターが必要な場合は、 [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md) メソッドを呼び出します。

## <a name="see-also"></a>関連項目
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)
- [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)
