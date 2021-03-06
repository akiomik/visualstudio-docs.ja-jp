---
title: 依存関係図の拡張
description: 依存関係図を作成および更新するコードを記述する方法、および Visual Studio の依存関係図に対してプログラムコードの構造を検証する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 10e0e07b6a8ee4245e19628e03bfdf484f94d34c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99935145"
---
# <a name="extend-dependency-diagrams"></a>依存関係図の拡張

コードを記述して、依存関係図を作成および更新したり、Visual Studio の依存関係図に対してプログラムコードの構造を検証したりすることができます。 図のショートカット (コンテキスト) メニューに表示するコマンドを追加し、ドラッグ アンド ドロップ ジェスチャをカスタマイズし、テキスト テンプレートからレイヤー モデルにアクセスすることができます。 これらの拡張機能を VSIX (Visual Studio Integration Extension) にパッケージ化し、他の Visual Studio ユーザーに配布することができます。

## <a name="requirements"></a>要件

レイヤー拡張機能を開発するコンピューターに以下の項目がインストールされている必要があります。

- Visual Studio

- [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

- Visual Studio のモデリング SDK

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

レイヤー拡張機能を実行するコンピューターには、適切なエディションの Visual Studio がインストールされている必要があります。 依存関係図をサポートする Visual Studio のエディションについては、「 [アーキテクチャツールとモデリングツールのエディションサポート](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)」を参照してください。

## <a name="see-also"></a>関連項目

- [依存関係図: リファレンス](../modeling/layer-diagrams-reference.md)
- [依存関係図: ガイドライン](../modeling/layer-diagrams-guidelines.md)
- [コードからの依存関係図の作成](../modeling/create-layer-diagrams-from-your-code.md)
- [依存関係図を使用したコードの検証](../modeling/validate-code-with-layer-diagrams.md)
