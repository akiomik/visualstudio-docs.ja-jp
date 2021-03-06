---
title: 従来の言語サービスの機能拡張 |Microsoft Docs
description: Visual Studio の従来の言語サービスの構造、実装、および拡張性について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services
- Visual Studio, language services
ms.assetid: 2700cd4d-5f68-43fc-b62f-dc80c3f3aa85
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: a6a886cce4140ed31fa7d472de7e78a42d810d49
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99839652"
---
# <a name="legacy-language-service-extensibility"></a>従来の言語サービスの機能拡張
言語サービスは、IDE でソースコードを編集するための言語固有のサポートを提供します。

 従来の言語サービスは VSPackage の一部として実装されていますが、言語サービス機能を実装するための新しい方法として、MEF 拡張機能を使用することをお勧めします。 言語サービスを実装する新しい方法の詳細については、「 [エディターと言語サービスの拡張機能](../../extensibility/editor-and-language-service-extensions.md)」を参照してください。

 このセクションでは、従来の言語サービスの構造と実装について説明します。

## <a name="in-this-section"></a>このセクションの内容
- [従来の言語サービスの移行](../../extensibility/internals/migrating-a-legacy-language-service.md)

 言語サービスを Visual Studio 2008 から最新バージョンに更新する方法について説明します。

- [従来の言語サービスの基本情報](../../extensibility/internals/legacy-language-service-essentials.md)

 言語サービスを開発してプログラミング言語を Visual Studio に統合する方法についての重要な情報を提供します。

- [従来の言語サービスの開発](../../extensibility/internals/developing-a-legacy-language-service.md)

 言語サービスの作成に役立つトピックへのリンクを示します。

- [従来の言語サービスでの構文の色分け表示](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)

 言語サービスでの構文の強調表示に関する情報を提供します。

- [従来の言語サービスの実装](../../extensibility/internals/implementing-a-legacy-language-service1.md)

 Managed package framework (MPF) を使用して、完全な機能を備えた言語サービスをマネージコードで実装する方法について説明します。

- [シンボル参照ツールのサポート](../../extensibility/internals/supporting-symbol-browsing-tools.md)

 IDE でシンボルのツリービューを参照できるようにするライブラリとツールについて説明します。

## <a name="related-sections"></a>関連項目
- [エディターと言語サービスの拡張機能](../../extensibility/editor-and-language-service-extensions.md)

 Visual Studio エディターの概要について説明します。

- [デバッグのための言語サービスのサポート](../../extensibility/internals/language-service-support-for-debugging.md)

 と Visual Studio デバッグ SDK へのリンクを提供します。この SDK には、プログラムのデバッグに使用されるデバッガーコンポーネントを作成およびカスタマイズするために必要な情報が含まれています。
