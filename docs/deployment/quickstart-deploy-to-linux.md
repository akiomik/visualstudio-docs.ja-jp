---
title: App Service on Linux に発行する
description: コンテナーを使用して ASP.NET Core アプリを Azure App Service Linux に発行する方法 (継続的と 1 回限りの各オプションを含む) について学習します。
ms.custom: SEO-VS-2020
ms.date: 01/29/2019
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- azure
ms.openlocfilehash: 0371a4186d51598a79818f79719b58e122a311f2
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99927458"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>Visual Studio を使用して App Service on Linux に ASP.NET Core アプリを発行する

Visual Studio 2017 バージョン 15.7 以降では、次のいずれかの方法を使用して、ASP.NET Core アプリを (コンテナーを使用して) Azure App Service Linux に発行できます。

* アプリの継続的 (または自動的) なデプロイの場合は、[Azure Pipelines](/azure/devops/pipelines/get-started-yaml?view=azdevops&preserve-view=true) で Azure DevOps を使用します。

* アプリの 1 回限り (または手動) のデプロイの場合は、Visual Studio の **発行** ツールを使用して、App Service for Linux (コンテナーを使用) に ASP.NET Core アプリを発行します。

この記事では、1 回限りのデプロイに **発行** ツールを使用する方法について説明します。

[!INCLUDE [quickstart-prereqs-azure-linux](includes/quickstart-prereqs-azure-linux.md)]

## <a name="publish-to-azure-app-service-on-linux"></a>Azure App Service on Linux に公開する

1. ソリューション エクスプローラーで、プロジェクトを右クリックして、 **[発行]** を選択します (または **[ビルド]**  >  **[発行]** メニュー項目を使用します)。

    ![ソリューション エクスプローラーのプロジェクト コンテキスト メニューにある [発行] コマンド](../deployment/media/quickstart-publish.png "[発行] を選択する")

1. 以前に発行プロファイルを構成してある場合、 **[発行]** ウィンドウが表示されます。 **[新規]** を選択します。

1. **[発行]** ウィンドウで、 **[Azure]** を選択します。

    ![発行先を選択する](../deployment/media/quickstart-publish-azure-new.png)

1. **[Azure App Service (Linux)]** 、 **[次へ]** の順に選択します。

    ![Azure App Service on Linux を選択する](../deployment/media/quickstart-publish-linux-select-azure-service.png)

1. 必要に応じて、Azure アカウントでサインインします。 **[新しい Azure App Service の作成...]** を選択します

    ![Azure App Service の新しいインスタンスを作成するためのリンク](../deployment/media/quickstart-publish-linux-create-new-link.png)

1. **[Azure App Service の作成 (Linux)]** ダイアログで、 **[アプリ名]** 、 **[リソース グループ]** 、 **[App Service プラン]** の各入力フィールドに値が設定されます。 これらの名前を保持することも、変更することもできます。 準備ができたら、 **[作成]** を選択します。

    ![Azure App Service (Linux) の作成ダイアログのスクリーンショット。[名前]、[サブスクリプション]、[リソース グループ]、[ホスティング プラン] の各フィールドが設定されています。](../deployment/media/quickstart-publish-linux-create-new-dialog.png)

1. **[発行]** ダイアログで、新しく作成されたインスタンスが自動的に選択されています。 準備ができたら、 **[完了]** をクリックします。

    ![新しく作成された MyASpCoreWebAppOnAzure サービスが発行用の App Service として選択されている [発行] ダイアログのスクリーンショット。](../deployment/media/quickstart-publish-linux-select-instance.png)

1. **[発行]** を選びます。 Visual Studio によってアプリが Azure App Service にデプロイされ、ブラウザに Web アプリが読み込まれます。 プロジェクト プロパティの **[発行]** ウィンドウに、サイト URL とその他の詳細が示されます。

    ![プロファイルの概要を示す [発行] プロパティ ウィンドウ](../deployment/media/quickstart-publish-linux-summary-page.png)

## <a name="clean-up-resources"></a>リソースをクリーンアップする

前の手順では、リソース グループ内に Azure リソースを作成しました。 今後、これらのリソースを必要としない場合は、リソース グループを削除することでリソースを削除できます。
Azure portal の左側のメニューから、 **[リソース グループ]** 、 **[myResourceGroup]** の順に選択します。
リソース グループ ページで、リストされたリソースが削除対象であることを確認します。
**[削除]** を選択し、テキスト ボックスに「**myResourceGroup**」と入力してから、 **[削除]** を選びます。

## <a name="next-steps"></a>次の手順

このクイック スタートでは、Visual Studio を使用して、App Service on Linux にデプロイするための発行プロファイルを作成する方法を学習しました。 Azure を使用する Linux への発行に関する詳細を確認できます。

> [!div class="nextstepaction"]
> [Linux App Service](/azure/app-service/containers/app-service-linux-intro)