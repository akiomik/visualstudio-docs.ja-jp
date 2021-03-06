---
title: 'IDebugCoreServer3:: CreateInstanceInServer |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::CreateInstanceInServer
helpviewer_keywords:
- IDebugCoreServer3::CreateInstanceInServer
ms.assetid: 76f36bae-f6ab-413c-a8a9-8808bfeba05b
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b76c37d767ae38a33d537a96f9ad8f7087503ed2
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99909960"
---
# <a name="idebugcoreserver3createinstanceinserver"></a>IDebugCoreServer3::CreateInstanceInServer
サーバー上にデバッグエンジンのインスタンスを作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT CreateInstanceInServer(
   LPCWSTR  szDll,
   WORD     wLangId,
   REFCLSID clsidObject,
   REFIID   riid,
   void**   ppvObject
);
```

```csharp
int CreateInstanceInServer(
   string     szDll,
   ushort     wLangID,
   ref Guid   clsidObject,
   ref Guid   riid,
   out IntPtr ppvObject
);
```

## <a name="parameters"></a>パラメーター
`szDll`\
からパラメーターで指定された CLSID を実装する dll へのパス `clsidObject` 。 がの場合 `NULL` 、COM の `CoCreateInstance` 関数が呼び出されます。

`wLangId`\
からデバッグエンジンのロケール。 [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)メソッドを呼び出さない場合は、0を指定できます。

`clsidObject`\
から作成するデバッグエンジンの CLSID。

`riid`\
からクラスオブジェクトから取得する特定のインターフェイスのインターフェイス ID。

`ppvObject`\
[出力] `IUnknown` インスタンス化されたオブジェクトからのインターフェイス。 このオブジェクトを目的のインターフェイスにキャストまたはマーシャリングします。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)
- [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)
