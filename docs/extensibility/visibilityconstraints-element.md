---
title: VisibilityConstraints 要素 |Microsoft Docs
description: VisibilityConstraints 要素は、コマンドおよびツールバーのグループの静的表示を決定します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VisibilityConstraints
helpviewer_keywords:
- VSCT XML schema elements, VisibilityConstraints
- VisibilityConstraints element (VSCT XML schema)
ms.assetid: d6dcd314-6fe4-4693-a189-91fa026c7b34
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: bb6047c98031c484f6a0a51ab2a393a2a46bb2a2
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99926091"
---
# <a name="visibilityconstraints-element"></a>VisibilityConstraints 要素
VisibilityConstraints 要素は、コマンドおよびツールバーのグループの静的表示を決定します。 可視性は、 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage を読み込まずに、統合開発環境 (IDE) によって最初に制御されます。

## <a name="syntax"></a>構文

```xml
<VisibilityConstraints>
  <VisibilityItem />
  <VisibilityItem />
</VisibilityConstraints>
```

## <a name="attributes-and-elements"></a>属性と要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

|属性|説明|
|---------------|-----------------|
|条件|任意。 「 [条件付き属性](../extensibility/vsct-xml-schema-conditional-attributes.md)」を参照してください。|

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[VisibilityItem 要素](../extensibility/visibilityitem-element.md)|コマンドおよびツールバーを静的に表示するかどうかを決定します。|
|[VisibilityConstraints](../extensibility/visibilityconstraints-element.md)|コマンドおよびツールバーのグループを静的に表示するかどうかを決定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[CommandTable 要素](../extensibility/commandtable-element.md)|VSPackage が IDE に提供するコマンド (メニュー項目、メニュー、ツールバー、コンボボックスなど) を表すすべての要素を定義します。|

## <a name="example"></a>例

```xml
<VisibilityConstraints>
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"
    context="guidNotViewSourceMode"/>
</VisibilityConstraints>
```

## <a name="see-also"></a>関連項目
- [VisibilityItem 要素](../extensibility/visibilityitem-element.md)
- [Visual Studio コマンドテーブル (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
