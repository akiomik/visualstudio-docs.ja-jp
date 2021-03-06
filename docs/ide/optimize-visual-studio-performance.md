---
title: Visual Studio が遅いときにパフォーマンスを改善する
titleSuffix: ''
description: Visual Studio の動作が遅いときに、そのパフォーマンスを向上させる方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 04/11/2018
ms.topic: conceptual
helpviewer_keywords:
- performance [Visual Studio]
author: TerryGLee
ms.author: tglee
manager: jmartens
f1_keywords:
- vs.performancecenter
ms.workload:
- multiple
ms.openlocfilehash: e1c1be9ef034f4c11fde22e8aa811785631321f5
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99909124"
---
# <a name="optimize-visual-studio-performance"></a>Visual Studio のパフォーマンスを最適化する

この記事では、Visual Studio の動作が遅いときに試すべきことをいくつか紹介します。 パフォーマンス改善案は他にもあり、「[Visual Studio のパフォーマンスのヒントとテクニック](../ide/visual-studio-performance-tips-and-tricks.md)」でご確認いただけます。

## <a name="upgrade-visual-studio"></a>Visual Studio のアップグレード

Visual Studio 2015 を現在使用している場合、[Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) または [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) を無料でダウンロードし、パフォーマンスの改善をご確認ください。 ソリューションの読み込みが Visual Studio 2015 よりも 2 から 3 倍速くなります。その他の面でもパフォーマンスが改善されます。 Visual Studio 2017 と Visual Studio 2019 は、Visual Studio 2015 との間に並行互換性があるので、試しても失うものはありません。

::: moniker range="vs-2017"

Visual Studio 2017 を既に使用している場合、15.6 以降のバージョンを実行していることを確認してください。 バージョン 15.6 ではソリューションの読み込みが最大 2 ～ 3 倍速くなることがデータによって示されています。 [こちら](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download)でダウンロードできます。

::: moniker-end

## <a name="extensions-and-tool-windows"></a>拡張機能とツール ウィンドウ

インストールした拡張機能が Visual Studio を遅くしていることがあります。 拡張機能を管理してパフォーマンスを改善する方法については、[拡張機能設定を変更してパフォーマンスを改善する](../ide/optimize-visual-studio-startup-time.md#extensions)方法に関するページを参照してください。

同様に、ツール ウィンドウが Visual Studio を遅くしていることがあります。 ツール ウィンドウを管理する方法については、[ツール ウィンドウ設定を変更してパフォーマンスを改善する](../ide/optimize-visual-studio-startup-time.md#tool-windows)方法に関するページを参照してください。

## <a name="hardware"></a>ハードウェア

ハードウェアのアップグレードを検討している場合、ソリッドステート ドライブ (SSD) がパフォーマンスの面で RAM を追加したり、より速い CPU に替えたりすることより効果があります。

SSD を追加する場合、最適なパフォーマンスを得るために、ハード ディスク ドライブ (HDD) ではなく、その SSD に Windows をインストールしてください。 お使いの Visual Studio ソリューションをどのドライブに置くかということはそれほど問題ではありません。

また、USB ドライブからはソリューションを実行しないでください。 ソリューションを HDD または SSD にコピーしてください。

## <a name="help-us-improve"></a>改善にご協力ください

お客様からのフィードバックは品質向上に役立ちます。 **問題の報告** 機能を利用してトレースを “記録” し、Microsoft にご送信ください。 **[クイック起動]** の横にあるフィードバック アイコンを選択するか、メニュー バーで **[ヘルプ]** 、 **[フィードバックの送信]** 、 **[問題の報告]** の順に選択します。 詳細については、「[Visual Studio で問題を報告する方法](../ide/how-to-report-a-problem-with-visual-studio.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [パフォーマンスのヒントとテクニック](../ide/visual-studio-performance-tips-and-tricks.md)
- [Visual Studio ブログ - Visual Studio 2017 バージョン 15.6 でソリューションの読み込みを速くする](https://devblogs.microsoft.com/visualstudio/load-solutions-faster-with-visual-studio-2017-version-15-6/)
