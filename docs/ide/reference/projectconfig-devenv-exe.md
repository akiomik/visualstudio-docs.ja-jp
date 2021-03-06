---
title: -ProjectConfig (devenv.exe)
description: devenv の ProjectConfig コマンドライン スイッチを使用して、プロジェクトをビルド、消去、リビルド、または配置する場合に適用されるプロジェクトのビルド構成を指定する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- /ProjectConfig Devenv switch
- configurations, rebuilding
- deployment projects, creating
- configurations, cleaning
- deployment projects, specifying
- deployment projects, adding
- build configurations, specifying
- Devenv, /ProjectConfig switch
- ProjectConfig Devenv switch (/ProjectConfig)
- projects [Visual Studio], build configuration
- projects [Visual Studio], cleaning
ms.assetid: 6b54ef59-ffed-4f62-a645-1279ede97ebf
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: ba1f6f0de7e7b716853ec58aa27a34fe11010da4
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99969595"
---
# <a name="projectconfig-devenvexe"></a>/ProjectConfig (devenv.exe)

`/Project` 引数で指定されたプロジェクトをビルド、消去、リビルド、または展開する際に適用されるプロジェクトのビルド構成を指定します。

## <a name="syntax"></a>構文

```shell
devenv SolutionName {/Build|/Clean|/Deploy|/Rebuild} [SolnConfigName [/Project ProjName [/ProjectConfig ProjConfigName]] [/Out OutputFilename]]
```

## <a name="arguments"></a>引数

- *SolutionName*

  必須。 ソリューション ファイルの完全パスと名前。

- {`/Build`|`/Clean`|`/Deploy`|`/Rebuild`}

  必須。 プロジェクトの[ビルド](build-devenv-exe.md)、[消去](clean-devenv-exe.md)、[配置](deploy-devenv-exe.md)、または[リビルド](rebuild-devenv-exe.md)を行います。

- *SolnConfigName*

  省略可能。 *SolutionName* で指定されたソリューションに適用されるソリューション構成の名前 (`Debug`、`Release` など)。 複数のソリューション プラットフォームが利用できる場合、プラットフォームも指定する必要があります (`Debug|Win32` など)。 この引数が指定されていないか空の文字列 (`""`) の場合、ソリューションのアクティブな構成が使用されます。

- `/Project` *ProjName*

  省略可能。 ソリューション内のプロジェクト ファイルのパスと名前です。 プロジェクトの表示名または *SolutionName* フォルダーからプロジェクト ファイルへの相対パスを入力できます。 プロジェクト ファイルの完全なパスと名前を入力することもできます。

- `/ProjectConfig` *ProjConfigName*

  省略可能。 指定した `/Project` に適用されるプロジェクトのビルド構成名 (`Debug`、`Release` など)。 複数のソリューション プラットフォームが利用できる場合、プラットフォームも指定する必要があります (`Debug|Win32` など)。

- `/Out` *OutputFilename*

  省略可能。 ツールの出力を送信する先のファイル名。 このファイルが既に存在する場合、ファイルの末尾に出力が追加されます。

## <a name="remarks"></a>注釈

`/ProjectConfig` スイッチは、`/Build`、/`Clean`、`/Deploy`、または `/Rebuild` コマンドの一部として `/Project` スイッチと共に使用する必要があります。

空白を含む文字列を二重引用符で囲みます。

エラーなどのビルドの概要情報は、[コマンド] ウィンドウ、または `/Out` スイッチで指定された任意のログ ファイルに表示できます。

## <a name="example"></a>例

次のコマンドでは、`MySolution` 内の `Debug` プロジェクト ビルド構成を使用して、プロジェクト `CSharpWinApp` をビルドします。

```shell
devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>参照

- [Devenv コマンドライン スイッチ](../../ide/reference/devenv-command-line-switches.md)
- [/Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Deploy (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
