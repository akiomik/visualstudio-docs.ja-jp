---
title: Shutdown | Microsoft Docs
description: Shutdown オプションを使用して、現在プロファイル中のプロセスが終了するかデタッチされるまで待機し、プロファイラーをオフにし、プロファイル データ ファイルを閉じる方法について学習します。
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
author: mikejo5000
ms.author: mikejo
manager: jmartens
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 455278f7fccbc9e4f80ce4f11a167e5b433ca8ab
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99950040"
---
# <a name="shutdown"></a>Shutdown
**Shutdown** オプションは、現在プロファイル中のプロセスが終了するかデタッチされるまで待機して、プロファイラーをオフにし、プロファイル データ ファイルを閉じます。 **Shutdown** オプションは、プロファイル実行の最後のコマンドである必要があります。

 タイムアウト パラメーターが指定されていない場合、**Shutdown** オプションは無期限に待機します。 タイムアウト パラメーターが指定されている場合、指定された秒数の経過後にオプションから制御が戻りますが、プロファイラーはオフにされず、データ ファイルも閉じられません。

 コマンド ラインで指定するオプションは **Shutdown** オプションのみにする必要があります。

## <a name="syntax"></a>構文

```cmd
VSPerfCmd.exe /Shutdown[:Timeout]
```

#### <a name="parameters"></a>パラメーター
`Timeout`
- (省略可能) 指定した場合は、指定した秒数の経過後にオプションから制御が戻りますが、プロファイラーはオフにされず、プロファイル データ ファイルも閉じられません。

## <a name="see-also"></a>関連項目
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [スタンドアロン アプリケーションのプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [サービスのプロファイリング](../profiling/command-line-profiling-of-services.md)
