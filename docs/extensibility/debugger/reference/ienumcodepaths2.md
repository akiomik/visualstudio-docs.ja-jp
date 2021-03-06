---
title: IEnumCodePaths2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumCodePaths2
helpviewer_keywords:
- IEnumCodePaths2 interface
ms.assetid: 17ec9f9e-dc06-4532-b5db-da52efcc8630
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 69a65488d38fe2562392be152e448369ff081915
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99962159"
---
# <a name="ienumcodepaths2"></a>IEnumCodePaths2
このインターフェイスは、コードパスの一覧を表します。

## <a name="syntax"></a>構文

```
IEnumCodePaths2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装側の注意
 デバッグエンジン (DE) は、コードパスの一覧を表すために、このインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 このインターフェイスを取得するには、 [Enumcodepaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) を呼び出します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表に、のメソッドを示し `IEnumCodePaths2` ます。

|Method|説明|
|------------|-----------------|
|[次へ](../../../extensibility/debugger/reference/ienumcodepaths2-next.md)|列挙シーケンス内の指定された数のコードパスを取得します。|
|[Skip](../../../extensibility/debugger/reference/ienumcodepaths2-skip.md)|列挙シーケンス内の指定された数のコードパスをスキップします。|
|[リセット](../../../extensibility/debugger/reference/ienumcodepaths2-reset.md)|列挙シーケンスを先頭にリセットします。|
|[複製](../../../extensibility/debugger/reference/ienumcodepaths2-clone.md)|現在の列挙子と同じ列挙状態を含む列挙子を作成します。|
|[GetCount](../../../extensibility/debugger/reference/ienumcodepaths2-getcount.md)|列挙子内のコードパスの数を取得します。|

## <a name="remarks"></a>解説
 コードパスは、プログラム内の分岐点または関数呼び出しを表します。 コードパスの一覧は、コードの実行が行われたパスを表します。

## <a name="requirements"></a>要件
 ヘッダー: msdbg. h

 名前空間: VisualStudio。

 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コアインターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
