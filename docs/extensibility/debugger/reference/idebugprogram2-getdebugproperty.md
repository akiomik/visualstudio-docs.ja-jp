---
title: 'IDebugProgram2:: GetDebugProperty |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetDebugProperty
helpviewer_keywords:
- IDebugProgram2::GetDebugProperty
ms.assetid: d194224e-f0e6-46ab-85d4-9e2639e28946
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: eb0bb520d3a821d777d5deaeaa200c4b7e526f65
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99911965"
---
# <a name="idebugprogram2getdebugproperty"></a>IDebugProgram2::GetDebugProperty
プログラムのプロパティを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetDebugProperty( 
   IDebugProperty2** ppProperty
);
```

```csharp
int GetDebugProperty( 
   out IDebugProperty2 ppProperty
);
```

## <a name="parameters"></a>パラメーター
`ppProperty`\
入出力プログラムのプロパティを表す [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。

## <a name="remarks"></a>解説
 このメソッドによって返されるプロパティは、プログラムに固有のプロパティです。 プログラムが複数のプロパティを返す必要がある場合、このメソッドによって返される [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) オブジェクトは追加プロパティのコンテナーであり、 [enumchildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) メソッドを呼び出すと、すべてのプロパティの一覧が返されます。

 プログラムは、インターフェイスを通じて記述できる追加プロパティの数と種類を公開する場合があり `IDebugProperty2` ます。 IDE では、汎用プロパティブラウザーのユーザーインターフェイスを使用して、追加のプログラムプロパティを表示できます。

## <a name="see-also"></a>関連項目
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)
