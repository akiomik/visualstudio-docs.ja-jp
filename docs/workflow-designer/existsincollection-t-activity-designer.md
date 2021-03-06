---
title: Exists Sincollection &lt; T &gt; アクティビティデザイナー
description: ワークフローデザイナーの [存在しないコレクション] アクティビティデザイナーを使用し <T> て、存在しないコレクションアクティビティを作成および構成する方法について説明し <T> ます。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ExistsInCollection`1.UI
ms.assetid: 0acf9a13-caf5-4bb4-ba22-ec37d2b7267a
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 971d6bd028315ae4a8b6f3a88164c97c6f95712b
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99961327"
---
# <a name="existsincollectiont-activity-designer"></a>ExistsInCollection\<T> アクティビティ デザイナー

存在するアクティビティデザイナーは、アクティビティを作成および構成するために使用されます。 **\<T>** <xref:System.Activities.Statements.ExistsInCollection%601>

## <a name="the-existsincollectiont-activity"></a>存在しているコレクション \<T> アクティビティ

<xref:System.Activities.Statements.ExistsInCollection%601> アクティビティでは、指定した項目が特定のコレクションに存在するかどうかを確認します。

### <a name="using-the-existsincollectiont-activity-designer"></a>"存在しないコレクション" \<T> アクティビティデザイナーの使用

存在 **する場合は、[ツールボックス**] の [**コレクション**] カテゴリにあります。このアクティビティデザイナーにアクセスするには、ワークフローデザイナーの [**ツールボックス**] タブをクリックします。 **\<T>** または、[**表示**] メニューの [**ツールボックス**] を選択するか、 **Ctrl** + **Alt** + **X** キーを押します。

Exists **Sincollection \<T>** アクティビティデザイナーは、[**ツールボックス**] からドラッグして、アクティビティを通常配置している任意の場所 (内など) にワークフローデザイナー画面にドロップできます <xref:System.Activities.Statements.Sequence> 。 これ <xref:System.Activities.Statements.ExistsInCollection%601> により、既定値が存在するアクティビティが作成さ <xref:System.Activities.Activity.DisplayName%2A> \> れます<Int32 です。 (既定では、 *Typeargument* は **Int32** です。 プロパティグリッドで変更できます)。 この値は、存在する場合は、 <xref:System.Activities.Activity.DisplayName%2A> **<\> T** アクティビティデザイナーのヘッダー、またはプロパティグリッドの [ **DisplayName** ] ボックスで編集できます。 他のプロパティは、プロパティ グリッドで編集する必要があります。

### <a name="the-existsincollectiont-properties"></a>存在するコレクションの \<T> プロパティ

次の表は、 <xref:System.Activities.Statements.ExistsInCollection%601> プロパティと、デザイナーでのそれらの使用方法を示しています。

|プロパティ名|必須|使用|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.ExistsInCollection%601> アクティビティの表示名。 既定値は、<Int32 \> です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.ExistsInCollection%601.Item%2A>|True|コレクション内で検索する項目 \<T> 。 この項目の型は *T* で、 *typeargument* 型です。 項目を指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|<xref:System.Activities.Statements.ExistsInCollection%601.Collection%2A>|True|項目が存在するかどうかを確認するコレクション。 このコレクションの型は **ICollection<TypeArgument \> です。** コレクションを指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601> に格納される項目の T 型。 既定では、この *Typeargument* 型は **Int32** に設定されています。 型を変更するには、プロパティグリッドで、コンボボックスの *Typeargument* の値を変更します。|
|<xref:System.Activities.Activity%601.Result%2A>|False|指定した項目がコレクション内に存在するかどうかを示す値。 結果にバインドする変数を指定するには、プロパティ グリッドで Visual Basic 変数を入力します。|

## <a name="see-also"></a>関連項目

- [コレクション](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)
- [RemoveFromCollection\<T>](../workflow-designer/removefromcollection-t-activity-designer.md)