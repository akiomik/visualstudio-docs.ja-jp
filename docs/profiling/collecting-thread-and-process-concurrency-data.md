---
title: スレッドとプロセスのコンカレンシー データの収集
description: プロファイル ツールのコンカレンシー プロファイル メソッドを使用して、関数のリソースへのアクセスを待機させる原因となるすべての同期イベントに関するデータを収集します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
author: mikejo5000
ms.author: mikejo
manager: jmartens
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 2f5065c3eafc9fb1cd9e36227a09bbf26ed321c6
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99950209"
---
# <a name="collect-thread-and-process-concurrency-data"></a>スレッドとプロセスのコンカレンシー データの収集

Visual Studio のプロファイリング ツールのコンカレンシー プロファイル メソッドを使用すると、プロファイリング対象のアプリケーションの機能がリソースへのアクセスを待機するすべての同期イベントに関する情報を含むリソース競合データを収集できます。

コンカレンシー プロファイル メソッドは、次のいずれかの手順を使用して指定できます。

- プロファイリング ウィザードの最初のページで **[コンカレンシー]** をクリックします
- パフォーマンス セッションの [プロパティ] ダイアログ ボックスの **[全般]** ページで、 **[コンカレンシー]** をクリックします。
- **パフォーマンス エクスプローラー** のツールバーで、 **[メソッド]** 一覧の **[コンカレンシー]** をクリックします。

## <a name="common-tasks"></a>一般的なタスク

追加のオプションを、パフォーマンス セッションの [ _パフォーマンス セッション]_ **[プロパティ ページ]** ダイアログ ボックスで指定できます。 このダイアログ ボックスを開くには:

- **パフォーマンス エクスプローラー** で、パフォーマンス セッション名を右クリックして **[プロパティ]** をクリックします。

次の表の各タスクでは、コンカレンシー メソッドを使用してプロファイリングを実行する際に、 _[パフォーマンス セッション]_ **[プロパティ ページ]** ダイアログ ボックスで指定できるオプションについて説明しています。

|タスク|関連コンテンツ|
|----------|---------------------|
|**[全般]** ページで、生成されるプロファイリング データ (.vsp) ファイルの名前付けの詳細を指定します。|- [方法: パフォーマンス データ ファイル名のオプションを設定する](../profiling/how-to-set-performance-data-file-name-options.md)|
|コード ソリューション内に複数の .exe プロジェクトがある場合は、 **[起動]** ページで、開始するアプリケーションを指定します。|- [方法: 開始するバイナリを指定する](../profiling/how-to-specify-the-binary-to-start.md)|
|**[階層の相互作用]** ページで、プロファイリング実行に ADO.NET 呼び出しデータを追加します。|- [階層相互作用データを収集する](../profiling/collecting-tier-interaction-data.md)|
|**[Windows カウンター]** ページで、プロファイリング データをマークとして追加するオペレーティング システムのパフォーマンス カウンターを 1 つ以上指定します。|- [方法: Windows カウンター データを収集する](../profiling/how-to-collect-windows-counter-data.md)|
|アプリケーション モジュールで複数のバージョンを使用する場合は、 **[詳細]** ページで、プロファイリングする .NET Framework ランタイムのバージョンを指定します。 既定では、最初に読み込まれたバージョンがプロファイリングされます。|- [方法: .NET Framework ランタイムを指定する](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|
