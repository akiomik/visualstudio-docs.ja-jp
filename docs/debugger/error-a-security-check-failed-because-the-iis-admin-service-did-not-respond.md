---
title: IIS 管理サービスが応答しないため、セキュリティ チェックに失敗しました | Microsoft Docs
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.iis_not_responding
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: e64947beb30b5abc4649fc65d8d566a7dedb55a3
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99871833"
---
# <a name="error-a-security-check-failed-because-the-iis-admin-service-did-not-respond"></a>エラー :IIS 管理サービスが応答しないため、セキュリティ チェックに失敗しました
このエラーは、IIS Admin サービスが応答しないときに発生します。 これは通常、IIS のインストールに問題があることを意味します。 まず、 **[管理ツール]** の **[サービス]** ツールを使用して、サービスが実行中であることを確認します。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- コントロール パネルの **[プログラムの追加と削除]** を使って、IIS を再インストールします。

- \- または -

- コントロール パネルの [アプリケーションの追加と削除] を使って、コンピューターから IIS を削除します。 IIS を削除しても問題が解決しない場合は、レジストリをチェックして、次のキーが存在しないことを確認します。

    `HKEY_CLASSES_ROOT\CLSID\{A9E69610-B80D-11D0-B9B9-00A0C922E750}`

     \- または -

- コントロール パネルの [管理ツール] を使って、IIS Admin サービスを無効にします。 これによって、コンピューター上の IIS は無効になります。

     この 3 つの手順のいずれかを実行した後は、コンピューターを再起動します。

     詳細については、IIS のドキュメントを参照してください。

## <a name="see-also"></a>関連項目
- [Web アプリケーションのデバッグ: エラーとトラブルシューティング](../debugger/debugging-web-applications-errors-and-troubleshooting.md)