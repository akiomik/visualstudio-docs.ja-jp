---
title: 'IDebugEngine2:: GetEngineID |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::GetEngineID
helpviewer_keywords:
- IDebugEngine2::GetEngineID
ms.assetid: 0d5674c8-a9b9-4b72-8211-d2d68695775a
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8ec0c294c0d1a1e19942ac86847cad1226041b24
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99878969"
---
# <a name="idebugengine2getengineid"></a>IDebugEngine2::GetEngineID
デバッグエンジン (DE) の GUID を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetEngineID(
    GUID* pguidEngine
);
```

```csharp
int GetEngineID(
    out Guid pguidEngine
);
```

## <a name="parameters"></a>パラメーター
`pguidEngine`\
入出力DE の GUID を返します。

## <a name="return-value"></a>戻り値
成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。

## <a name="remarks"></a>解説
一般的な Guid の例として `guidScriptEng` 、、、などがあり `guidNativeEng` `guidSQLEng` ます。 新しいデバッグエンジンでは、識別用に独自の GUID が作成されます。

## <a name="example"></a>例
次の例は、IDebugEngine2 インターフェイスを実装する単純なオブジェクトに対してこのメソッドを実装する方法を示して `CEngine` います。 [](../../../extensibility/debugger/reference/idebugengine2.md)

```cpp
HRESULT CEngine::GetEngineId(GUID *pguidEngine) {
    if (pguidEngine) {
        // Set pguidEngine to guidBatEng, as defined in the Batdbg.idl file.
        // Other languages would require their own guidDifferentEngine to be
        //defined in the Batdbg.idl file.
        *pguidEngine = guidBatEng;
        return NOERROR; // This is typically S_OK.
    } else {
        return E_INVALIDARG;
    }
}
```

## <a name="see-also"></a>関連項目
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
