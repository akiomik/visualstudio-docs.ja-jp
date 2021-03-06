---
title: 'IDebugContainerField:: EnumFields |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugContainerField::EnumFields
helpviewer_keywords:
- IDebugContainerField::EnumFields method
ms.assetid: 9e5e681b-ad49-4c62-bd95-4afa11d61a57
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4121ecf719ba8422f1ac8d4544a57e81aaf2efde
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99928511"
---
# <a name="idebugcontainerfieldenumfields"></a>IDebugContainerField::EnumFields
コンテナーのフィールドの列挙子を作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumFields( 
   FIELD_KIND         dwKindFilter,
   FIELD_MODIFIERS    dwModifiersFilter,
   LPCOLESTR          pszNameFilter,
   NAME_MATCH         nameMatch,
   IEnumDebugFields** ppEnum
);
```

```csharp
int EnumFields(
   enum_ FIELD_KIND      dwKindFilter,
   enum_ FIELD_MODIFIERS dwModifiersFilter,
   string                pszNameFilter,
   NAME_MATCH            nameMatch,
   out IEnumDebugFields  ppEnum
);
```

## <a name="parameters"></a>パラメーター
`dwKindFilter`\
から列挙するフィールドを選択する [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) 定数の組み合わせ。 フィールドの種類では、クラスやプリミティブなどのストレージ型、またはローカル、パラメーター、または "this" ポインターなどの特定の情報を記述できます。

`dwModifiersFilter`\
から列挙するフィールドを選択する [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) 定数の組み合わせ。 フィールド修飾子には、パブリックまたはプライベートなどのアクセス権限や、virtual、static、final などのストレージ情報を指定できます。

`pszNameFilter`\
から列挙するフィールドの名前。 すべてのフィールドが返される場合は、null 値を指定できます。

`nameMatch`\
から検索で大文字と小文字を区別するかどうかを制御する [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md) 列挙の値。

`ppEnum`\
入出力フィールドの一覧を表す [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) オブジェクトを返します。 フィールドがない場合は、null 値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は、フィールドがない場合は S_OK または S_FALSE を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説
 、、およびの各パラメーターを組み合わせると、 `dwKindFilter` `dwModifiersFilter` たとえば、 `pszNameFilter` "MyMethod" という名前のパブリック仮想メソッドをすべて選択できます。

## <a name="see-also"></a>関連項目
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)
- [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)
- [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md)
