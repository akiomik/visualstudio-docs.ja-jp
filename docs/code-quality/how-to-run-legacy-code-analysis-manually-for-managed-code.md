---
title: レガシコード分析を手動で実行する (.NET)
description: ソースコードで発生する可能性のある欠陥を検出する方法について説明します。 「Visual Studio でマネージコードに対してレガシコード分析を手動で実行する方法」を参照してください。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- code analysis, running
ms.assetid: 5086d228-f92e-4515-9708-c5b89b9e9a03
author: Mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- dotnet
ms.openlocfilehash: 45f201e2c647a1b1074585d59c7618e1ddeb9084
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99859997"
---
# <a name="how-to-run-legacy-code-analysis-manually-for-managed-code"></a>方法: マネージコードに対してレガシコード分析を手動で実行する

コード分析ツールは、ソースコードで発生する可能性のある欠陥に関する情報を提供します。 コードプロジェクトの各ビルドでコード分析を自動的に実行できます。また、コード分析を手動で実行することもできます。 コード分析の実行時にチェックされる規則は、プロジェクトのプロパティページの [コード分析] ページで指定します。 詳細については、「 [方法: マネージコードプロジェクトのコード分析を構成する](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)」を参照してください。

## <a name="to-run-code-analysis-manually"></a>コード分析を手動で実行するには

1. Visual Studio 2019 バージョン16.5 以降を使用している場合は、Visual Studio を起動する前に、コマンドプロンプトで次のコマンドを実行します。

```
set EnableLegacyCodeAnalysis = true
```

2. **ソリューションエクスプローラー** で、プロジェクトをクリックします。

3. [**分析**] メニューの [*プロジェクト名***に対してコード分析を実行**] をクリックします。
