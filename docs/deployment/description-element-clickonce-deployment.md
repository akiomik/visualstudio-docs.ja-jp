---
title: '&lt;description &gt; 要素 (ClickOnce 配置) |Microsoft Docs'
description: Description 要素は、コントロールパネルの [シェルのプレゼンス] と [プログラムの追加と削除] 項目を作成するために使用されるアプリケーション情報を識別します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#description
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <description> element [ClickOnce deployment manifest]
ms.assetid: 18f6919e-a3ab-4942-a57d-167fabfac44e
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 8dee33fca027ce47ede8315f7956479ee2394382
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99893088"
---
# <a name="ltdescriptiongt-element-clickonce-deployment"></a>&lt;description &gt; 要素 (ClickOnce 配置)
コントロールパネルの [シェルのプレゼンス] と [ **プログラムの追加と削除** ] 項目を作成するために使用されるアプリケーション情報を識別します。

## <a name="syntax"></a>構文

```xml

      <description 
   publisher 
   product
   suiteName
   supportUrl
/>
```

## <a name="elements-and-attributes"></a>要素と属性
 `description` 要素は必須です。この要素は `urn:schemas-microsoft-com:asm.v1` 名前空間にあります。 子要素は含まれず、次の属性があります。

|属性|説明|
|---------------|-----------------|
|`publisher`|必須。 展開がインストール用に構成されている場合に、Windows の [ **スタート** ] メニューおよび [コントロールパネル] の [ **プログラムの追加と削除** ] 項目で、アイコンの配置に使用される会社名を識別します。|
|`product`|必須。 製品の完全な名前を識別します。 Windows の [ **スタート** ] メニューにインストールされているアイコンのタイトルとして使用されます。|
|`suiteName`|任意。 Windows の [スタート] メニューのフォルダー内のサブフォルダーを識別 `publisher` します。 |
|`supportUrl`|任意。 コントロールパネルの [ **プログラムの追加と削除** ] 項目に表示されるサポート URL を指定します。 この URL へのショートカットは、展開がインストール用に構成されている場合に、Windows の [ **スタート** ] メニューでアプリケーションをサポートするためにも作成されます。|

## <a name="remarks"></a>解説
 Description 要素は、すべての配置構成に必要です。

## <a name="example"></a>例
 次のコード例は、 `description` 配置マニフェストの要素を示してい [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ます。 このコード例は、「 [ClickOnce 配置マニフェスト](../deployment/clickonce-deployment-manifest.md) 」で提供されている、より大きな例の一部です。

```xml
<description
  asmv2:publisher="My Company Name"
  asmv2:product="My Application"
  xmlns="urn:schemas-microsoft-com:asm.v1" />
```

## <a name="see-also"></a>関連項目
- [ClickOnce 配置マニフェスト](../deployment/clickonce-deployment-manifest.md)