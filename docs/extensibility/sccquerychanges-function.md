---
title: SccQueryChanges 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccQueryChanges
helpviewer_keywords:
- SccQueryChanges function
ms.assetid: 4cd58eb3-6952-49b1-9620-8682e3eaa604
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: fd69183b290fa194d87dff79d69596dd65ec19ba
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99836723"
---
# <a name="sccquerychanges-function"></a>SccQueryChanges 関数
この関数は、指定されたファイルのリストを列挙し、コールバック関数を介して各ファイルの名前変更に関する情報を提供します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccQueryChanges(
   LPVOID           pContext,
   LONG             nFiles,
   LPCSTR*          lpFileNames,
   QUERYCHANGESFUNC pfnCallback,
   LPVOID           pvCallerData
);
```

#### <a name="parameters"></a>パラメーター
 pContext

からソース管理プラグインのコンテキストポインター。

 nFiles

から配列内のファイルの数 `lpFileNames` 。

 lpFileNames 名

から情報を取得するファイル名の配列。

 pfnCallback

からリスト内の各ファイル名に対して呼び出すコールバック関数 (詳細については、「 [queryの](../extensibility/querychangesfunc.md) 内容」を参照してください)。

 pvCallerData

からコールバック関数に変更されずに渡される値。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|値|説明|
|-----------|-----------------|
|SCC_OK|クエリ処理が正常に完了しました。|
|SCC_E_PROJNOTOPEN|プロジェクトがソース管理で開かれていません。|
|SCC_E_ACCESSFAILURE|ネットワークまたは競合の問題が原因で、ソース管理システムへのアクセスで問題が発生しました。|
|SCC_E_NONSPECIFICERROR|指定されていないか、一般的なエラーが発生しました。|

## <a name="remarks"></a>解説
 に対して照会される変更は、名前空間に対して行われます。具体的には、ファイルの名前変更、追加、および削除です。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)
- [エラー コード](../extensibility/error-codes.md)
