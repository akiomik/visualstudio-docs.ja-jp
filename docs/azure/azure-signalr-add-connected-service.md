---
title: 接続済みサービス | を使用して Azure SignalR を追加するMicrosoft Docs
description: Azure SignalR をアプリに追加するには、Visual Studio を使用して接続済みサービスを追加します。
author: AngelosP
manager: jmartens
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 08/17/2020
ms.author: angelpe
monikerRange: '>= vs-2019'
ms.openlocfilehash: a3b76115e7d5cfe484c9aea00246e4d42acf6268
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99841160"
---
# <a name="add-azure-signalr-by-using-visual-studio-connected-services"></a>Visual Studio を使用して Azure SignalR を追加する接続済みサービス

Visual Studio では、 **接続済みサービス** 機能を使用して、次のいずれかを Azure SignalR service に接続できます。

- .NET Framework コンソールアプリ
- ASP.NET MVC (.NET Framework) 
- ASP.NET Core
- .NET Core (コンソールアプリ、WPF、Windows フォーム、クラスライブラリを含む)
- .NET Core Worker ロール
- Azure Functions
- ユニバーサル Windows プラットフォームアプリ
- Xamarin
- Cordova

接続済みサービス機能により、必要なすべての参照と接続コードがプロジェクトに追加され、構成ファイルが適切に変更されます。

> [!NOTE]
> このトピックは、Windows 上の Visual Studio に適用されます。 Visual Studio for Mac については、[Visual Studio for Mac での接続済みサービス](/visualstudio/mac/connected-services)に関するページを参照してください。
## <a name="prerequisites"></a>前提条件

- Azure ワークロードがインストールされている Visual Studio。
- サポートされている種類の1つのプロジェクト

## <a name="connect-to-azure-signalr-using-connected-services"></a>接続済みサービスを使用して Azure SignalR に接続する

1. Visual Studio でプロジェクトを開きます。

1. **ソリューションエクスプローラー** で、[**接続済みサービス**] ノードを右クリックし、コンテキストメニューの [**接続済みサービスの追加**] を選択します。

1. [ **接続済みサービス** ] タブで、 **サービスの依存関係** の [+] アイコンを選択します。

    ![サービスの依存関係の追加](./media/vs-azure-tools-connected-services-storage/vs-2019/connected-services-tab.png)

1. [ **依存関係の追加** ] ページで、[ **Azure SignalR Service**] を選択します。

    ![Azure SignalR サービスの追加](./media/azure-signalr-add-connected-service/add-signalr-service.png)

    まだサインインしていない場合は、Azure アカウントにサインインします。 Azure アカウントを持っていない場合、[無料試用版](https://azure.microsoft.com/account/free)でサインアップできます。

1. [ **Configure Azure SignalR** ] 画面で、既存の azure SignalR コンポーネントを選択し、[Next] \ ( **次へ**\) を選択します。

    新しいコンポーネントを作成する必要がある場合は、次の手順に進んでください。 それ以外の場合は、手順 7 に進みます。

    ![既存の Azure SignalR コンポーネントに接続する](./media/azure-signalr-add-connected-service/created-signalr.png)

1. Azure SignalR サービスインスタンスを作成するには:

   1. 画面の下部にある [ **新しい Azure SignalR Service インスタンスの作成** ] を選択します。

   1. **Azure SignalR サービスに入力します。 [新規作成**] 画面で、[**作成**] を選択します。

       ![新しい Azure SignalR Service インスタンス](./media/azure-signalr-add-connected-service/create-new-signalr.png)

   1. [ **Configure Azure SignalR Service** ] 画面が表示されると、新しいインスタンスが一覧に表示されます。 一覧で新しいインスタンスを選択し、[ **次へ**] を選択します。

1. 接続文字列名を入力するか、既定値を選択して、接続文字列をローカルシークレットファイルに保存するか、 [Azure Key Vault](/azure/key-vault)に格納するかを選択します。

   ![接続文字列の指定](./media/azure-signalr-add-connected-service/connection-string.png)

1. [ **変更の概要** ] 画面には、プロセスが完了した場合にプロジェクトに対して行われるすべての変更が表示されます。 変更が OK の場合は、[ **完了**] を選択します。

   ![変更の概要](./media/azure-signalr-add-connected-service/summary-of-changes.png)

1. 接続は、[**接続済みサービス**] タブの [**サービスの依存関係**] セクションに表示されます。

   ![サービスの依存関係](./media/azure-signalr-add-connected-service/service-dependencies-after.png)

## <a name="see-also"></a>関連項目

- [Azure SignalR の製品ページ](https://azure.microsoft.com/services/signalr-service/)
- [Azure SignalR Service のドキュメント](/azure/azure-signalr)
- [接続済みサービス (Visual Studio for Mac)](/visualstudio/mac/connected-services)
