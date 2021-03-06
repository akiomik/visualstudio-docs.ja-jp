---
title: IDebugGenericParamField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugGenericParamField interface
ms.assetid: ba24f499-5ba7-4c67-83e6-923229b52327
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 5ad01730f7f1d1e8e155cd1df44f75fbf88c73a4
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99838644"
---
# <a name="idebuggenericparamfield"></a>IDebugGenericParamField
マネージコードのジェネリック型のパラメーターを表します。

## <a name="syntax"></a>構文

```
IDebugGenericParamField : IDebugField
```

## <a name="notes-for-implementers"></a>実装側の注意
 ジェネリックのサポートに使用されます。

## <a name="methods"></a>メソッド
 このインターフェイスは、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) インターフェイスのメソッドに加えて、次のメソッドを実装します。

|Method|説明|
|------------|-----------------|
|[ConstraintCount](../../../extensibility/debugger/reference/idebuggenericparamfield-constraintcount.md)|このジェネリックパラメーターに関連付けられている制約の数を返します。|
|[GetConstraints](../../../extensibility/debugger/reference/idebuggenericparamfield-getconstraints.md)|このジェネリックパラメーターに関連付けられている制約を取得します。|
|[GetFlags](../../../extensibility/debugger/reference/idebuggenericparamfield-getflags.md)|このジェネリックパラメーターのフラグを取得します。|
|[GetIndex](../../../extensibility/debugger/reference/idebuggenericparamfield-getindex.md)|このジェネリックパラメーターのインデックスを取得します。|
|[GetNameOfFormalParam](../../../extensibility/debugger/reference/idebuggenericparamfield-getnameofformalparam.md)|このジェネリックパラメーターの名前を取得します。|
|[GetOwner](../../../extensibility/debugger/reference/idebuggenericparamfield-getowner.md)|このジェネリックパラメーターの型またはメソッドの所有者を取得します。|

## <a name="requirements"></a>要件
 ヘッダー: Sh. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll
