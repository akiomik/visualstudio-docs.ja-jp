---
title: SupportsLanguageDropDown 要素 (Visual Studio テンプレート)
titleSuffix: ''
description: SupportsLanguageDropDown 要素について、および Web 項目テンプレートが複数の言語で同一であるかどうか、および言語オプションが有効になっているかどうかをどのように指定するかについて説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SupportsLanguageDropDown
helpviewer_keywords:
- SupportsLanguageDropDown element [Visual Studio Templates]
- <SupportsLanguageDropDown> element [Visual Studio Templates]
ms.assetid: 641197d5-f724-4c06-bc47-2e22dad3fbfb
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 79141361253df4e1ccaf29ff15332d534ceade84
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99898092"
---
# <a name="supportslanguagedropdown-element-visual-studio-templates"></a>SupportsLanguageDropDown 要素 (Visual Studio テンプレート)

Web 項目テンプレートが複数の言語で同一であるかどうか、および [**新しい項目の追加**] ダイアログボックスで [**言語**] オプションが有効になっているかどうかを指定します。

 \<VSTemplate> \<TemplateData>
 \<SupportsLanguageDropDown>

## <a name="syntax"></a>構文

```xml
<SupportsLanguageDropDown> true/false </SupportsLanguageDropDown>
```

## <a name="attributes-and-elements"></a>属性および要素

 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

 なし。

### <a name="child-elements"></a>子要素

 なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必須の要素です。<br /><br /> テンプレートをカテゴリに分類し、 **[新しいプロジェクト]** ダイアログ ボックス、または **[新しい項目の追加]** ダイアログ ボックスでどのように表示させるかを定義します。|

## <a name="text-value"></a>テキスト値

 テキスト値が必要です。

 テキストはまたはのいずれかである必要があり `true` `false` ます。 [**新しい項目の追加**] ダイアログボックスで [**言語**] オプションを使用できるかどうかを示します。

## <a name="remarks"></a>解説

 `SupportsLanguageDropDown` は省略可能な要素です。 既定値は `false` です。

 `SupportsLanguageDropDown`要素は、Web 項目テンプレートでのみ使用できます。

 この要素の値がに設定されている場合、 `true` すべてのプログラミング言語で項目テンプレートが同じになり、[**新しい項目の追加**] ダイアログボックスで [**言語**] オプションが有効になります。 このオプションを使用すると、テンプレートから作成する新しい項目のプログラミング言語を選択できます。

## <a name="example"></a>例

 次の例では、 **言語** ドロップダウンオプションを表示するように指定します。

```xml
<VSTemplate Version="3.0.0" Type="Project"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>
    <TemplateData>
        <Name>MyWebProjecStarterKit</Name>
        <Description>A simple Web template</Description>
        <Icon>icon.ico</Icon>
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        <DefaultName>WebSite</DefaultName>
        <SupportsLanguageDropDown>true</SupportsLanguageDropDown>
    </TemplateData>
    <TemplateContent>
        <Project File="WebApplication.webproj">
            <ProjectItem>icon.ico</ProjectItem>
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>
            <ProjectItem>Default.aspx.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>関連項目

- [Visual Studio テンプレートスキーマリファレンス](../extensibility/visual-studio-template-schema-reference.md)
- [プロジェクトテンプレートと項目テンプレートの作成](../ide/creating-project-and-item-templates.md)
