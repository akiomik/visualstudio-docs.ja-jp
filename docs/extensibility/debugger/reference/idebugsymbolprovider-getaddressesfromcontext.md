---
title: 'IDebugSymbolProvider:: Getアドレス Fromcontext |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a9a7b3f9096bbbef1c4de2161c6bb3b6a4c59e4d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99897195"
---
# <a name="idebugsymbolprovidergetaddressesfromcontext"></a>IDebugSymbolProvider::GetAddressesFromContext
このメソッドは、ドキュメントコンテキストをデバッグアドレスの配列にマップします。

## <a name="syntax"></a>構文

```cpp
HRESULT GetAddressesFromContext( 
   IDebugDocumentContext2* pDocContext,
   BOOL                    fStatmentOnly,
   IEnumDebugAddresses**   ppEnumBegAddresses,
   IEnumDebugAddresses**   ppEnumEndAddresses
);
```

```csharp
int GetAddressesFromContext(
   IDebugDocumentContext2  pDocContext,
   bool                    fStatmentOnly,
   out IEnumDebugAddresses ppEnumBegAddresses,
   out IEnumDebugAddresses ppEnumEndAddresses
);
```

## <a name="parameters"></a>パラメーター
`pDocContext`\
からドキュメントコンテキスト。

`fStatmentOnly`\
からTRUE の場合、デバッグアドレスを1つのステートメントに限定します。

`ppEnumBegAddresses`\
入出力このステートメントまたは行に関連付けられている開始デバッグアドレスの列挙子を返します。

`ppEnumEndAddresses`\
入出力このステートメントまたは行に関連付けられている終了デバッグアドレスの [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) 列挙子を返します。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。

## <a name="remarks"></a>解説
 ドキュメントコンテキストは、通常、ソース行の範囲を示します。 このメソッドは、これらの行に関連付けられているデバッグの開始アドレスと終了アドレスを提供します。 一部の言語では、複数の行にまたがるステートメントや、複数のステートメントを含む行が許可されます。 このメソッドには、デバッグアドレスを1つのステートメントに制限するフラグが用意されています。

 テンプレートの場合のように、1つのステートメントに複数のデバッグアドレスを含めることができます。

## <a name="see-also"></a>関連項目
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)
- [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)
