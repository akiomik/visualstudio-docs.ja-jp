---
title: IDebugPortEx2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEx2
helpviewer_keywords:
- IDebugPortEx2 interface
ms.assetid: 144724d0-38ee-4c9b-87ca-8a504371182b
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: b2ff055f730d193b5294b98129e073a21428f8ee
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99919900"
---
# <a name="idebugportex2"></a>IDebugPortEx2
このインターフェイスを使用すると、セッションデバッグマネージャー (SDM) は、ポートで実行されているプログラムとプロセスを制御できます。

## <a name="syntax"></a>構文

```
IDebugPortEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装側の注意
 カスタムポートサプライヤーは、 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)を実装するのと同じオブジェクトにこのインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 SDM は、インターフェイスの [QueryInterface](/cpp/atl/queryinterface) を呼び出して、 `IDebugPort2` このインターフェイスを取得します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表に、のメソッドを示し `IDebugPortEx2` ます。

|Method|説明|
|------------|-----------------|
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)|実行可能ファイルを起動します。|
|[ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)|プロセスの実行を再開します。|
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugportex2-canterminateprocess.md)|プロセスを終了できるかどうかを判断します。|
|[TerminateProcess](../../../extensibility/debugger/reference/idebugportex2-terminateprocess.md)|プロセスを終了します。|
|[GetPortProcessId](../../../extensibility/debugger/reference/idebugportex2-getportprocessid.md)|ポート自体のプロセス ID を取得します。|
|[GetProgram](../../../extensibility/debugger/reference/idebugportex2-getprogram.md)|プログラムノードに関連付けられているプログラムを取得します。|

## <a name="remarks"></a>解説
 このインターフェイスは、通常、SDM とカスタムポート供給業者の間でプライベートです。

 必要に応じて、デバッグエンジン (DE) は、 [launchsuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)に渡された[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)インターフェイスでこのインターフェイスを検索し、 [launchsuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)を使用してプログラムを起動することができます。 ただし、これは必須ではありません。また、DE は、要求プログラムを起動するために必要な操作を行うことができます。

## <a name="requirements"></a>要件
 ヘッダー: portpriv. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コアインターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
