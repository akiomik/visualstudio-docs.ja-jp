---
title: コンストラクターのクイック アクションを生成する
description: '[クイックアクションとリファクタリング] メニューを使用して、クラスのコードをすぐに生成する方法について説明します。'
ms.custom: SEO-VS-2020
ms.date: 07/10/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jmartens
ms.workload:
- dotnet
ms.openlocfilehash: 24e9324444dbeb10a86184f7c15ea8b88e118177
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99898060"
---
# <a name="generate-a-constructor-in-visual-studio"></a>Visual Studio でコンストラクターを生成する

このコード生成は以下に適用されます。

- C#

- Visual Basic

**概要:** クラスの新しいコンストラクターのコードをすぐに生成できます。

**条件:** 新しいコンストラクターを導入し、自動的に適切に宣言したいとき。または既存のコンストラクターを変更するとき。

**理由:** コンストラクターは使用する前に自分で宣言できますが、この機能ではコンストラクターと適切なパラメーターが自動的に生成されます。 さらに、既存のコンストラクターを変更するには、この機能を使って自動的に更新しない限り、すべての呼び出しサイトを更新する必要があります。

**方法:** コンストラクターを生成するにはいくつかの方法があります。

- [コンストラクターを生成してメンバーを選択する](#pick)
- [プロパティを指定してコンストラクターを生成する](#with)
- [選択したフィールドからコンストラクターを生成する](#selection)
- [新しい使用からコンストラクターを生成する](#usage)
- [既存のコンストラクターにパラメーターを追加する](#addparameter)
- [コンストラクターのパラメーターからフィールド/プロパティを作成して初期化する](#create)

## <a name="generate-constructor-and-pick-members-c-only"></a><a id = "pick"></a> コンストラクターを生成してメンバーを選択する (C# のみ)

1. クラス内の任意の空の行にカーソルを置きます。

   ![空の行のカーソル](media/constructor1-highlight-cs.png)

1. 次に、以下のいずれかを実行します。

   - **[キーボード]**
      - 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
   - **マウス**
      - 右クリックして **[クイック アクションとリファクタリング]** メニューを選択します。
      - テキスト カーソルが既にクラスの空の行の上にある場合に、左余白に表示される :::image type="icon" source="media/screwdriver.png"::: アイコンをクリックします。

   ![[生成] オプションのスクリーンショット。](media/constructor1-preview-cs.png)

1. ドロップダウン メニューから **[コンストラクターを生成する]** を選択します。

   **[メンバーの選択]** ダイアログ ボックスが開きます。

1. コンストラクターのパラメーターとして含めるメンバーを選択します。 上下の矢印を使って順序を変更できます。 **[OK]** をクリックします。

   ![[メンバーの選択] ダイアログ](media/constructor1-dialog-cs.png)

   > [!TIP]
   > **[null チェックを追加する]** チェックボックスをオンにすると、コンストラクターのパラメーターの null チェックを自動的に生成できます。

   指定したパラメーターを含むコンストラクターが作成されます。

   ![指定したパラメーターで生成されたものを示すスクリーンショット。](media/constructor1-result-cs.png)

## <a name="generate-constructor-with-properties-c-only"></a><a id = "with"></a> プロパティを指定してコンストラクターを生成する (C# のみ)

1. インスタンスにカーソルを合わせます。

2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

3. **[`<QualifiedName>` でコンストラクターを生成する (プロパティ付き)** ] を選択します。

   ![[キーで生成する (プロパティ付き)] オプションのスクリーンショット。](media/generate-constructor-with-properties.png)

## <a name="generate-constructor-from-selected-fields-c-only"></a><a id="selection"></a> 選択したフィールドからコンストラクターを生成する (C# のみ)

1. 生成されるコンストラクターに含めるメンバーを強調表示します。

   ![メンバーを強調表示する](media/constructor2-highlight-cs.png)

1. 次に、以下のいずれかを実行します。

   - **[キーボード]**
      - 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
   - **マウス**
      - 右クリックして **[クイック アクションとリファクタリング]** メニューを選択します。
      - テキスト カーソルが既に選択した行の上にある場合に、左余白に表示される :::image type="icon" source="media/screwdriver.png"::: アイコンをクリックします。

      ![[Person string string を生成します] オプションのスクリーンショット。](media/constructor2-preview-cs.png)

1. ドロップダウン メニューから **[コンストラクター 'TypeName(...)' を生成します]** を選択します。

   選択したパラメーターを含むコンストラクターが作成されます。

   ![選択したパラメーターで生成されたものを示すスクリーンショット。](media/constructor2-result-cs.png)

## <a name="generate-constructor-from-new-usage-c-and-visual-basic"></a><a id="usage"></a> 新しい使用からコンストラクターを生成する (C#、Visual Basic)

1. 赤い波線が表示されている行にカーソルを置きます。 赤い波線は、まだ存在していないコンストラクターの呼び出しを示します。

   - C#:

       ![強調表示された C# のコード](media/constructor-highlight-cs.png)

   - Visual Basic:

       ![強調表示された VB のコード](media/constructor-highlight-vb.png)

2. 次に、以下のいずれかを実行します。

   - **[キーボード]**
      - 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
   - **マウス**
      - 右クリックして **[クイック アクションとリファクタリング]** メニューを選択します。
      - 赤い波線をポイントし、表示された :::image type="icon" source="media/error-bulb.png"::: アイコンをクリックします。
      - テキスト カーソルが既に赤い波線の行の上にある場合に、左余白に表示される :::image type="icon" source="media/error-bulb.png"::: アイコンをクリックします。

      ![[Person に生成します] オプションのスクリーンショット。](media/constructor-preview-cs.png)

3. ドロップダウン メニューから **['*TypeName*' にコンストラクターを生成します]** を選択します。

   > [!TIP]
   > プレビュー ウィンドウの下部にある **[変更のプレビュー]** リンクを使うと、選択する前に、行われる [すべての変更を確認する](../../ide/preview-changes.md)ことができます。

   コンストラクターと、その使用法から推論されるすべてのパラメーターが作成されます。

   - C#:

       ![C# のメソッド生成結果](media/constructor-result-cs.png)

   - Visual Basic:

       ![VB のメソッド生成結果](media/constructor-result-vb.png)

## <a name="add-parameter-to-existing-constructor-c-only"></a><a id="addparameter"></a> 既存のコンストラクターにパラメーターを追加する (C# のみ)

1. 既存のコンストラクターの呼び出しにパラメーターを追加します。

2. まだ存在しないコンストラクターを使用したことを示す赤い波線がある行にカーソルを置きます。

    ![赤い波線が表示されている行のスクリーンショット。](media/constructor4-highlight-cs.png)

3. 次に、以下のいずれかを実行します。

   - **[キーボード]**
      - 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
   - **マウス**
      - 右クリックして **[クイック アクションとリファクタリング]** メニューを選択します。
      - 赤い波線をポイントし、表示された :::image type="icon" source="media/error-bulb.png"::: アイコンをクリックします。
      - テキスト カーソルが既に赤い波線の行の上にある場合に、左余白に表示される :::image type="icon" source="media/error-bulb.png"::: アイコンをクリックします。

      ![[パラメーターを Person string string に追加する] オプションのスクリーンショット。](media/constructor4-preview-cs.png)

4. ドロップダウン メニューから **[パラメーターを 'TypeName(...)' に追加する]** を選択します。

   パラメーターと、その使用法から推測される型が、コンストラクターに追加されます。

   ![パラメーターと、その使用法から推測される型が、コンストラクターに追加されていることを示すスクリーンショット。](media/constructor4-result-cs.png)

また、既存のメソッドにパラメーターを追加することもできます。 詳細については、[メソッドにパラメーターを追加する方法](add-parameter.md)に関するページを参照してください。

## <a name="create-and-initialize-a-field-or-property-from-a-constructor-parameter-c-only"></a><a id="create"></a> コンストラクターのパラメーターからフィールドまたはプロパティを作成して初期化する (C# のみ)

1. 既存のコンストラクターを探して、パラメーターを追加します。

   ![既存のコンストラクターを示すスクリーンショット。](media/constructor5-highlight-cs.png)

1. 新しく追加されたパラメーター内にカーソルを置きます。

1. 次に、以下のいずれかを実行します。

   - **[キーボード]**
      - 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
   - **マウス**
      - 右クリックして **[クイック アクションとリファクタリング]** メニューを選択します。
      - パラメーターが追加された行の上に既にテキスト カーソルがある場合に、左余白に表示される :::image type="icon" source="media/screwdriver.png"::: アイコンをクリックします。

   ![[プロパティ 'Age' を作成して初期化する] オプションのスクリーンショット。](media/constructor5-preview-cs.png)

1. ドロップダウン メニューから **[プロパティ '{0}' を作成して初期化する]** または **[フィールド '{0}' を作成して初期化する]** を選びます。

   フィールドまたはプロパティが宣言されて、自動的に型と一致する名前が付けられます。 また、フィールドまたはプロパティを初期化するコード行が、コンストラクターの本体に追加されます。

   ![フィールドまたはプロパティが宣言されて、自動的に型と一致する名前が付けられていることを示すスクリーンショット。](media/constructor5-result-cs.png)

## <a name="see-also"></a>関連項目

- [コード生成](../code-generation-in-visual-studio.md)
- [変更のプレビュー](../../ide/preview-changes.md)
