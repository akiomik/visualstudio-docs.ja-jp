---
title: コード マップ アナライザーを使用して潜在的な問題を検索する
description: コードマップでアナライザーを実行して、複雑なコードや改善が必要なコードを特定する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.progression.codemapanalyzers
helpviewer_keywords:
- code analysis, dependency graphs
- dependency graphs, analyzing code
- graph documents, analyzing
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 77e5d8f6241f6f1978f24b9ebb5ad49aa9f24331
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99934989"
---
# <a name="find-potential-problems-using-code-map-analyzers"></a>コード マップ アナライザーを使用して潜在的な問題を検索する

コード マップに対してアナライザーを実行して、複雑すぎるコードや、改良が必要なコードを特定できます。 たとえば、アナライザーを使用して次のような作業を実行できます。

|**次のものが含まれたコードを見つける**|**問題の領域を調べて次のことを確認する**|
|-|-|
|ループまたは循環の依存関係|これらを単純化できないか確認する。また、これらの循環をブレークできないか検討する。|
|多すぎる依存関係|実行している関数が多すぎないか確認する。または、これらの領域を変更した場合の影響を判断する。 適切な形式のコード マップには最小限の数の依存関係が表示される。 コードの保守、変更、テスト、再利用を容易にするために、これらの領域をリファクタリングして依存関係をより明確に定義できないか検討する。または、同様の関数を実行するコードをマージできないか検討する。|
|依存関係なし|依存関係が必要かどうか確認する。または、このコードを削除する必要があるかどうか確認する。|

## <a name="analyze-code-maps"></a>コード マップの分析

マップのツールバーで、[**レイアウト** アナライザー] を選択し、実行するアナライザーを選択し  >  ます。

|**Analyzer**|**次のようなノードを特定する**|
|-|-|
|**循環参照アナライザー**|相互に循環する依存関係を持つノード。 **注:** **ジェネリック** グループに含まれる循環依存関係は、グループを展開したときにマップに表示されません。|
|**ハブ検索アナライザー**|緊密に連結されたノードの上位 25 % にあるノード<br /><br /> **マップ上の他のすべてのノードを非表示にするには**<br /><br /> -マップのショートカットメニューを開き、[ **詳細設定**]、 **[選択範囲** の **非表示**] の順に選択します。<br />     マップで選ばれていないノードが非表示にされ、アナライザーで新しいノードがハブとして識別されます。|
|**未参照ノード アナライザー**|他のノードからの参照がないノード。 **注意:**  コードが使用されていないと想定する前に、これらの各ケースを確認してください。 XAML の依存関係や実行時の依存関係などの特定の依存関係は、コード内で静的には見つかりません。|

コード マップのアナライザーは、適用後も引き続き実行されます。 マップを変更すると、適用されたアナライザーが、更新されたマップを自動的に再処理します。 アナライザーの実行を停止するには、マップのツールバーで [**レイアウト** アナライザー] を選択し  >  ます。 選んだアナライザーをオフにします。

> [!TIP]
> サイズの非常に大きなマップが存在する場合、アナライザーを実行するとメモリ不足例外が発生する可能性があります。 例外が発生した場合は、マップを編集してスコープを縮小するか、より小さいマップを生成してから、アナライザーを実行します。

## <a name="see-also"></a>関連項目

- [ソリューション間の依存関係をマップする](../modeling/map-dependencies-across-your-solutions.md)
- [コード マップを使用してアプリケーションをデバッグする](../modeling/use-code-maps-to-debug-your-applications.md)
- [デバッグを行うときの呼び出し履歴に対するメソッドのマップ](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
