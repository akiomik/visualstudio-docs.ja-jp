---
title: Hidden 要素 (Visual Studio テンプレート) |Microsoft Docs
description: Hidden 要素について、また、[新しいプロジェクト] ダイアログボックスまたは [新しい項目の追加] ダイアログボックスにテンプレートを表示するかどうかを指定する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 04/17/2019
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Hidden
helpviewer_keywords:
- Hidden element [Visual Studio project template]
ms.assetid: f37406b0-52e7-4f2c-aacf-bc8d7a4117b3
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 476e187a0e4c3cefde7f09124fbbd21374e2175c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99945696"
---
# <a name="hidden-element-visual-studio-templates"></a>Hidden 要素 (Visual Studio テンプレート)

[新しいプロジェクト] ダイアログボックスまたは [ **新しい項目の追加** ] ダイアログボックスにテンプレートを表示するかどうかを指定します。

```xml
<VSTemplate>
    <TemplateData>
        <Hidden>
```

## <a name="syntax"></a>構文

```xml
<Hidden>true</Hidden>
<Hidden>false</Hidden>
```

## <a name="attributes-and-elements"></a>属性と要素

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

テキストはまたはのいずれかである必要があります。これは、[ `true` `false` **新しいプロジェクト** ] ダイアログボックスまたは [ **新しい項目の追加** ] ダイアログボックスにテンプレートが表示されるかどうかを示します。

## <a name="remarks"></a>解説

`Hidden` は省略可能な要素です。

指定した場合、要素の他の子要素は必要ありません `TemplateData` 。

## <a name="example"></a>例

次の例は、C# テンプレートのメタデータを示しています。

```xml
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic template</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <Hidden>true</Hidden>
    </TemplateData>
    <TemplateContent>
        <Project File="MyTemplate.csproj">
            <ProjectItem>Form1.cs<ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>関連項目

- [テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)
- [プロジェクト テンプレートと項目テンプレートを作成する](../ide/creating-project-and-item-templates.md)
