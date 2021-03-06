---
title: IDebugEnumField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEnumField
helpviewer_keywords:
- IDebugEnumField interface
ms.assetid: 42f685bf-0f39-47f4-98b0-6022efe2bf97
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: a67c660ec8457191e688fdd430c3f7a07b5d75c3
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99933324"
---
# <a name="idebugenumfield"></a>IDebugEnumField
このインターフェイスは、列挙型を表します。

## <a name="syntax"></a>構文

```
IDebugEnumField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>実装側の注意
 シンボルプロバイダーは、このインターフェイスを実装して列挙体を表します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 [Getkind](../../../extensibility/debugger/reference/idebugfield-getkind.md)がを返す場合は、 [QueryInterface](/cpp/atl/queryinterface)を使用して、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイスからこのインターフェイスを取得し `FIELD_TYPE_ENUM` ます。

## <a name="methods-in-vtable-order"></a>VTable の順序でのメソッド
 インターフェイスおよびインターフェイスのメソッドに加え `IDebugField` て `IDebugContainerField` 、このインターフェイスは次のメソッドを実装します。

|Method|説明|
|------------|-----------------|
|[GetUnderlyingSymbol](../../../extensibility/debugger/reference/idebugenumfield-getunderlyingsymbol.md)|この列挙型の名前を記述する [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) を返します。|
|[GetStringFromValue](../../../extensibility/debugger/reference/idebugenumfield-getstringfromvalue.md)|指定された値に関連付けられている列挙定数の名前を返します。|
|[GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)|指定した列挙定数名に関連付けられている値を返します。|
|[GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md)|指定した列挙定数名に関連付けられている値を返しますが、大文字と小文字は区別しません。|

## <a name="remarks"></a>解説
 これは、 [バインド](../../../extensibility/debugger/reference/idebugbinder-bind.md)がある場所に実際にバインドされている、基になるシンボルです。

## <a name="requirements"></a>要件
 ヘッダー: sh. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボル プロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [束縛](../../../extensibility/debugger/reference/idebugbinder-bind.md)
