---
title: IDebugCustomAttributeQuery2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttributeQuery2
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
- IDebugCustomAttributeQuery2 interface
ms.assetid: 7cfa23e4-a05a-47a3-af6c-bd40c655014b
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 331fba87de68b3cf5e135e0b6f633874236bec38
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99842408"
---
# <a name="idebugcustomattributequery2"></a>IDebugCustomAttributeQuery2
このフィールドにカスタム属性が存在するかどうかを判断し、存在する場合は属性情報を返します。

## <a name="syntax"></a>構文

```
IDebugCustomAttributeQuery2 : IDebugCustomAttributeQuery
```

## <a name="notes-for-implementers"></a>実装側の注意
 シンボルプロバイダーは、カスタム属性をサポートするために、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) を実装する同じオブジェクトにこのインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 [QueryInterface](/cpp/atl/queryinterface)を使用して、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイスからこのインターフェイスを取得します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、 **IDebugCustomAttributeQuery** インターフェイスのメソッドを示しています。

|Method|説明|
|------------|-----------------|
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md)|カスタム属性が名前によって存在するかどうかを判断します。|
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery2-getcustomattributebyname.md)|指定されたカスタム属性の属性情報を取得します。|

 **IDebugCustomAttributeQuery** メソッドに加えて、には `IDebugCustomAttributeQuery2` 次のメソッドが実装されています。

|Method|説明|
|------------|-----------------|
|[EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)|このフィールドにアタッチされているすべてのカスタム属性の列挙子を取得します。|

## <a name="remarks"></a>解説
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)メソッドは、このフィールドに対して定義されているすべてのカスタム属性の列挙子を返すことができます。

## <a name="requirements"></a>要件
 ヘッダー: sh. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボル プロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)
