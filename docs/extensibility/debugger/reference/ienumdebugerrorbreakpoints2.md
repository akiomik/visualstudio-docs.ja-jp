---
title: IEnumDebugErrorBreakpoints2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugErrorBreakpoints2
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2
ms.assetid: ffdad73d-969a-45ef-9ad1-7f5d3b814018
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 33ff6805537327b29b1d43b1bf4009b431452fc1
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99896975"
---
# <a name="ienumdebugerrorbreakpoints2"></a>IEnumDebugErrorBreakpoints2
このインターフェイスは、保留中のブレークポイントに関連付けられたエラーブレークポイントを列挙します。

## <a name="syntax"></a>構文

```
IEnumDebugErrorBreakpoints2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装側の注意
 デバッグエンジン (DE) は、ブレークポイントのサポートの一部としてこのインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 Visual Studio は [Canbind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md) を呼び出して、バインドできないブレークポイントのリストを表すこのインターフェイスを取得します。また、このインターフェイスを取得するには、バインドされていないブレークポイントの一覧を [取得します](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) 。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表に、のメソッドを示し `IEnumDebugErrorBreakpoints2` ます。

|Method|説明|
|------------|-----------------|
|[次へ](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-next.md)|列挙シーケンス内の指定された数のエラーブレークポイントを取得します。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-skip.md)|列挙シーケンス内の指定された数のエラーブレークポイントをスキップします。|
|[リセット](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-reset.md)|列挙シーケンスを先頭にリセットします。|
|[複製](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-clone.md)|現在の列挙子と同じ列挙状態を含む列挙子を作成します。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-getcount.md)|列挙子内のエラーブレークポイントの数を取得します。|

## <a name="remarks"></a>解説
 このインターフェイスは、バインドできなかったブレークポイントとバインドできなかった理由をそれぞれ記述する [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) インターフェイスのリストを保持します。 Visual Studio は、 `IEnumDebugErrorBreakpoint2` IDE に表示されているブレークポイントを更新するためにインターフェイスを使用します。

## <a name="requirements"></a>要件
 ヘッダー: msdbg. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コアインターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)
- [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)
- [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)
