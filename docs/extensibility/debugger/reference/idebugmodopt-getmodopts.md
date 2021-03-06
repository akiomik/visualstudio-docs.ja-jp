---
title: 'IDebugModOpt:: GetModOpts |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugModOpt::GetModOpts
- GetModOpts
ms.assetid: cb513fa9-d521-4a65-b968-f55f53a368df
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 78ddcaa6a062b844c3f60c04f7a08aa673c69f67
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99941789"
---
# <a name="idebugmodoptgetmodopts"></a>IDebugModOpt::GetModOpts
省略可能な修飾子のリストを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetModOpts(
   ULONG  celt,
   BSTR*  rgelt,
   ULONG* pceltFetched
);
```

```csharp
int GetModOpts(
   uint         celt,
   out string[] rgelt,
   ref uint     pceltFetched
);
```

## <a name="parameters"></a>パラメーター
`celt`\
から返される要素の数。

`rgelt`\
入出力オプションを格納している配列を返します。

`pceltFetched`\
[入力、出力]配列で返される要素の数 `rgelt` 。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)
