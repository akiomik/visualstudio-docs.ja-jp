---
title: SccEndBatch 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccEndBatch
helpviewer_keywords:
- SccEndBatch function
ms.assetid: 100e7833-fe0a-45c0-9fca-3e61fd1165b7
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 85d49fcd9920c442aa1736f1fb0f3e46ccd4eba0
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99943050"
---
# <a name="sccendbatch-function"></a>SccEndBatch 関数
この関数は、ソース管理操作のバッチを終了します。 これらのバッチを入れ子にすることはできません。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccEndBatch(void);
```

## <a name="parameters"></a>パラメーター
 [なし] :

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|値|説明|
|-----------|-----------------|
|SCC_OK|操作のバッチが正常に終了しました。|
|SCC_E_UNKNOWNERROR|不特定のエラーです。|

## <a name="remarks"></a>解説
 ソース管理バッチは、複数のプロジェクトまたは複数のコンテキストで同じソース管理操作を実行するために使用されます。 バッチ処理を使用すると、バッチ操作中のユーザーエクスペリエンスから冗長なダイアログボックスを排除できます。 [Sccbeginbatch](../extensibility/sccbeginbatch-function.md)と関数は、 `SccEndBatch` 操作の開始と終了を示すペアとして使用されます。 入れ子にすることはできません。

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [SccBeginBatch](../extensibility/sccbeginbatch-function.md)
