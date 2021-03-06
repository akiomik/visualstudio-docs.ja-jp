---
title: DUMPTYPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DUMPTYPE
helpviewer_keywords:
- DUMPTYPE enumeration
ms.assetid: ea8160db-8732-4056-a1d7-892ef72da71e
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 99e7e5a9e092118eb40501e6f2ba3cc580cf7cc7
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99953735"
---
# <a name="dumptype"></a>DUMPTYPE
ダンプするプログラムの状態 (スレッドの実行、スタックフレーム、現在の命令アドレスなど) の量を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_DUMPTYPE {
    DUMP_MINIDUMP = 0,
    DUMP_FULLDUMP = 1
};
typedef DWORD DUMPTYPE;
```

```csharp
public enum enum_DUMPTYPE {
    DUMP_MINIDUMP = 0,
    DUMP_FULLDUMP = 1
};
```

## <a name="fields"></a>フィールド
`DUMP_MINIDUMP`\
小さいコンパクトなダンプを指定します。

`DUMP_FULLDUMP`\
大きな完全なダンプを指定します。

## <a name="remarks"></a>解説
[WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md)メソッドに引数として渡されます。

## <a name="requirements"></a>要件
ヘッダー: msdbg. h

名前空間: VisualStudio。

アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md)
