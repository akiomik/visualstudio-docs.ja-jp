---
title: ClickOnce 発行バージョンの自動インクリメント
description: Visual Studio を使用して ClickOnce アプリケーションのリビジョン番号の自動インクリメントを無効にする方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], incrementing publish version automatically
- Publish Version property, incrementing
- ClickOnce deployment, incrementing publish version automatically
- publishing, ClickOnce
ms.assetid: 686ab88a-6305-4914-a05b-fe269cc0ae1e
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: b84b0a8932bb9d8fd4738c2cd4924b61bb6faeb7
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99947776"
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>方法: ClickOnce の発行するバージョンを自動的にインクリメントする

アプリケーションを公開するときに、プロパティを変更すると、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] `Publish Version` アプリケーションが更新プログラムとして発行されます。 既定では、アプリケーションを発行するたびに、Visual Studio によっての数が自動的に増加し `Revision` `Publish Version` ます。

この動作は、**プロジェクトデザイナー** の [**発行**] ページで無効にすることができます。

> [!NOTE]
> 実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[リセット設定](../ide/environment-settings.md#reset-settings)」を参照してください。

## <a name="to-disable-automatically-incrementing-the-publish-version"></a>発行バージョンを自動的にインクリメントしないようにするには

1. **ソリューション エクスプローラー** でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

2. **[公開]** タブをクリックします。

3. [ **発行バージョン** ] セクションで、[ **リリースごとにリビジョンを自動的にインクリメント** する] チェックボックスをオフにします。

## <a name="see-also"></a>関連項目

- [方法: ClickOnce の発行バージョンを設定する](../deployment/how-to-set-the-clickonce-publish-version.md)
- [ClickOnce アプリケーションの発行](../deployment/publishing-clickonce-applications.md)
- [方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行する](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)