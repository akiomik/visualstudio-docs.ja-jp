---
title: TerminateWorkflow アクティビティデザイナー
description: ワークフローデザイナーでは、TerminateWorkflow アクティビティデザイナーを使用して TerminateWorkflow アクティビティを作成および構成する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 3f37c862768dd0d72ba66d435478faed9bee8ef3
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99931488"
---
# <a name="terminateworkflow-activity-designer"></a>TerminateWorkflow アクティビティ デザイナー

**TerminateWorkflow** アクティビティデザイナーは、アクティビティを作成および構成するために使用され <xref:System.Activities.Statements.TerminateWorkflow> ます。

## <a name="the-terminateworkflow-activity"></a>TerminateWorkflow アクティビティ

<xref:System.Activities.Statements.TerminateWorkflow> アクティビティは、ワークフローの実行を停止します。

### <a name="using-the-terminateworkflow-activity-designer"></a>TerminateWorkflow アクティビティ デザイナーの使用

**TerminateWorkflow** アクティビティデザイナーは、 **[ツールボックス**] の [**ランタイム**] カテゴリにあります。このカテゴリにアクセスするには、[**ツール** ボックス] タブをクリックします (または、[**表示**] メニューの [**ツールボックス**] を選択するか、CTRL + ALT + X キーを押します)。

**TerminateWorkflow** アクティビティデザイナーは、[**ツールボックス**] からドラッグして、アクティビティを通常配置している任意の場所 (内など) にワークフローデザイナー画面にドロップできます <xref:System.Activities.Statements.Sequence> 。 これ <xref:System.Activities.Statements.TerminateWorkflow> により、TerminateWorkflow という既定の **DisplayName** を持つアクティビティが作成されます。 は、 <xref:System.Activities.Activity.DisplayName%2A> **TerminateWorkflow** アクティビティデザイナーのヘッダー、またはプロパティグリッドの [ **DisplayName** ] ボックスで編集できます。

### <a name="the-terminateworkflow-properties"></a>TerminateWorkflow のプロパティ

次の表に、<xref:System.Activities.Statements.TerminateWorkflow> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティグリッドで編集することができ、一部のプロパティはワークフローデザイナー画面で編集できます。

|プロパティ名|必須|使用|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TerminateWorkflow> アクティビティの表示名。 既定値は TerminateWorkflow です。 表示名は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|ワークフローが停止されたときにスローする例外。 このプロパティは、プロパティ グリッドで設定します。|
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|ワークフローが停止された理由。 このプロパティは、プロパティ グリッドで設定します。|

## <a name="see-also"></a>関連項目

- [Runtime](../workflow-designer/runtime-activity-designers.md)
- [保持](../workflow-designer/persist-activity-designer.md)
