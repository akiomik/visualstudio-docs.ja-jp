---
title: Office ソリューションのローカルデータベースファイルの使用の概要
description: SQL Server Express (.mdf) ファイルや Microsoft Office Access (.mdb) ファイルなどのデータベースファイルを Office ソリューションに含める方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- data [Office development in Visual Studio], local
- local data [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 857038700a29f423250f006e743152bceea43c14
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99838233"
---
# <a name="use-local-database-files-in-office-solutions-overview"></a>Office ソリューションのローカルデータベースファイルの使用の概要
  Office ソリューションには、SQL Server Express (*.mdf*) ファイルや Microsoft Office Access (*.mdb*) ファイルなどのデータベースファイルを含めることができます。 これにより、エンドユーザーは、1台のコンピューターでのみ使用されるローカルインベントリソリューションなど、集中管理されたデータベースを保持する必要がない場合に、ローカルデータベースを管理できます。

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

## <a name="import-the-database-file-into-a-project"></a>データベースファイルをプロジェクトにインポートする
 データベースファイルをプロジェクトにインポートするには、 **データソース構成ウィザード** を使用して、データベースファイルに基づいてデータソースを作成します。 ウィザードによって、データベースファイルと型指定されたデータセットがプロジェクトに追加されます。

## <a name="deploy-the-database-file"></a>データベースファイルの配置
 **データソース構成ウィザード** は、相対パスを使用して、ローカルデータベースファイルへの接続を作成します。 これにより、ファイルの相対位置を維持している場合に、ソリューションをあるコンピューターから別のコンピューターにコピーすることができます。

 ソリューションをサーバーに配置してから、ドキュメントを各エンドユーザーに配布する場合は、データベースファイルを手動で配布し、ドキュメントと同じ位置にインストールする必要もあります。 つまり、エンドユーザーは、データベースファイルを移動しない限り、自分のコンピューター上の新しい場所にドキュメントを移動することはできません。

## <a name="local-database-files-and-caching-the-dataset"></a>ローカルデータベースファイルとデータセットのキャッシュ
 Microsoft Office Excel と Microsoft Office Word のドキュメントレベルのソリューションでは、データセットインスタンスを属性でマークすることによって、ドキュメント内のデータセットをキャッシュすることができ <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> ます。 **データソース構成ウィザード** を使用してデータベースファイルをプロジェクトに追加すると、型指定されたデータセットがプロジェクトに自動的に追加されます。 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>データは既にユーザーのコンピューター上にローカルにあるため、このデータセットに適用する必要はほとんどありません。 詳細については、「 [データのキャッシュ](../vsto/caching-data.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [Office ソリューションのコントロールにデータをバインドする](../vsto/binding-data-to-controls-in-office-solutions.md)
- [方法: データベースのデータをドキュメントに読み込む](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [方法: ホストコントロールのデータを使用してデータソースを更新する](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Office ソリューションの配置](../vsto/deploying-an-office-solution.md)
- [キャッシュ データ](../vsto/caching-data.md)
