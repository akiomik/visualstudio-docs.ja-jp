---
title: SafeControl 要素 |Microsoft Docs
description: SafeControl 要素に関する情報を取得します。これは、SharePoint サイトの ASPX ページでユーザーがアクセスできるようにセキュリティで保護された ASPX コントロールまたは web パーツを表します。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SafeControl element
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: f08046666ff00d4a0e5489bc78c0c70967774f08
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99889474"
---
# <a name="safecontrol-element"></a>SafeControl 要素
  SharePoint サイトの任意の ASPX ページで任意のユーザーがアクセスできるようにセキュリティで保護されていると指定された ASPX コントロールまたは Web パーツを表します。

## <a name="syntax"></a>構文

```xml
<SafeControl Assembly = "Name of assembly that contains the safe control"
    IsSafe = "true/false"
    IsSafeAgainstScript = "true/false"
    Name = "Name of this safe control entry"
    Namespace = "Namespace of the safe control"
    TypeName = "Type of the safe control" />
```

## <a name="attributes-and-elements"></a>属性と要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

|属性|説明|
|---------------|-----------------|
|**Assembly**|**Xs: string** 属性 (省略可能)。<br /><br /> ASPX コントロールまたは Web パーツが定義されているアセンブリの名前。 既定では、この属性は、アセンブリ名に対して **$SharePoint. プロジェクト** の置き換え可能なパラメーターを使用します。 詳細については、「[置き換え可能パラメーター](../sharepoint/replaceable-parameters.md)」を参照してください。|
|**IsSafe**|**Xs: boolean** 属性 (省略可能)。<br /><br /> ASPX コントロールまたは Web パーツが、信頼されていないユーザーにアクセスすることをセキュリティで保護するかどうかを指定します。|
|**IsSafeAgainstScript**|**Xs: boolean** 属性 (省略可能)。<br /><br /> 信頼されていないユーザーが ASPX コントロールまたは Web パーツのプロパティを表示または編集できるかどうかを指定します。|
|**名前**|**Xs: string** 属性 (省略可能)。<br /><br /> コレクション内のこの安全なコントロールエントリの名前。|
|**Namespace**|**Xs: string** 属性 (省略可能)。<br /><br /> ASPX コントロールまたは Web パーツの名前空間。|
|**TypeName**|**Xs: string** 属性 (省略可能)。<br /><br /> ASPX コントロールまたは Web パーツの型名。|

### <a name="child-elements"></a>子要素
 なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[SafeControls](../sharepoint/safecontrols-element.md)|SharePoint サイトの任意の ASPX ページですべてのユーザーがアクセスできるようにセキュリティで保護されたものとして指定された ASPX コントロールおよび Web パーツのコレクションを表します。|

## <a name="remarks"></a>解説
 安全なコントロールの詳細については、「 [プロジェクト項目でのパッケージ化と配置の情報の提供](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)」を参照してください。

## <a name="element-information"></a>要素情報

|プロパティ|値|
|-|-|
|**Namespace**|http: \/ \/ schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**スキーマ名**|SharePoint プロジェクトアイテムスキーマ|
|**検証ファイル**|ProjectItemModelSchema|
|**空にすることができます**|いいえ|

## <a name="see-also"></a>関連項目
- [SharePoint プロジェクト項目スキーマのリファレンス](../sharepoint/sharepoint-project-item-schema-reference.md)
- [プロジェクト項目でのパッケージ化と配置の情報を提供する](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)
