---
title: CODE_PATH |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CODE_PATH
helpviewer_keywords:
- CODE_PATH structure
ms.assetid: 2d4b2890-4c9d-47e1-83c0-df9c6436427f
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d4bba942b0740fba98e88a3cddcecfcd43d7d215
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99900310"
---
# <a name="code_path"></a>CODE_PATH
メソッドまたは関数呼び出しを記述します。

## <a name="syntax"></a>構文

```cpp
typedef struct tagCODE_PATH { 
    BSTR                bstrName;
    IDebugCodeContext2* pCode;
} CODE_PATH;
```

```csharp
public struct CODE_PATH {
    public string            bstrName;
    public IDebugCodeContext pCode;
}
```

## <a name="members"></a>メンバー
`bstrName`\
コードパスの名前。

`pCode`\
関数にステップインするコード内の位置を識別する [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) オブジェクト。

## <a name="remarks"></a>解説
この構造体は、関数へのステップインを実装するために使用されます。 [Enumcodepaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) は、デバッグ中のプログラムの現在の場所からのすべての呼び出しを返します。 この構造体は、このような呼び出しの1つを表します。

## <a name="requirements"></a>要件
ヘッダー: msdbg. h

名前空間: VisualStudio。

アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
- [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)
