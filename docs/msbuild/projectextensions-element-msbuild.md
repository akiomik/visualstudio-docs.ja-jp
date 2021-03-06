---
title: ProjectExtensions 要素 (MSBuild) | Microsoft Docs
description: MSBuild プロジェクト ファイルに MSBuild 以外の情報を含めることができる MSBuildProjectExtensions 要素について説明します。
ms.custom: SEO-VS-2020
ms.date: 03/13/2017
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ProjectExtensions
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <ProjectExtensions> element [MSBuild]
- ProjectExtensions element [MSBuild]
ms.assetid: f95f312f-ff92-41eb-9469-ad99e236a307
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: b7b186fa1d7a5ecb8297045d4b0bbb111d136d1d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99905292"
---
# <a name="projectextensions-element-msbuild"></a>ProjectExtensions 要素 (MSBuild)

MSBuild プロジェクト ファイルに、MSBuild 以外の情報を含めることを可能にします。 `ProjectExtensions` 要素内の内容は、すべて MSBuild から無視されます。

 \<Project> \<ProjectExtensions>

## <a name="syntax"></a>構文

```xml
<ProjectExtensions>
    Non-MSBuild information to include in file.
</ProjectExtensions>
```

## <a name="attributes-and-elements"></a>属性と要素

 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

 なし

### <a name="child-elements"></a>子要素

 なし

### <a name="parent-elements"></a>親要素

| 要素 | 説明 |
| - | - |
| [プロジェクト](../msbuild/project-element-msbuild.md) | MSBuild プロジェクト ファイルの必須のルート要素です。 |

## <a name="remarks"></a>Remarks

 `ProjectExtensions` 要素は、MSBuild プロジェクトで 1 つだけ使用できます。

## <a name="example"></a>例

 次のコード例は、`ProjectExtensions` 要素に格納されている統合開発環境の情報を示します。

```xml
<ProjectExtensions>
    <VSIDE>
        <External>
            <!--
            Raw XML passed to the IDE by an external source
            -->
        </External>
    </VSIDE>
</ProjectExtensions>
```

## <a name="see-also"></a>関連項目

- [プロジェクト ファイル スキーマ リファレンス](../msbuild/msbuild-project-file-schema-reference.md)
- [MSBuild](../msbuild/msbuild.md)
