---
title: コードメトリックスウィンドウ
ms.date: 12/12/2017
description: Visual Studio code のメトリック分析データを表示、フィルター処理、再配置、およびエクスポートする方法について説明します。 「コードメトリックスの結果に基づいて作業項目を作成する方法」を参照してください。
ms.custom: SEO-VS-2020
ms.topic: reference
f1_keywords:
- vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: c02f5a3b5175be4517a51a6dc477d6e59b38a762
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99859568"
---
# <a name="use-the-code-metrics-results-window"></a>[コードメトリックスの結果] ウィンドウを使用する

[ **コードメトリックスの結果** ] ウィンドウには、コードメトリックス分析によって生成されるデータが表示されます。 コードメトリックスのデータ値の詳細については、「 [コードメトリックスの値](../code-quality/code-metrics-values.md)」を参照してください。

## <a name="display-code-metrics-results"></a>コードメトリックスの結果を表示する

コードメトリックスの結果を生成すると、[ **コードメトリックスの結果** ] ウィンドウが自動的に表示されます。 ウィンドウはいつでも表示できます。

コードメトリックスの結果ウィンドウは、次のいずれかのメニューシーケンスを使用して表示できます。

- [**分析**] メニューの [ **Windows**  >  **コードメトリックスの結果**] をクリックします。

- [**表示**] メニューの [**その他の Windows**  >  **コードメトリックスの結果**] をクリックします。

結果が含まれていない場合でも、[ **コードメトリックスの結果** ] ウィンドウが開きます。

### <a name="to-view-code-metrics-details"></a>コードメトリックスの詳細を表示するには

コードメトリックスの結果が生成された場合は、[ **階層** ] 列のツリーを展開します。

## <a name="filter-code-metrics-results"></a>コードメトリックスの結果をフィルター処理する

上部にあるツールバーを使用して、[ **コードメトリックスの結果** ] ウィンドウに表示される結果をフィルター処理できます。 たとえば、保守容易性インデックスが65未満の結果のみを表示することができます。

[ **フィルター** ] ドロップダウンボックスには、結果列の名前が表示されます。 フィルターが定義されると、一覧の一番下にインデントと共に追加されます。 一覧には、定義された最後の10個のフィルターを含めることができます。

### <a name="to-filter-the-code-metrics-results"></a>コードメトリックスの結果をフィルター処理するには

1. [ **フィルター** ] ボックスの一覧から列名を選択します。

2. [ **最小**] で、表示する最小値を入力します。

3. [ **最大**] で、表示される最大値を入力します。

4. [ **フィルターの適用** ] ボタンをクリックします。

5. 結果の詳細を表示するには、階層ツリーを展開します。

## <a name="add-remove-and-rearrange-data-columns"></a>データ列の追加、削除、および再配置

[ **コードメトリックスの結果** ] ウィンドウで結果列を追加または削除できます。 また、結果列を目的の順序で表示されるように再配置することもできます。

### <a name="add-or-remove-a-column"></a>列を追加または削除する

1. [ **列の追加と削除** ] ボタンをクリックするか、任意の列見出しを右クリックして、[ **列の追加と削除**] をクリックします。

1. [ **列の追加と削除** ] ダイアログボックスで、追加または削除する列のチェックボックスをオンまたはオフにし、[ **OK]** をクリックします。

### <a name="rearrange-columns"></a>列の再配置

1. [ **列の追加と削除** ] ボタンをクリックします。

1. [ **列の追加と削除** ] ダイアログボックスで、移動する列を選択し、上矢印または下矢印を選択します。

1. 列が必要な位置に配置されたら、 **[OK]** をクリックします。

## <a name="copy-data-to-the-clipboard-or-excel"></a>クリップボードまたは Excel にデータをコピーする

選択した行のコードメトリックスデータをクリップボードにコピーするには、各データ列の名前と値の1行を含むテキスト文字列を選択します。 また、[ **Microsoft excel で選択** した項目を開く] をクリックして、すべてのコードメトリックスの結果を excel スプレッドシートにエクスポートすることもできます。

## <a name="create-a-work-item-based-on-code-metric-results"></a>コードメトリックスの結果に基づいて作業項目を作成する

[**コードメトリックスの結果**] ウィンドウの結果に基づいて、 [Azure Boards](/azure/devops/boards/index?view=vsts&preserve-view=true)作業項目を作成できます。 作業項目が作成されると、Visual Studio によって [ **タイトル** ] フィールドにタイトルとコードメトリックスデータが自動的に [ **履歴** ] タブに入力されます。

作業項目の Azure Boards の詳細については、「 [作業項目](/azure/devops/boards/work-items/index?view=vsts&preserve-view=true)」を参照してください。

### <a name="to-create-a-work-item-based-on-a-result"></a>結果に基づいて作業項目を作成するには

1. 結果を右クリックします。

2. [ **作業項目の作成**] をポイントし、作成する作業項目の種類 (**バグ**、 **タスク** など) をクリックします。

3. すべての必須フィールドに入力して、作業項目フォームを完成させます。

4. [ **ファイル** ] メニューの [ **すべてを保存** ] をクリックして、作業項目を保存します。

### <a name="to-create-a-bug-based-on-a-result"></a>結果に基づいてバグを作成するには

1. 結果をクリックして選択します。

2. [ **作業項目の作成** ] ボタンをクリックします。

3. すべての必須フィールドに入力して、作業項目フォームを完成させます。

4. [ **ファイル** ] メニューの [ **すべてを保存** ] をクリックして、作業項目を保存します。

## <a name="see-also"></a>関連項目

- [コードメトリックスの値](../code-quality/code-metrics-values.md)
- [方法: コードメトリックスデータを生成する](../code-quality/how-to-generate-code-metrics-data.md)
