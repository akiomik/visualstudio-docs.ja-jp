---
title: 'IDebugClassField:: Enumnesteデ Ums |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumNestedEnums
helpviewer_keywords:
- IDebugClassField::EnumNestedEnums method
ms.assetid: 90fd0cef-9145-4de6-91d4-6c881df39d6e
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b9c283d4b07458368a4ea5f143dc83bf13453302
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99912007"
---
# <a name="idebugclassfieldenumnestedenums"></a>IDebugClassField::EnumNestedEnums
このクラスの入れ子になった列挙子の列挙子を作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumNestedEnums(
    IEnumDebugFields** ppEnum
);
```

```csharp
int EnumNestedEnums(
    out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>パラメーター
`ppEnum`\
入出力入れ子になった列挙型のリストを表す [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) オブジェクトを返します。 入れ子になった列挙型がない場合は、null 値を返します。

## <a name="return-value"></a>戻り値
成功した場合は、S_OK を返すか、入れ子になった列挙子がない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説
列挙体の各要素は、入れ子になった列挙体を記述する [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) オブジェクトです。

クラス内で宣言された列挙体は、入れ子になった列挙体と見なされます。 次に例を示します。

```
class RootClass {
    enum NestedEnum { EnumValue = 0 }
};
```

この `EnumNestedEnums` メソッドは、列挙体を表す1つの[IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)オブジェクトを含む[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)オブジェクトを返し `NestedEnum` ます。

## <a name="see-also"></a>関連項目
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
