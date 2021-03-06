---
title: IEnumDebugFields |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFields
helpviewer_keywords:
- IEnumDebugFields interface
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: cce45c926700779906881bc4a4607b05f0732be3
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99956400"
---
# <a name="ienumdebugfields"></a>IEnumDebugFields
このインターフェイスは、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) インターフェイスを実装するオブジェクトのコレクションを表します。

## <a name="syntax"></a>構文

```
IEnumDebugFields : IUnknown
```

## <a name="notes-for-implementers"></a>実装側の注意
 このインターフェイスは、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) インターフェイスを実装するオブジェクトのセットを提供するために、シンボルプロバイダーによって実装されます。 これは、 [GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md) メソッドが存在するため、標準の COM 列挙ではないことに注意してください。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 このインターフェイスは、 [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md) および [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)によって返されます。

## <a name="methods-in-vtable-order"></a>Vtable の順序でのメソッド
 このインターフェイスは、次のメソッドを実装します。

|Method|説明|
|------------|-----------------|
|[次へ](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|列挙体から次の [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) オブジェクトのセットを取得します。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|指定された数のエントリをスキップします。|
|[リセット](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|列挙体を最初のエントリにリセットします。|
|[複製](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|現在の列挙体のコピーを取得します。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|列挙体のエントリ数を取得します。|

## <a name="remarks"></a>解説

## <a name="requirements"></a>必要条件
 ヘッダー: sh. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボル プロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)
- [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)
