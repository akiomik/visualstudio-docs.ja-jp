---
title: ソース管理情報を proj ファイルと .sln ファイルから削除します。
description: ソース管理プラグイン API では、SCC 情報は MSSCCPRJ.SCC に格納されます。プロジェクトファイルとソリューションファイルではなく SCC ファイル。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, .sln and .proj files
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 03b1c3f6e2c1cc6852ea443788bb336a03c3330f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99905813"
---
# <a name="removal-of-source-control-information-from-proj-and-sln-files"></a>Proj ファイルと .sln ファイルからのソース管理情報の削除

ソース管理プラグイン API のバージョン1.2 では、SCC 情報は MSSCCPRJ.SCC に格納されます。SCC ファイル。 MSSCCPRJ.SCC の利点。SCC ファイルとは、SCC 情報がソース管理されていないということです。これは、tfsbuild.proj ファイルや .sln ファイルなどにあります。

## <a name="version-12-changes"></a>バージョン1.2 の変更

 ソース管理プラグイン API バージョン1.1 に基づくソース管理プラグインでは、ソース管理に関する情報がプロジェクト (proj) ファイルとソリューション (.sln) ファイルに格納されます。 ソース管理情報のデータベースの場所は、「データソース」によって指定され、データベース内の特定の場所は ProjName によって指定されます。 この動作により、分岐、フォーク、またはコピー操作後に問題が発生する可能性があります。これは、これらの操作のいずれかを実行した後、ProjName が通常は無効になるためです。

 ソース管理プラグイン API バージョン1.1 では、IDE では、プラグインが MSSCCPRJ.SCC をサポートしているかどうかを検出するために、~ SAK ファイルが使用されていました。ソース管理情報を格納する SCC メソッド。 ソース管理プラグイン API バージョン1.2 には、MSSCCPRJ.SCC のサポートを検出するための新しい機能が用意されています。~ SAK ファイルを使用しない SCC ファイル。 詳細については、「 [~ SAK ファイルの削除](../../extensibility/internals/elimination-of-tilde-sak-files.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [ソース管理プラグイン API バージョン 1.2 の新機能](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)
