---
title: 開発者コミュニティのガイドライン
description: Visual Studio Developer Community を利用するためのガイドラインについて説明します。
ms.date: 6/30/2020
ms.topic: conceptual
author: madskristensen
ms.author: madsk
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 0722716b086877d5522b9ef8fae79976fbdb0805
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99894674"
---
# <a name="developer-community-guidelines"></a>開発者コミュニティのガイドライン

開発者コミュニティでは、Visual Studio に関するイシューと機能の提案を追跡できます。

## <a name="submitting-problems-and-suggestions"></a>問題と提案の送信

[Visual Studio Developer Community](https://aka.ms/feedback/suggest?space=8) では、Visual Studio に関するイシューと機能の提案を追跡できます。

### <a name="before-submitting-an-issue"></a>イシューを送信する前に

Visual Studio Developer Community でイシューを検索して、それがまだ存在していないことを確認します。 イシューが既に存在する場合は、関連するコメントを作成して、投票してください。

イシューが質問の場合は、_visual-studio_ タグを使用して、[Stack Overflow](https://stackoverflow.com/questions/tagged/visual-studio?tab=Newest) でコミュニティに質問します。 そのタグを監視するカスタマー サポートのスタッフがいるので、質問への回答を Microsoft が支援します。

バグまたは機能について説明している既存のイシューが見つからない場合は、次のガイドラインを使用して問題を送信します。

### <a name="writing-a-good-bug-report-or-feature-suggestion"></a>適切なバグ報告または機能の提案の作成

- イシュー 1 件あたり、問題または機能要求を 1 件のみ報告します。

  - 複数の問題や機能要求を 1 つのイシューにまとめると、診断が困難になり、他のユーザーにとっては、イシューに投票しにくくなります。
  - 入力内容が同じ場合を除き、既存のイシューに自分のイシューをコメントとして追加しないでください。 類似するイシューは多数ありますが、原因はさまざまです。そのため、イシューの診断が困難になります。

- 提供される情報が多いほど、イシューを再現しやすくなり、修正が簡単になります。
- 各イシューには、次の手順を含めます。

  - 再現可能な手順 (1... 2... 3...)、および想定したことと経験したことの比較。
  - 画像、アニメーション、またはビデオへのリンク。 画像とアニメーションは再現手順を示していますが、それらを _置き換えないでください_。
  - 必要に応じて、イシュー、またはコード リポジトリへのリンクを示すコード スニペット。これを使用すると、マシンにプルして、イシューを簡単に再作成できます。

- 次の手順を必ず実行してください。

  - 検索して、重複が存在するかどうかを確認します。 存在する場合は、既存のイシューに投票し、必要に応じて、追加のコメントまたは説明を提供します。
  - すべての拡張機能を無効にしたうえで、イシューを再作成します。 インストールした拡張機能がそのイシューの原因であることがわかっている場合は、その拡張機能に関するイシューをそれぞれ報告します。
  - 問題をより的確に特定できるように、イシューに関するコードを簡略化します。

詳細な情報が含まれているイシューであっても、そのイシューを再現できないために、詳細情報を要求する場合があります。

## <a name="managing-problem-reports"></a>問題の報告の管理

イシューのトリアージは、複数の手順から成るプロセスであり、機能チーム内で共同作業によって実行されます。 トリアージには通常 1 週間かかりますが、それ以上かかる場合もあります。 トリアージの目的は、イシューのその後の状況について、明確に把握できるようにすることです。 たとえば、トリアージを行った後に、イシューに対して修正が計画されているのか、コミュニティからのフィードバックを待っているのかがわかります。

問題を報告した後は、提出した問題がライフサイクルのどの段階にあるかが状態で示されます。 Visual Studio 製品チームがフィードバックを検討して、適切な状態に設定します。 [問題の状態とよくあるご質問](./report-a-problem.md)に関する記事を参照して、問題の報告の進行状況を追跡します。

### <a name="prioritizing-which-issues-to-fix"></a>修正する問題の優先順位付け

報告された問題をすべて修正することはできません。 修正にコストがかかりすぎたり、他の機能領域でバグ再発を引き起こしたり、影響が小さすぎたりするものもあります。 イシュー レポートの送信に時間を費やしたならば、このような対応を残念に思われることは承知しています。 Microsoft のだれもが、このプロジェクトでも、携わった他のプロジェクトでも、同じ経験があります。 問題が解決されたものの、Microsoft が提示した理由に満足できない場合は、ユースケースを明確にして、別のパスでこのイシューをもう一度アクティブにするよう要求することができます。 このときに、Microsoft からさらに情報が求められることがあるかもしれません。

### <a name="missing-important-information"></a>重要な情報が含まれていない

Microsoft では、イシューに重要な情報が含まれていない場合、"_詳細情報が必要_" 状態を割り当てます。 必要な特定の情報と合わせてイシューについてコメントし、ユーザーは電子メール通知を受け取ります。 7 日以内に情報を受信しない場合は、ユーザーにリマインダーを送信します。 その後、14 日間の非アクティブ状態を経て、チケットを終了します。

### <a name="other-product"></a>その他の製品

イシューを報告する際に、Visual Studio ではなく、別の製品が原因となっていることがわかる場合があります。 関連する別のアプリケーションや拡張機能の場合もあります。 

このような場合は、イシューを終了し、他の製品でそのイシューをオープンするよう、ユーザーに依頼します。 このようなイシューを報告するための一般的な場所を次に示します。

* [SQL Server](https://feedback.azure.com/forums/908035-sql-server)
* [Visual Studio サブスクリプション サポート](https://feedback.azure.com/forums/908035-sql-server)
* [Office](https://support.office.com/article/how-do-i-give-feedback-on-microsoft-office-2b102d44-b43f-4dd2-9ff4-23cf144cfb11)
* [Windows](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub-app)

#### <a name="additional-information"></a>追加情報

- [パフォーマンスの問題が修正される可能性を高める方法](./how-to-increase-chances-of-performance-issue-being-fixed.md)
- [MSBuild に関する問題のトラブルシューティングとログ記録](./msbuild-logs.md)

## <a name="managing-feature-suggestions"></a>機能の提案の管理

機能の提案は、Microsoft と開発者コミュニティのメンバーとのコミュニケーション手段です。 技術的には、すべての機能要求を永続的にオープンにしておくことができます。 しかし、イシューをオープンのままにしておくと、機能の実際の状態が、コミュニティから見えにくくなってしまいます。 そのため、対応しない機能要求を終了し、対処する可能性のある機能を _[レビュー中]_ ラベルに割り当てます。

機能を提案したユーザーにとっては、自分の要求への対処が計画されないことを不満に感じるかもしれません。 そのことは理解しています。 Microsoft のだれもが、このプロジェクトや、携わった他のプロジェクトで、同じ経験があります。 どのような入力内容も歓迎していますので、ご安心ください。 自分の提案が終了していたり、 _[レビュー中]_ ラベルに割り当てられたりしていても、不満に思わないでください。 自分の機能の提案はオープンのままであるべきだと思う場合は、ユース ケースを明確化して、Microsoft に問い合わせるか、賛成票をさらに集めてください。

意思決定プロセスでは、機能の提案について次の特性を確認しています。

- 一般的な製品の方向性と一致しているか?
- ビルドと管理を許容できるか?
- 全体的な[ロードマップ](/visualstudio/productinfo/vs-roadmap)戦略に合っているか?
- 投票やコメントが示すとおりのコミュニティ サポートが得られるか?
- コミュニティ サポートが低くても、Microsoft がそれを気に入るか?

これらの質問の 1 つでも、答えが "はい" ではない場合は、終了します。 しかし、多くの場合、提案は _[レビュー中]_ としてオープンのままとなります。

提案が製品の全体的な方向性と一致しない場合は、"*スコープ外*" として閉じます。 たとえば、Visual Studio ファミリ製品の他のメンバーに同様の投資がある場合があります。 または、提案された機能は少数の人にのみ関連しているため、拡張機能を提供する方が適していることがあります。

[提案の状態とよくあるご質問](./report-a-problem.md)に関する記事を参照して、機能の提案の進行状況を追跡します。

## <a name="discussion-etiquette"></a>ディスカッションのエチケット

会話の明確さと透明性を保つには、ディスカッションを英語に限定して、常にイシューに関連した内容を扱います。 他のユーザーに気を配り、常に礼儀正しく、プロフェッショナルとして振る舞います。

詳細については、「[マイクロソフト コミュニティの使用条件](https://answers.microsoft.com/en-us/page/codeofconduct)」を参照してください。

ディスカッションのエチケットに違反する場合は、コメントが削除され、最終的に、そのユーザーは利用禁止になります。

## <a name="data-privacy"></a>データのプライバシー

コメントと返信は公開されますが、添付ファイルはすべて、Microsoft とのみプライベートに共有されます。 この可視性は、他のユーザーによって発見されたイシューや解決策をコミュニティ全体で見ることができるという利点があります。 自分のデータや ID のプライバシーについて懸念がある場合は、いくつかのオプションがあります。 詳細については、「[開発者コミュニティのデータのプライバシー](./developer-community-privacy.md)」を参照してください。

## <a name="next-steps"></a>次の手順

問題の報告、機能の提案、または既存のチケットを使用した閲覧を行うには、[Visual Studio Developer Community](https://aka.ms/feedback/suggest?space=8) にアクセスしてください。 それではお楽しみください。
