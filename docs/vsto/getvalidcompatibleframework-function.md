---
title: Getvalid互換フレームワーク関数
description: Getvalid互換フレームワーク API が Office インフラストラクチャをサポートする方法について説明します。コードから直接使用するためのものではありません。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: b089f954c59219461c8e267ee6e88e47015fc794
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99860621"
---
# <a name="getvalidcompatibleframework-function"></a>Getvalid互換フレームワーク関数
  この API は Office インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```csharp
HRESULT WINAPI GetValidCompatibleFramework(
    LPCWSTR lpwszCompatibleFrameworksXML,
    BSTR* pbstrValidFrameworkTag
);
```

### <a name="parameters"></a>パラメーター

|パラメーター|Description|
|---------------|-----------------|
|*lpwszCompatibleFrameworksXML*|使用しないでください。|
|*pbstrValidFrameworkTag*|使用しないでください。|

## <a name="return-value"></a>戻り値
 関数が成功した場合は、 **S_OK** を返します。 関数が失敗した場合は、エラーコードを返します。
