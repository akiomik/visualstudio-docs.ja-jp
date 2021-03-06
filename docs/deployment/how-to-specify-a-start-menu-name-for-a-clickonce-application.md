---
title: ClickOnce アプリの [スタート] メニューの名前を指定する
description: '[発行オプション] ダイアログボックスで Product name を設定して、ClickOnce アプリケーションの表示名を変更する方法について説明します。'
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: a9c9dee27ae78375dcb667bba5157ea84c046073
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99940437"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>方法: ClickOnce アプリケーションのスタート メニューの名前を指定する
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションがオンラインとオフラインの両方でインストールされると、[**スタート**] メニューと [**プログラムの追加と削除**] の一覧にエントリが追加されます。 既定では、表示名はアプリケーションアセンブリの名前と同じですが、[**発行オプション**] ダイアログボックスの [**製品名**] を設定して表示名を変更できます。

 [ *publish.htm* ] ページに **製品名** が表示されます。インストールされているオフラインアプリケーションの場合は、[**スタート**] メニューのエントリの名前になり、[**プログラムの追加と削除**] に表示される名前になります。

 **発行者名** は、[ *publish.htm* ] ページの [ **製品名**] の上に表示されます。インストールされているオフラインアプリケーションの場合は、[ **スタート** ] メニューにアプリケーションのアイコンが含まれているフォルダーの名前にもなります。

 [スタート] メニューのショートカットまたはアプリの参照は、 *%Appdata%\Microsoft\Windows\Start Menu\Programs \\<発行者名 \>* で作成されます。 ショートカットまたはアプリケーションの参照には、製品名と同じ名前が付けられています。

 [**発行オプション**] ダイアログボックスでは、[**製品名**] プロパティと [発行 **元名**] プロパティを設定できます。このダイアログボックスは、**プロジェクトデザイナー** の [**発行**] ページで使用できます。

### <a name="to-specify-a-start-menu-name"></a>[スタート] メニューの名前を指定するには

1. **ソリューション エクスプローラー** でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

2. **[公開]** タブをクリックします。

3. [ **オプション** ] ボタンをクリックして、[ **発行オプション** ] ダイアログボックスを開きます。

4. [ **説明**] をクリックします。

5. [ **発行オプション** ] ダイアログボックスで、[ **製品名**] に表示する名前を入力します。

6. 必要に応じて、[ **発行者名**] に発行者名を入力できます。

## <a name="see-also"></a>関連項目
- [ClickOnce アプリケーションの発行](../deployment/publishing-clickonce-applications.md)
- [方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行する](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)