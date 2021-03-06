---
title: カスタムコード分析規則セットを作成する
ms.date: 11/02/2018
description: Visual Studio でコード分析規則セットをカスタマイズする方法について説明します。 新しいセットを最初から作成する方法、または既存のセットから作成する方法を参照してください。 規則の優先順位を理解します。
ms.custom: SEO-VS-2020
ms.topic: how-to
f1_keywords:
- vs.codeanalysis.addremoverulesets
helpviewer_keywords:
- rule sets
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: dda89e9822e361438346300a2f60c05bcfd64d6f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99860153"
---
# <a name="customize-a-rule-set"></a>規則セットをカスタマイズする

カスタム規則セットを作成して、コード分析のための特定のプロジェクトのニーズを満たすことができます。

## <a name="create-a-custom-rule-set-from-an-existing-rule-set"></a>既存の規則セットからカスタム規則セットを作成する

カスタム規則セットを作成するには、 **規則セットエディター** で組み込み規則セットを開くことができます。 そこから、特定のルールを追加または削除したり、ルールに違反したときに発生するアクションを変更したりでき &mdash; ます。たとえば、警告やエラーが表示されます。

1. **ソリューションエクスプローラー** で、プロジェクトを右クリックし、[**プロパティ**] を選択します。

2. [ **プロパティ** ] ページで、[ **コード分析** ] タブを選択します。

::: moniker range="vs-2017"

3. [ **この規則セットを実行** ] ドロップダウンリストで、次のいずれかの操作を行います。

::: moniker-end

::: moniker range=">=vs-2019"

3. [ **アクティブな規則** ] ドロップダウンリストで、次のいずれかの操作を行います。

::: moniker-end

   - カスタマイズする規則セットを選択します。

     \- または

   - **\<Browse>** 一覧に含まれていない既存の規則セットを指定する場合に選択します。

4. [ **開く** ] を選択すると、ルールセットエディターにルールが表示されます。

> [!NOTE]
> .NET Core または .NET Standard プロジェクトがある場合、プロジェクトプロパティの [ **コード分析** ] タブでは同じオプションがサポートされないため、プロセスは少し異なります。 手順に従って、 [定義済みの規則セットをプロジェクトにコピーし、アクティブな規則セットとして設定](/dotnet/fundamentals/code-analysis/code-quality-rule-options)します。 規則セットをコピーした後は、 [Visual Studio の規則セットエディターで](working-in-the-code-analysis-rule-set-editor.md)**ソリューションエクスプローラー** から開くことで編集できます。

## <a name="create-a-new-rule-set"></a>新しい規則セットを作成する

新しい規則セットファイルは、[ **新しいファイル** ] ダイアログから作成できます。

1. [**ファイル**] [新しいファイル] を選択する  >    >  か、 **ctrl** + **N** キーを押します。

2. [ **新しいファイル** ] ダイアログボックスで、左側の [ **全般** ] カテゴリを選択し、[ **コード分析ルールセット**] を選択します。

3. **[開く]** を選択します。

   ルールセットエディターに新しい *ルール* セットファイルが開きます。

## <a name="create-a-custom-rule-set-from-multiple-rule-sets"></a>複数の規則セットからカスタム規則セットを作成する

> [!NOTE]
> 次の手順は、[ **コード分析** ] プロパティタブの同じ機能をサポートしていない .net Core プロジェクトまたは .NET Standard プロジェクトには適用されません。

1. **ソリューションエクスプローラー** で、プロジェクトを右クリックし、[**プロパティ**] を選択します。

2. [ **プロパティ** ] ページで、[ **コード分析** ] タブを選択します。

::: moniker range="vs-2017"

3. [ **\<Choose multiple rule sets>** **この規則セットを実行** する] を選択します。

::: moniker-end

::: moniker range=">=vs-2019"

3. [ **\<Choose multiple rule sets>** **アクティブなルール** から] を選択します。

::: moniker-end

4. [ **規則セットの追加と削除** ] ダイアログボックスで、新しい規則セットに含める規則セットを選択します。

   ![[ルールセットの追加または削除] ダイアログボックス](media/add-remove-rule-sets.png)

5. [名前を付け **て保存**] を選択し、 *ルールセット* ファイルの名前を入力して、[ **保存**] を選択します。

   新しい規則セットは、[ **この規則セットを実行** する] の一覧で選択されています。

6. [ **開く** ] を選択して、ルールセットエディターで新しいルールセットを開きます。

## <a name="rule-precedence"></a>ルールの優先順位

- 異なる重大度のルールセットに同じルールが2回以上表示されている場合、コンパイラはエラーを生成します。 次に例を示します。

   ```xml
   <RuleSet Name="Rules for ClassLibrary21" Description="Code analysis rules for ClassLibrary21.csproj." ToolsVersion="15.0">
     <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
       <Rule Id="CA1021" Action="Warning" />
       <Rule Id="CA1021" Action="Error" />
     </Rules>
   </RuleSet>
   ```

- *同じ重要度* のルールセットに同じルールが2回以上表示されている場合は、**エラー一覧** に次の警告が表示されることがあります。

   **CA0063: 規則セットファイル ' your \[ . ルールセット ' またはその依存ルールセットファイルの1つを読み込めませんでした。ファイルが規則セットスキーマに準拠していません。**

- 規則セットに **Include** タグを使用して子規則セットが含まれていて、子と親の規則セットの両方に同じ規則があるが、重大度が異なる場合は、親規則セットの重要度が優先されます。 次に例を示します。

   ```xml
   <!-- Parent rule set -->
   <?xml version="1.0" encoding="utf-8"?>
   <RuleSet Name="Rules for ClassLibrary21" Description="Code analysis rules for ClassLibrary21.csproj." ToolsVersion="15.0">
     <Include Path="classlibrary_child.ruleset" Action="Default" />
     <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
       <Rule Id="CA1021" Action="Warning" /> <!-- Overrides CA1021 severity from child rule set -->
     </Rules>
   </RuleSet>

   <!-- Child rule set -->
   <?xml version="1.0" encoding="utf-8"?>
   <RuleSet Name="Rules from child" Description="Code analysis rules from child." ToolsVersion="15.0">
     <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
       <Rule Id="CA1021" Action="Error" />
     </Rules>
   </RuleSet>
   ```

## <a name="name-and-description"></a>名前と説明

エディターで開いている規則セットの表示名を変更するには、メニューバー の  >  [**プロパティウィンドウ** の表示] をクリックして、[プロパティ] ウィンドウを開きます。 [ **名前** ] ボックスに表示名を入力します。 また、規則セットの説明を入力することもできます。

## <a name="next-steps"></a>次の手順

ルールセットが完成したので、次の手順では、ルールを追加または削除したり、ルール違反の重大度を変更したりして、ルールをカスタマイズします。

> [!div class="nextstepaction"]
> [規則セットエディターで規則を変更する](../code-quality/working-in-the-code-analysis-rule-set-editor.md)

## <a name="see-also"></a>関連項目

- [方法: マネージド コード プロジェクトのコード分析を構成する](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)
- [コード分析規則セットの参照](../code-quality/rule-set-reference.md)