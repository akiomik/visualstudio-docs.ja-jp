---
title: 'IDebugProperty2:: SetValueAsString |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::SetValueAsString
helpviewer_keywords:
- IDebugProperty2::SetValueAsString
ms.assetid: 9e6a5054-41b7-4223-b509-b93689d366a5
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 812bb7807a8b739d09cb15c6f03e58732fde20a4
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99916027"
---
# <a name="idebugproperty2setvalueasstring"></a>IDebugProperty2::SetValueAsString
指定された文字列からプロパティの値を設定します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetValueAsString ( 
   LPCOLESTR pszValue,
   UINT      nRadix,
   DWORD     dwTimeout
);
```

```csharp
int SetValueAsString ( 
   string pszValue,
   uint   nRadix,
   uint   dwTimeout
);
```

## <a name="parameters"></a>パラメーター
`pszValue`\
から設定する値を格納している文字列。

`nRadix`\
から数値情報の解釈に使用される基数。 0を指定すると、基数を自動的に決定できます。

`dwTimeout`\
からこのメソッドから制御が戻るまでに待機する最大時間をミリ秒単位で指定します。 `INFINITE`無期限に待機するには、を使用します。

## <a name="return-value"></a>戻り値
 成功した場合は、を返します。それ以外の場合は `S_OK` エラーコードを返します。 次の表に、その他の使用可能な値を示します。

|値|説明|
|-----------|-----------------|
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|文字列をプロパティ値に変換できなかったか、プロパティ値を設定できませんでした。|
|`E_SETVALUE_VALUE_IS_READONLY`|このプロパティは読み取り専用です。|

## <a name="see-also"></a>関連項目
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
