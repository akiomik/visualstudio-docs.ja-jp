---
title: IDebugAddress |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress
helpviewer_keywords:
- IDebugAddress interface
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: e069a822cc2394769d256c93a1decf01b451b643
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99944857"
---
# <a name="idebugaddress"></a>IDebugAddress
このインターフェイスは、項目のアドレスを表します。 シンボルハンドラーによって返されます。

## <a name="syntax"></a>構文

```
IDebugAddress : IUnknown
```

## <a name="notes-for-implementers"></a>実装側の注意
 シンボルプロバイダーは、オブジェクトのアドレスを表すためにこのインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 多くのインターフェイスの多くのメソッドは、このインターフェイスを返します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 このインターフェイスは、次のメソッドを実装します。

|Method|説明|
|------------|-----------------|
|[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|オブジェクトとその位置を記述する [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 構造体を取得します。|

## <a name="remarks"></a>解説
 シンボルプロバイダーは、特定のスコープ (関数、メソッド、クラスなど) 内のオブジェクトとその位置を表すために、このインターフェイスを返します。 このインターフェイスは、シンボルプロバイダーおよび式エバリュエーターのさまざまなメソッドに返され、そのメソッドに渡されます。 通常、シンボルプロバイダーは、このインターフェイスの内容を解釈する必要がある唯一のエンティティです。

## <a name="requirements"></a>要件
 ヘッダー: sh. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボル プロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)
