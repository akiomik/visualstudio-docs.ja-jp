---
title: ターゲットのバッチの項目メタデータ | Microsoft Docs
description: ビルド ターゲットの入力と出力に対して依存関係分析を実行するため、MSBuild によってターゲットのバッチの項目メタデータが使用される方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, target batching
- target batching [MSBuild]
ms.assetid: f3cc4186-6a4c-4161-bbe5-1ec638b4925b
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 2d3389d24ded805c7b1f8bbb8d31daef0cbef1a5
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99913910"
---
# <a name="item-metadata-in-target-batching"></a>ターゲットのバッチの項目メタデータ

MSBuild には、ビルド ターゲットの入力と出力の依存関係の分析を実行する機能があります。 ターゲットの入力または出力が最新の状態であると判断された場合、ターゲットはスキップされ、ビルドが進行します。 `Target` 要素は `Inputs` 属性と `Outputs` 属性を利用し、依存関係分析中に検査する項目を指定します。

バッチ処理された項目を入力または出力として使用するタスクがターゲットに含まれている場合、ターゲットの `Target` 要素では、既に最新の状態になっている項目のバッチ処理を MSBuild でスキップできるようにするために、その `Inputs` または `Outputs` 属性でバッチ処理を利用する必要があります。

## <a name="batch-targets"></a>バッチのターゲット

次の例には、`Culture` 項目メタデータに基づいて 2 つのバッチに分割されている `Res` という名前の項目一覧が含まれています。 これらのバッチのいずれも `AL` タスクに渡されます。このタスクで、バッチごとに出力アセンブリが作成されます。 `Target` 要素の `Outputs` 属性でバッチ処理を利用することで、MSBuild では、ターゲットを実行する前に、個々のバッチが最新の状態になっているかどうかを判断できます。 ターゲットのバッチ処理を利用しないと、ターゲットが実行されるたびに項目の両方のバッチが実行されます。

```xml
<Project
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <ItemGroup>
        <Res Include="Strings.fr.resources">
            <Culture>fr</Culture>
        </Res>
        <Res Include="Strings.jp.resources">
            <Culture>jp</Culture>
        </Res>
        <Res Include="Menus.fr.resources">
            <Culture>fr</Culture>
        </Res>
        <Res Include="Dialogs.fr.resources">
            <Culture>fr</Culture>
        </Res>
        <Res Include="Dialogs.jp.resources">
            <Culture>jp</Culture>
        </Res>
        <Res Include="Menus.jp.resources">
            <Culture>jp</Culture>
        </Res>
    </ItemGroup>

    <Target Name="Build"
        Inputs="@(Res)"
        Outputs="%(Culture)\MyApp.resources.dll">

        <AL Resources="@(Res)"
            TargetType="library"
            OutputAssembly="%(Culture)\MyApp.resources.dll">

    </Target>

</Project>
```

## <a name="see-also"></a>関連項目

- [方法: インクリメンタル ビルド](../msbuild/how-to-build-incrementally.md)
- [バッチ処理](../msbuild/msbuild-batching.md)
- [Target 要素 (MSBuild)](../msbuild/target-element-msbuild.md)
- [タスクのバッチの項目メタデータ](../msbuild/item-metadata-in-task-batching.md)
