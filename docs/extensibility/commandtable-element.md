---
title: CommandTable 要素 |Microsoft Docs
description: CommandTable は、VSPackage が IDE に提供するコマンドのレイアウトと種類を定義する、. vsct ファイルのルート要素です。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CommandTable
helpviewer_keywords:
- CommandTable element (VSCT XML schema)
- VSCT XML schema elements, CommandTable
ms.assetid: 15c38159-660a-4ef4-9643-aa6fcfca82a9
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 79441880091088cf1d953c8925273e801dc0860d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99887355"
---
# <a name="commandtable-element"></a>CommandTable 要素
CommandTable は、 *. vsct* ファイルのルート要素です。 これは、VSPackage が IDE に提供するコマンドの実際のレイアウトと種類を定義するファイルです。 コマンドには、メニュー項目、メニュー、ツールバー、およびコンボボックスを含めることができます。 詳細については、「 [Visual Studio コマンドテーブル (vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)」を参照してください。

## <a name="syntax"></a>構文

```xml
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema" >
  <Extern>... </Extern>
  <Include>... </Include>
  <Define>... </Define>
  <Commands>... </Commands>
  <CommandPlacements>... </CommandPlacements>
  <VisibilityConstraints>... </VisibilityConstraints>
  <KeyBindings>... </KeyBindings>
  <UsedCommands... </UsedCommands>
  <Symbols>... </Symbols>
</CommandTable>
```

## <a name="attributes-and-elements"></a>属性と要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

| 属性 | 説明 |
|-----------| - |
| xmlns | 必須。 XML 名前空間:<br /><br /> `xmlns=http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable`<br /><br /> xmlns: xs = " <http://www.w3.org/2001/XMLSchema> " |
| language | 任意。 Language 属性は、コマンドテーブル内のすべての要素の既定の言語を指定するために使用でき \<Strings> ます。  言語が指定されていない場合は、現在のプロセスの言語が使用されます。<br /><br /> language = "en-us" |

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[Extern 要素](../extensibility/extern-element.md)|任意。 コンパイラのプリプロセッサディレクティブを格納します。|
|[Include 要素](../extensibility/include-element.md)|任意。 コンパイルに含めるすべてのファイルへのパスを格納します。|
|[Define 要素](../extensibility/define-element.md)|任意。 名前と値を指定してシンボルを定義します。|
|[Commands 要素](../extensibility/commands-element.md)|任意。 他のすべての要素を含む VSPackage のすべてのコマンドを定義する親要素。|
|[CommandPlacements 要素](../extensibility/commandplacements-element.md)|任意。 コマンドバーのどこにコマンドを配置するかを定義します。|
|[VisibilityConstraints 要素](../extensibility/visibilityconstraints-element.md)|任意。 コマンドおよびツールバーを静的に表示するかどうかを決定します。|
|[キーバインド要素](../extensibility/keybindings-element.md)|任意。 コマンドのショートカットキーの組み合わせ (存在する場合) を指定します。|
|[Used Commands 要素](../extensibility/usedcommands-element.md)|任意。 VSPackage は、必要に応じて、他の Vspackage でサポートされていた独自のバージョンの機能を実装できます。|
|[Symbols 要素](https://www.microsoft.com/download/details.aspx?id=55984)|任意。 コンパイラのシンボルデータ (Guid、Id など) が含まれています。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|なし||

## <a name="see-also"></a>関連項目
- [Visual Studio コマンドテーブル (vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
