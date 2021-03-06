---
title: ワークフローデザイナー-If アクティビティデザイナー
description: If アクティビティが条件を評価し、その評価の結果に応じてアクティビティを実行する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 93f36a3c2b587718fe6889688baa50224f663c1c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99881361"
---
# <a name="if-activity-designer"></a>If アクティビティ デザイナー

<xref:System.Activities.Statements.If> アクティビティでは、条件を評価し、その評価の結果に応じてアクティビティを実行します。 このアクティビティは、手順型モデルのプログラミング スタイルを使用する場合に最も役立ちます。 <xref:System.Activities.Statements.If> アクティビティは、<xref:System.Activities.Statements.Sequence> アクティビティや <xref:System.Activities.Statements.Parallel> アクティビティなどの内部に入れ子にすることができます。 <xref:System.Activities.Statements.Flowchart> アクティビティを使用している場合は、代わりに、<xref:System.Activities.Statements.FlowDecision> アクティビティの使用を検討してください。

## <a name="if-properties-in-the-workflow-designer"></a>ワークフロー デザイナーでの If のプロパティ

次の表に、最も役に立つ <xref:System.Activities.Statements.If> アクティビティのプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必須|使用|
|-|--------------|-|
|<xref:System.Activities.Statements.If.Condition%2A>|True|実行する子アクティビティを決定する条件。 を設定するには <xref:System.Activities.Statements.If.Condition%2A> 、 **If** アクティビティデザイナーまたはプロパティグリッドの [**条件**] ボックスに Visual Basic 式を入力します。|
|<xref:System.Activities.Statements.If.Else%2A>|False|が false の場合に実行するアクティビティ <xref:System.Activities.Statements.If.Condition%2A> 。  分岐によって実行されるアクティビティを追加するには、 <xref:System.Activities.Statements.If.Else%2A> "ここにアクティビティをドロップします" というヒントテキストが表示された **if** アクティビティデザイナーの [ **Else** ] ボックスに、[**ツールボックス**] からアクティビティをドロップします。|
|<xref:System.Activities.Statements.If.Then%2A>|False|が true の場合に実行するアクティビティ <xref:System.Activities.Statements.If.Condition%2A> 。  分岐によって実行されるアクティビティを追加するには <xref:System.Activities.Statements.If.Then%2A> 、"ここにアクティビティをドロップします" というヒントテキストが表示された **If** アクティビティデザイナーの **[Then** ] ボックスに、[**ツールボックス**] からアクティビティをドロップします。|

## <a name="see-also"></a>関連項目

- [Sequence](../workflow-designer/sequence-activity-designer.md)
- [Parallel](../workflow-designer/parallel-activity-designer.md)
- [制御フロー](../workflow-designer/control-flow-activity-designers.md)
