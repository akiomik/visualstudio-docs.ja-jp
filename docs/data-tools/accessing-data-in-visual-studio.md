---
title: Visual Studio でのデータの使用
description: Visual Studio でデータを操作します。 ローカルコンピューター、Lan、またはパブリッククラウドまたはプライベートクラウドを介して、他のデータベース製品またはサービスのデータに接続するアプリを作成します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [Visual Studio]
- data access [Visual Studio]
- data [C#]
- ADO.NET, data access
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- data-storage
ms.openlocfilehash: b5e3d8b8cf0b2c74a5b5a862539bbf3b201b4ffd
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99859438"
---
# <a name="work-with-data-in-visual-studio"></a>Visual Studio でのデータの使用

Visual Studio では、ローカルコンピューター、ローカルエリアネットワーク、パブリッククラウド、プライベートクラウド、またはハイブリッドクラウドで、事実上すべてのデータベース製品またはサービスのデータに接続するアプリケーションを作成できます。

JavaScript、Python、PHP、Ruby、または C++ のアプリケーションでは、ライブラリを入手してコードを記述することで、他の操作と同様にデータに接続できます。 .NET アプリケーションの場合、Visual Studio には、データソースの探索、メモリ内のデータを格納および操作するためのオブジェクトモデルの作成、およびユーザーインターフェイスへのデータのバインドに使用できるツールが用意されています。 Microsoft Azure には、.NET、Java、Node.js、PHP、Python、Ruby、モバイルアプリ用の Sdk と、Azure Storage に接続するための Visual Studio のツールが用意されています。

::: moniker range="vs-2017"
次の一覧は、Visual Studio から使用できる多くのデータベースおよびストレージシステムを示しています。 [Microsoft Azure](https://azure.microsoft.com/)オファリングは、基になるデータストアのすべてのプロビジョニングと管理を含むデータサービスです。 [Visual studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download)の **azure 開発** ワークロードを使用すると、Visual studio から直接 azure データストアを操作できます。
::: moniker-end
::: moniker range=">=vs-2019"
次の一覧は、Visual Studio から使用できる多くのデータベースおよびストレージシステムを示しています。 [Microsoft Azure](https://azure.microsoft.com/)オファリングは、基になるデータストアのすべてのプロビジョニングと管理を含むデータサービスです。 [Visual studio 2019](https://visualstudio.microsoft.com/downloads)の **azure 開発** ワークロードを使用すると、Visual studio から直接 azure データストアを操作できます。
::: moniker-end

![[Azure の開発] ワークロード](media/azure-development-workload.png)

ここに記載されている他の SQL および NoSQL データベース製品のほとんどは、ローカルコンピューター、ローカルネットワーク、または仮想マシン上の Microsoft Azure でホストできます。 データベースを Microsoft Azure の仮想マシンでホストする場合は、データベース自体を管理する必要があります。

**Microsoft Azure**

- SQL Database
- Azure Cosmos DB
- ストレージ (blob、テーブル、キュー、ファイル)
- SQL Data Warehouse
- SQL Server Stretch Database
- StorSimple
- その他...

**SQL**

- SQL Server 2005-2016 (Express と LocalDB を含む)
- Firebird
- MariaDB
- MySQL
- Oracle
- PostgreSQL
- SQLite
- その他...

**NoSQL**

- Apache Cassandra
- CouchDB
- MongoDB
- NDatabase
- OrientDB |
- RavenDB
- VelocityDB
- その他...

::: moniker range="vs-2017"

多くのデータベースベンダーとサードパーティは、NuGet パッケージによる Visual Studio の統合をサポートしています。 Nuget.org または Visual Studio の nuget パッケージマネージャー ([**ツール**] [  >  **nuget パッケージマネージャー**] [  >  **ソリューションの nuget パッケージの管理**]) でオファリングを調べることができます。 その他のデータベース製品は、拡張機能として Visual Studio と統合されます。 これらの製品は、 [Visual Studio Marketplace](https://marketplace.visualstudio.com/)で参照するか、[**ツール**  >  ] [**拡張機能と更新プログラム**] に移動して、ダイアログボックスの左側のウィンドウで [**オンライン**] を選択します。 詳細については、「 [Visual Studio の互換性のあるデータベースシステム](../data-tools/installing-database-systems-tools-and-samples.md)」を参照してください。

::: moniker-end

::: moniker range=">=vs-2019"

多くのデータベースベンダーとサードパーティは、NuGet パッケージによる Visual Studio の統合をサポートしています。 Nuget.org または Visual Studio の nuget パッケージマネージャー ([**ツール**] [  >  **nuget パッケージマネージャー**] [  >  **ソリューションの nuget パッケージの管理**]) でオファリングを調べることができます。 その他のデータベース製品は、拡張機能として Visual Studio と統合されます。 これらの製品を参照するには、 [Visual Studio Marketplace](https://marketplace.visualstudio.com/)で参照するか、[**拡張** 機能の管理] に移動して、  >  ダイアログボックスの左側のウィンドウで [**オンライン**] を選択します。 詳細については、「 [Visual Studio の互換性のあるデータベースシステム](../data-tools/installing-database-systems-tools-and-samples.md)」を参照してください。

::: moniker-end

> [!NOTE]
> SQL Server 2005 の延長サポートは 2016 年 4 月 12 日で終了しました。 Visual Studio 2015 以降のデータツールが SQL Server 2005 と引き続き動作することは保証されていません。 詳細については、 [SQL Server 2005 のサポート終了](https://www.microsoft.com/sql-server/sql-server-2005)に関するお知らせを参照してください。

## <a name="net-languages"></a>.NET 言語

.NET Core を含むすべての .NET データアクセスは、ADO.NET に基づいています。これは、リレーショナルと非リレーショナルの両方の種類のデータソースにアクセスするためのインターフェイスを定義するクラスのセットです。 Visual Studio には、ADO.NET と連携して、データベースに接続し、データを操作し、データをユーザーに提示するのに役立つ、いくつかのツールとデザイナーがあります。 このセクションのドキュメントでは、これらのツールの使用方法について説明します。 ADO.NET command オブジェクトに対して直接プログラムを実行することもできます。 ADO.NET Api を直接呼び出す方法の詳細については、 [ADO.NET](/dotnet/framework/data/adonet/index)を参照してください。

ASP.NET に関連するデータアクセスドキュメントについては、ASP.NET サイトの [データの操作](https://www.asp.net/web-forms/overview/presenting-and-managing-data) に関するページを参照してください。 ASP.NET MVC での Entity Framework の使用に関するチュートリアルについては、「 [mvc 5 を使用した Entity Framework 6 Code First のはじめに](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application)」を参照してください。

C# または Visual Basic のユニバーサル Windows プラットフォーム (UWP) アプリは、Microsoft Azure SDK for .NET を使用して Azure Storage およびその他の Azure サービスにアクセスできます。 Windows の Web. HttpClient クラスは、任意の RESTful サービスとの通信を可能にします。 詳細については、「 [Windows を使用して http サーバーに接続する方法](/previous-versions/windows/apps/dn469430(v=win.10))」を参照してください。

ローカルコンピューター上のデータストレージの場合、推奨される方法は、アプリケーションと同じプロセスで実行される SQLite を使用することです。 オブジェクトリレーショナルマッピング (ORM) レイヤーが必要な場合は、Entity Framework を使用できます。 詳細については、Windows デベロッパーセンターの「 [データアクセス](/windows/uwp/data-access/index) 」を参照してください。

Azure サービスに接続する場合は、最新の [AZURE SDK ツール](https://azure.microsoft.com/downloads/)をダウンロードしてください。

### <a name="data-providers"></a>データ プロバイダー

ADO.NET で使用するデータベースには、カスタム *ADO.NET データプロバイダー* が必要です。そうでない場合は、ODBC または OLE DB インターフェイスを公開する必要があります。 Microsoft では、SQL Server 製品用の [ADO.NET データプロバイダー](/dotnet/framework/data/adonet/ado-net-overview) 、および ODBC および OLE DB プロバイダーの一覧を提供しています。

### <a name="data-modeling"></a>データ モデリング

.NET では、データソースからデータを取得した後、メモリ内のデータをモデル化して操作するための3つの選択肢があります。

[Entity Framework](../data-tools/entity-data-model-tools-in-visual-studio.md) お勧めの Microsoft ORM テクノロジ。 これを使用して、ファーストクラスの .NET オブジェクトとしてのリレーショナルデータに対するプログラミングを行うことができます。 新しいアプリケーションの場合、モデルが必要になったときの既定の最初の選択になります。 これには、基になる ADO.NET プロバイダーからのカスタムサポートが必要です。

[LINQ to SQL](../data-tools/linq-to-sql-tools-in-visual-studio2.md) 以前世代のオブジェクトリレーショナルマッパー。 これは、より複雑なシナリオに適していますが、アクティブな開発ではなくなりました。

[データセット](../data-tools/dataset-tools-in-visual-studio.md) 3つのモデリングテクノロジの中で最も古いもの。 これは主に、大量のデータを処理したり、複雑なクエリや変換を実行したりしない "フォームオーバーデータ" アプリケーションを迅速に開発するために設計されています。 DataSet オブジェクトは、.NET オブジェクトよりはるかに多くの SQL database オブジェクトに似た DataTable オブジェクトと DataRow オブジェクトで構成されています。 SQL データソースに基づく比較的単純なアプリケーションの場合でも、データセットが適している可能性があります。

これらのテクノロジを使用する必要はありません。 特にパフォーマンスが重要な場合は、DataReader オブジェクトを使用してデータベースを読み取り、必要な値を List などのコレクションオブジェクトにコピーするだけで済み \<T> ます。

## <a name="native-c"></a>ネイティブ C++

SQL Server に接続する C++ アプリケーションでは、ほとんどの場合、 [SQL Server に Microsoft® ODBC ドライバー 13.1](https://www.microsoft.com/download/details.aspx?id=53339) を使用する必要があります。 サーバーがリンクされている場合は、OLE DB が必要です。そのためには、 [SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client)を使用します。 [ODBC](/sql/odbc/microsoft-open-database-connectivity-odbc?view=sql-server-2017&preserve-view=true)または OLE DB ドライバーを直接使用して、他のデータベースにアクセスできます。 ODBC は現在の標準データベースインターフェイスですが、ほとんどのデータベースシステムは、ODBC インターフェイスを使用してアクセスできないカスタム機能を提供しています。 OLE DB は、従来の COM データアクセステクノロジであり、新しいアプリケーションでは引き続きサポートされますが、お勧めできません。 詳細については、「[Visual C++ でのデータ アクセス](/cpp/data/data-access-in-cpp)」を参照してください。

REST サービスを使用する c++ プログラムでは、 [C++ REST SDK](https://github.com/Microsoft/cpprestsdk)を使用できます。

Microsoft Azure Storage で動作する C++ プログラムは、 [Microsoft Azure Storage クライアント](https://www.nuget.org/packages/Microsoft.Azure.Storage.CPP)を使用できます。

データモデリング &mdash; Visual Studio では、C++ の ORM レイヤーは提供されていません。 [Odbc](https://www.codesynthesis.com/products/odb/) は、C++ 用の広く普及しているオープンソースの ORM です。

C++ アプリからデータベースに接続する方法の詳細については、「 [Visual Studio data tools For c++](../data-tools/visual-studio-data-tools-for-cpp.md)」を参照してください。 レガシ Visual C++ データアクセステクノロジの詳細については、「 [データアクセス](/cpp/data/data-access-in-cpp)」を参照してください。

## <a name="javascript"></a>JavaScript

[Visual Studio の JavaScript](/scripting/javascript/javascript-language-reference) は、クロスプラットフォームアプリ、UWP アプリ、クラウドサービス、web サイト、web アプリを構築するためのファーストクラスの言語です。 Visual Studio 内から Bower、Grunt、Gulp、npm、および NuGet を使用して、お気に入りの JavaScript ライブラリとデータベース製品をインストールできます。 Azure の [web サイト](https://azure.microsoft.com/)から sdk をダウンロードして、azure storage とサービスに接続します。 Edge.js は、サーバー側の JavaScript (Node.js) を ADO.NET データソースに接続するライブラリです。

## <a name="python"></a>Python

Python アプリケーションを作成するには、 [Visual Studio で python サポート](../python/overview-of-python-tools-for-visual-studio.md) をインストールします。 Azure ドキュメントには、次のようなデータへの接続に関するいくつかのチュートリアルがあります。

- [Azure での Django と SQL Database](/azure/app-service/app-service-web-get-started-python)
- [Azure 上の Django と MySQL](/azure/app-service-web/web-sites-python-ptvs-django-mysql)
- [Blob](/azure/storage/blobs/storage-quickstart-blobs-python)、[ファイル](/azure/storage/files/storage-python-how-to-use-file-storage)、[キュー](/azure/storage/queues/storage-python-how-to-use-queue-storage)、および[テーブル (Cosmo DB)](/azure/cosmos-db/table-storage-how-to-use-python)を操作します。

## <a name="related-topics"></a>関連トピック

[MICROSOFT AI プラットフォーム](https://azure.microsoft.com/overview/ai-platform/?v=17.42w) &mdash;Cortana Analytics Suite やモノのインターネットのサポートなど、Microsoft インテリジェントクラウドの概要について説明します。

[Microsoft Azure Storage](/azure/storage/) &mdash;Azure Storage について説明します。また、Azure blob、テーブル、キュー、およびファイルを使用してアプリケーションを作成する方法について説明します。

[Azure SQL Database](/azure/sql-database/) &mdash;サービスとしてのリレーショナルデータベース Azure SQL Database に接続する方法について説明します。

[SQL Server Data Tools](/sql/ssdt/download-sql-server-data-tools-ssdt) &mdash;データ接続アプリケーションとデータベースの設計、探索、テスト、および配置を簡略化するツールについて説明します。

[ADO.NET](/dotnet/framework/data/adonet/index) &mdash;ADO.NET アーキテクチャと、ADO.NET クラスを使用してアプリケーションデータを管理し、データソースと XML を操作する方法について説明します。

[ADO.NET Entity Framework](/ef/ef6/) &mdash;開発者がリレーショナルデータベースに対して直接ではなく、概念モデルに対してプログラミングを行うことができるデータアプリケーションを作成する方法について説明します。

[WCF Data Services 4.5](/dotnet/framework/data/wcf/index) &mdash;を使用して、 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] web 上または[Open Data Protocol (OData)](https://www.odata.org/)を実装するイントラネットにデータサービスを配置する方法について説明します。

[Office ソリューション](../vsto/data-in-office-solutions.md) &mdash; のデータOffice ソリューションでのデータの動作について説明するトピックへのリンクが含まれています。 スキーマ指向プログラミング、データ キャッシュ、およびサーバー側データ アクセスに関する説明が含まれます。

[LINQ (統合言語クエリ)](/dotnet/csharp/linq/) &mdash;C# および Visual Basic に組み込まれているクエリ機能と、リレーショナルデータベース、XML ドキュメント、データセット、およびメモリ内コレクションに対してクエリを実行するための一般的なモデルについて説明します。

[Visual Studio](../xml-tools/xml-tools-in-visual-studio.md) &mdash; の XML ツールXML データの操作、XSLT のデバッグ、.NET XML 機能、および XML クエリのアーキテクチャについて説明します。

[XML ドキュメントと XML データ](/dotnet/standard/data/xml/index) &mdash;.NET で XML ドキュメントとデータを操作する包括的で統合されたクラスのセットについて概要を説明します。