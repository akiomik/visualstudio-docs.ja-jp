---
title: '方法: モデルにエンティティを追加する |Microsoft Docs'
description: エンティティをモデルに追加するには、Visual Studio のツールボックスからビジネスデータ接続 (BDC) デザイナーにエンティティコントロールを追加します。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
f1_keywords:
- EntityTool
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], entity
- Business Data Connectivity service [SharePoint development in Visual Studio], adding an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], entity
- BDC [SharePoint development in Visual Studio], adding an entity
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 1d900639463f727a23c4fafab6f077f787c5ca04
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99959975"
---
# <a name="how-to-add-an-entity-to-a-model"></a>方法: モデルにエンティティを追加する
  エンティティを作成するには、Visual Studio の **ツールボックス** から Business Data CONNECTIVITY (BDC) デザイナーにエンティティコントロールを追加します。

### <a name="to-add-an-entity-to-the-model"></a>エンティティをモデルに追加するには

1. BDC プロジェクトを作成するか、既存の BDC プロジェクトを開きます。 詳細については、「[ビジネス データ接続モデルを作成する](../sharepoint/creating-a-business-data-connectivity-model.md)」を参照してください。

2. **ツールボックス** の **BusinessDataCatalog** グループから、**エンティティ** コントロールをデザイナーに追加します。

     新しいエンティティがデザイナーに表示されます。 Visual Studio は、 `<Entity>` プロジェクト内の BDC モデルファイルの XML に要素を追加します。 エンティティ要素の属性の詳細については、「 [entity](/previous-versions/office/developer/sharepoint-2010/ee558325(v=office.14))」を参照してください。

3. デザイナーで、エンティティのショートカットメニューを開き、[ **追加**] を選択し、[ **識別子**] を選択します。

     エンティティに新しい識別子が表示されます。

    > [!NOTE]
    > エンティティの名前と識別子は、[ **プロパティ** ] ウィンドウで変更できます。

4. クラスのエンティティのフィールドを定義します。 新しいクラスをプロジェクトに追加するか、またはオブジェクトリレーショナルデザイナー (O/R デザイナー) などの他のツールを使用して作成された既存のクラスを使用することができます。 Contact という名前のエンティティクラスの例を次に示します。

     [!code-csharp[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/CSharp/sp_bdc_entity_data_class/bdcmodel1/contact.cs#1)]
     [!code-vb[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/VisualBasic/sp_bdc_entity_data_class/bdcmodel1/contact.vb#1)]

## <a name="see-also"></a>関連項目
- [方法: Creator メソッドを追加する](../sharepoint/how-to-add-a-creator-method.md)
- [方法: 削除子メソッドを追加する](../sharepoint/how-to-add-a-deleter-method.md)
- [方法: Updater メソッドを追加する](../sharepoint/how-to-add-an-updater-method.md)
- [方法: Finder メソッドを追加する](../sharepoint/how-to-add-a-finder-method.md)
- [方法: 特定の Finder メソッドを追加する](../sharepoint/how-to-add-a-specific-finder-method.md)
