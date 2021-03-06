---
title: ClickOnce キャッシュの概要 |Microsoft Docs
description: Clickonce アプリケーションキャッシュについて説明します。 clickonce アプリケーションキャッシュには、ClickOnce アプリケーションが格納されているクライアントコンピューター上の隠しディレクトリが含まれています。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployemtn
- ClickOnce applications, cache
- ClickOnce deployment, cache
ms.assetid: e379921e-9ef1-4326-bbf3-53ba67925526
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 12c14850717688b17caed2fbe7feb546e0ebdb6e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99936172"
---
# <a name="clickonce-cache-overview"></a>ClickOnce キャッシュの概要
ローカルにインストールされているか、オンラインでホストされているすべての [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションは、クライアントコンピューターのアプリケーションキャッシュに格納され [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ます。  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]キャッシュは、現在のユーザーの [ドキュメントと設定] フォルダーの [ローカル設定] ディレクトリにある非表示ディレクトリのファミリです。 このキャッシュは、アセンブリ、構成ファイル、アプリケーションとユーザー設定、およびデータディレクトリを含む、アプリケーションのすべてのファイルを保持します。 キャッシュは、アプリケーションのデータディレクトリを最新バージョンに移行する役割も担います。 データ移行の詳細については、「 [ClickOnce アプリケーションにおけるローカルデータおよびリモートデータへのアクセス](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)」を参照してください。

 アプリケーションストレージ用に1つの場所を提供することにより、は、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ユーザーからアプリケーションの物理的なインストールを管理するタスクを引き継ぎます。 また、キャッシュは、すべてのアプリケーションのアセンブリとデータファイルと、個別のバージョンを相互に分離して、アプリケーションを分離するのにも役立ちます。 たとえば、アプリケーションをアップグレードすると、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] そのバージョンとそのデータリソースはキャッシュ内に独自のディレクトリと共に提供されます。

## <a name="cache-storage-quota"></a>キャッシュストレージクォータ
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] オンラインでホストされているアプリケーションは、キャッシュのサイズを制限するクォータによって占有される領域の量に制限され [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ます。 キャッシュサイズは、すべてのユーザーのオンラインアプリケーションに適用されます。部分的に信頼された1つのオンラインアプリケーションは、クォータ領域の半分に制限されます。 インストールされているアプリケーションはキャッシュサイズによって制限されず、キャッシュの制限にはカウントされません。 すべてのアプリケーションについて、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] キャッシュには現在のバージョンと以前にインストールされたバージョンのみが保持されます。

 既定では、クライアントコンピューターには、オンラインアプリケーション用に 250 MB の記憶域があり [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ます。 データファイルは、この制限にはカウントされません。 システム管理者は、レジストリキーの **HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment\OnlineAppQuotaInKB** を変更することにより、特定のクライアントコンピューターのこのクォータを拡大または縮小できます。これは、キャッシュサイズを kb 単位で表す DWORD 値です。 たとえば、キャッシュサイズを 50 MB に減らすために、この値を51200に変更します。

## <a name="see-also"></a>関連項目
- [ClickOnce アプリケーションにおけるローカル データおよびリモート データへのアクセス](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)