---
title: プロジェクトに NuGet パッケージを含める
description: このドキュメントでは、Visual Studio for Mac を使用してプロジェクトに NuGet パッケージを含める方法について説明します。 パッケージの検索およびダウンロードの手順を説明し、IDE 統合機能の概要を示します。
author: jmatthiesen
ms.author: jomatthi
ms.date: 11/09/2020
ms.assetid: 5C800815-0B13-4B27-B017-95FCEF1A0EA2
ms.custom: conceptual
ms.openlocfilehash: 46ceb99617c6a0e9ba457fdb769c1162090d1d31
ms.sourcegitcommit: 2cf3a03044592367191b836b9d19028768141470
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "94493492"
---
# <a name="install-and-manage-nuget-packages-in-visual-studio-for-mac"></a>Visual Studio for Mac に NuGet パッケージをインストールして管理する

Visual Studio for Mac 内で NuGet パッケージ マネージャー UI を使用すると、プロジェクトやソリューション内で NuGet パッケージを簡単にインストール、アンインストール、更新することができます。 パッケージを検索し、.NET Core、ASP.NET Core、Xamarin プロジェクトに追加することができます。

この記事では、プロジェクトに NuGet パッケージを含める方法について説明し、プロセスをシームレスにするツール チェーンを示します。

Visual Studio for Mac での NuGet の使用の概要については、「[クイック スタート: Visual Studio for Mac にパッケージをインストールして使用する](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)」を参照してください。

## <a name="find-and-install-a-package"></a>パッケージを検索してインストールする

1. Visual Studio for Mac でプロジェクトを開いた状態で、 **[ソリューション] ウィンドウ** 内の **[依存関係]** フォルダー (Xamarin プロジェクトを使用する場合は **[パッケージ]** フォルダー) を右クリックし、 **[NuGet パッケージの管理]** を選択します。

    ![新しい NuGet パッケージのコンテキスト アクションを追加する](media/nuget-walkthrough-packages-menu.png)

2. **[NuGet パッケージの管理]** ウィンドウが起動します。 中央の NuGet パッケージ リポジトリを検索できるように、ダイアログの左上隅にある [ソース] ドロップ ダウンを確実に `nuget.org` に設定します。

    ![Nuget パッケージのリスト](media/nuget-walkthrough-add-packages1.png)

3. `EntityFramework` などの特定のパッケージを検索するには、右上隅の検索ボックスを使用します。 使用するパッケージが見つかったら、それを選択し、**[パッケージを追加]** ボタンをクリックしてインストールを開始します。

    ![EntityFramework NuGet パッケージの追加](media/nuget-walkthrough-add-packages2.png)

4. パッケージはダウンロードされた後、プロジェクトに追加されます。 ソリューションは、編集中のプロジェクトの種類に応じて変化します。

    **Xamarin プロジェクト**
    * **[参照]** ノードには、NuGet パッケージの一部であるすべてのアセンブリのリストが含まれます。
    * **[パッケージ]** ノードには、ダウンロードした各 NuGet パッケージが表示されます。 このリストのパッケージを更新したり、削除したりすることができます。
    
    **.NET Core プロジェクト**

    * **[依存関係] > [NuGet]** ノードには、ダウンロードした各 NuGet パッケージが表示されます。 このリストのパッケージを更新したり、削除したりすることができます。

## <a name="using-nuget-packages"></a>NuGet パッケージの使用

NuGet パッケージが追加され、プロジェクト参照が更新されたら、他のプロジェクト参照の場合と同じように API に対してプログラミングできます。

必ず、必要な `using` ディレクティブをファイルの先頭に追加してください。

```csharp
using Newtonsoft.Json;
```

<a name="Package_Updates" class="injected"></a>

## <a name="updating-packages"></a>パッケージの更新

パッケージの更新は、**[依存関係]** ノード (または、Xamarin プロジェクトの場合は **[パッケージ]** ノード) を右クリックすることで、すべて一度に行うことも、パッケージごとに個別に行うこともできます。 新しいバージョンの NuGet パッケージが使用可能になると、更新アイコンが表示されます ![丸で囲まれた上向きの矢印](media/nuget-walkthrough-update-icon.png)。

コンテキスト メニューにアクセスするには、**[依存関係]** を右クリックして、**[更新]** を選択し、すべてのパッケージを更新します。

![[更新] メニューが強調表示された [依存関係] コンテキスト メニュー](media/nuget-walkthrough-packages-menu-update.png)

* **[NuGet パッケージの管理]** - プロジェクトにさらにパッケージを追加するためのウィンドウが開きます。
* **[更新]** - 各パッケージのソース サーバーを確認し、新しいバージョンをダウンロードします。
* **[復元]** - 不足しているパッケージをダウンロードします (既存のパッケージを新しいバージョンに更新しません)。

更新オプションと復元オプションはソリューション レベルでも使用でき、ソリューション内のすべてのプロジェクトに影響します。

### <a name="updating-to-pre-release-versions-of-packages"></a>パッケージのプレリリース版への更新
パッケージの新しいプレリリース版に更新するには、 **[依存関係]** を右クリックしてコンテキスト メニューを開き、 **[NuGet パッケージの管理]** メニューを選択します。

![[NuGet パッケージの管理] メニューが強調表示された [依存関係] コンテキスト メニュー](media/nuget-walkthrough-packages-menu-manage-nuget-packages.png)

ダイアログの下部にある **[プレリリース パッケージを表示する]** チェックボックスをオンにします。

![[プレリリース パッケージを表示する] オプションがオンになっている [NuGet パッケージの管理] ダイアログ](media/nuget-walkthrough-show-pre-release-packages.png)

最後に、ダイアログの **[更新プログラム]** タブで、更新するパッケージを選択し、 **[新しいバージョン]** ドロップダウンから新しいプレリリース版を選択して、 **[パッケージの更新]** をクリックします。

![[インストール済み] タブに [NuGet パッケージの管理] ダイアログが開きます。パッケージが選択され、[新しいバージョン] のドロップダウン リストが開きます。](media/nuget-walkthrough-packages-nuget-dialog-update-installed-package.png)

### <a name="locating-outdated-packages"></a>すべての古いパッケージの特定
[ソリューション] ウィンドウから、現在インストールされているパッケージのバージョンを表示し、更新するパッケージを右クリックすることができます。

![[更新]、[削除]、[更新] のオプションが表示されている [パッケージ] メニュー](media/nuget-walkthrough-PackageMenu.png)

パッケージの新しいバージョンが利用可能な場合は、パッケージ名の横に通知が表示されるので、更新するかどうかを決定できます。

![新しいパッケージ バージョンが利用可能になったときに表示される通知](media/nuget-walkthrough-package-update-available.png)

表示されるメニューには、次の 2 つのオプションがあります。

* **[更新]** - ソース サーバーを確認し、新しいバージョン (存在する場合) をダウンロードします。
* **[削除]** - このプロジェクトからパッケージを削除し、プロジェクトの参照から関連するアセンブリを削除します。

## <a name="manage-packages-for-the-solution"></a>ソリューションのパッケージの管理

ソリューションのパッケージの管理は、複数のプロジェクトを同時に操作するための便利な手段です。

1. ソリューションを右クリックし、**[NuGet パッケージの管理]** を選択します。

    ![ソリューションの NuGet パッケージの管理](media/nuget-walkthrough-manage-packages-solution.png)

1. ソリューションのパッケージを管理する場合、UI を利用して、操作によって影響を与えるプロジェクトを選択できます。

    ![ソリューションのパッケージを管理する場合のプロジェクト セレクター](media/nuget-walkthrough-add-to-projects.png)

### <a name="consolidate-tab"></a>[統合] タブ

複数のプロジェクトを含むソリューションで作業する場合、各プロジェクトで同じ NuGet パッケージを使用するすべての場所で、そのパッケージのバージョン番号についても確実に同じでものを使用することがベスト プラクティスであると考えられます。 Visual Studio for Mac を使用すると、それが簡単になります。ソリューション用のパッケージの管理を行う場合に、パッケージ マネージャー UI の **[統合]** タブを指定します。 このタブを使用すると、ソリューション内の各プロジェクトで使用されているパッケージのバージョン番号が異なる場合を容易に確認できます。

![パッケージ マネージャー UI の [統合] タブ](media/nuget-walkthrough-consolidate-tab.png)

この例の場合、NuGetDemo プロジェクトでは Microsoft.EntityFrameworkCore 2.20 が使用されていますが、NuGetDemo.Shared では Microsoft.EntityFrameworkCore 2.2.6 が使用されています。 パッケージ バージョンを統合するには、次を実行します。

- プロジェクトの一覧で、更新するプロジェクトを選択します。
- **[新しいバージョン]** リスト内で該当するすべてのプロジェクトに使用するバージョン (Microsoft.EntityFrameworkCore 3.0.0 など) を選択します。
- **[パッケージの統合]** ボタンを選択します。

パッケージ マネージャーによって、選択されたすべてのプロジェクトに対して、選択されたパッケージ バージョンがインストールされます。パッケージは **[統合]** タブ上には表示されなくなります。

## <a name="adding-package-sources"></a>パッケージ ソースの追加

インストール可能なパッケージが最初に nuget.org から取得されます。ただし、Visual Studio for Mac に他のパッケージの場所を追加することができます。 これは、開発中の独自の NuGet パッケージをテストする場合や、会社または組織内でプライベートの NuGet サーバーを使用する場合に便利です。

Visual Studio for Mac で、**[Visual Studio]、[基本設定]、[NuGet]、[ソース]** の順に移動し、パッケージ ソースのリストを表示して編集します。 ソースはリモート サーバー (URL で指定) またはローカル ディレクトリである場合があります。

![パッケージ ソース](media/nuget-walkthrough-PackageSource.png)

**[追加]** をクリックして新しいソースをセットアップします。 パッケージ ソースのフレンドリ名と URL (またはファイル パス) を入力します。 ソースがセキュリティで保護された Web サーバーの場合は、ユーザー名とパスワードも入力します。それ以外の場合はこれらの項目を空白のままにします。

![名前、場所の URL、ユーザー名、およびパスワードを入力する [パッケージ ソースを追加する] ダイアログ。](media/nuget-walkthrough-PackageSource2.png)

パッケージを検索する際に、以下のようにさまざまなソースを選択することができます。

![パッケージ ソース一覧のドロップ ダウンが表示された [パッケージ ソースを追加する] ダイアログ。](media/nuget-walkthrough-PackageSource3.png)

## <a name="version-control"></a>バージョン コントロール

NuGet のドキュメントでは、[ソース管理にパッケージをコミットせずに NuGet を使用する方法](/nuget/consume-packages/packages-and-source-control)について説明しています。 ソース管理でバイナリおよび未使用の情報を格納しない場合は、自動的にサーバーからパッケージを復元するように Visual Studio for Mac を構成することができます。 これは、開発者が初めてソース管理からプロジェクトを取得するときに、Visual Studio for Mac が自動的に必要なパッケージをダウンロードしてインストールすることを意味します。

![パッケージを自動的に復元する](media/nuget-walkthrough-AutoRestore.png)

`packages` ディレクトリを追跡対象から除外する方法の詳細については、特定のソース管理のドキュメントを参照してください。

## <a name="related-video"></a>関連ビデオ

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Using-NuGet/player]

## <a name="see-also"></a>関連項目

* [Visual Studio でパッケージをインストールして使用する (Windows)](/nuget/quickstart/install-and-use-a-package-in-visual-studio)
