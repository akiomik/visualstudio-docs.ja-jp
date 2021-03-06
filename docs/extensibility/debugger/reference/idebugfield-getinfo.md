---
title: 'IDebugField:: GetInfo |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetInfo
helpviewer_keywords:
- IDebugField::GetInfo method
ms.assetid: 7d508200-89ce-400f-a8ea-f28e7610cb2b
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 21d80f222bdea8a8e17a9b74eefb7885cab0c289
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99869909"
---
# <a name="idebugfieldgetinfo"></a>IDebugField::GetInfo
このメソッドは、フィールドに関する情報を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetInfo( 
   FIELD_INFO_FIELDS dwFields,
   FIELD_INFO* pFieldInfo
);
```

```csharp
int GetInfo(
   enum_FIELD_INFO_FIELDS dwFields,
   FIELD_INFO[] pFieldInfo
);
```

## <a name="parameters"></a>パラメーター
`dwFields`\
から表示する情報を選択する [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) 定数の組み合わせ。 フィールドがシンボルを表す場合は、通常、シンボル名と型になります。

`pFieldInfo`\
入出力指定された [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) 構造体の情報を返します。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)
