---
title: IDebugProgramProvider2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramProvider2
helpviewer_keywords:
- IDebugProgramProvider2 interface
ms.assetid: a9ec7b3e-a59c-4069-b2ee-6f45916eeb78
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 788c4add42b70107ea2960ae5682a2e2cc815d59
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99959624"
---
# <a name="idebugprogramprovider2"></a>IDebugProgramProvider2
この登録済みインターフェイスにより、セッションデバッグマネージャー (SDM) は、 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md) インターフェイスを通じて "公開" されたプログラムに関する情報を取得できます。

## <a name="syntax"></a>構文

```
IDebugProgramProvider2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装側の注意
デバッグエンジン (DE) は、デバッグ中のプログラムに関する情報を提供するために、このインターフェイスを実装します。 このインターフェイスは、「 `metricProgramProvider` [デバッグ用の SDK ヘルパー](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)」で説明されているように、メトリックを使用してレジストリの DE セクションに登録されます。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
`CoCreateInstance` `CLSID` レジストリから取得したプログラムプロバイダーのを使用して、COM の関数を呼び出します。 例を参照してください。

## <a name="methods-in-vtable-order"></a>Vtable の順序でのメソッド

|Method|説明|
|------------|-----------------|
|[GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)|さまざまな方法でフィルター処理された、実行中のプログラムに関する情報を取得します。|
|[GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)|特定のプロセス ID を指定して、プログラムノードを取得します。|
|[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)|特定の種類のプロセスに関連付けられているプロバイダーイベントを監視するためのコールバックを確立します。|
|[SetLocale](../../../extensibility/debugger/reference/idebugprogramprovider2-setlocale.md)|DE によって必要とされる言語固有のリソースのロケールを設定します。|

## <a name="remarks"></a>解説
通常、プロセスでは、このインターフェイスを使用して、そのプロセスで実行されているプログラムに関する情報を確認します。

## <a name="requirements"></a>要件
ヘッダー: msdbg. h

名前空間: VisualStudio。

アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="example"></a>例

```cpp
IDebugProgramProvider2 *GetProgramProvider(GUID *pDebugEngineGuid)
{
    // This is typically defined globally. For this example, it is
    // defined here.
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";
    IDebugProgramProvider2 *pProvider = NULL;
    if (pDebugEngineGuid != NULL) {
        CLSID clsidProvider = { 0 };
        ::GetMetric(NULL,
                    metrictypeEngine,
                    *pDebugEngineGuid,
                    metricProgramProvider,
                    &clsidProvider,
                    strRegistrationRoot);
        if (!IsEqualGUID(clsidProvider,GUID_NULL)) {
            CComPtr<IDebugProgramProvider2> spProgramProvider;
            spProgramProvider.CoCreateInstance(clsidProvider);
            if (spProgramProvider != NULL) {
                pProvider = spProgramProvider.Detach();
            }
        }
    }
    return(pProvider);
}
```

## <a name="see-also"></a>関連項目
- [コアインターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)
- [デバッグ用の SDK ヘルパー](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
