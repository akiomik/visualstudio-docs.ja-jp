---
title: DSL 定義のプロパティ
description: DslDefinition プロパティで、バージョン番号付けなどのドメイン固有言語定義プロパティが定義されていることについて説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, definition file
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: ef8f49e46c554efca89862c787fbfbe97c48c8f4
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99959117"
---
# <a name="properties-of-a-dsl-definition"></a>DSL 定義のプロパティ
DslDefinition プロパティは、バージョン番号付けなど *、ドメイン固有言語* 定義のプロパティを定義します。 DslDefinition プロパティは、*ドメイン固有言語デザイナー* でダイアグラムの空いている領域をクリックすると、[**プロパティ**] ウィンドウに表示されます。

 詳細については、「 [Domain-Specific 言語を定義する方法](../modeling/how-to-define-a-domain-specific-language.md)」を参照してください。 これらのプロパティの使用方法の詳細については、「 [Domain-Specific 言語のカスタマイズと拡張](../modeling/customizing-and-extending-a-domain-specific-language.md)」を参照してください。

 DslDefinition には、次の表に示すプロパティがあります。

|プロパティ|説明|Default|
|-|-|-|
|アクセス修飾子|ドメインクラスのアクセス修飾子が public か internal かを決定します。|public|
|カスタム属性|ドメインクラスのカスタム定義属性。<br /><br /> **メモ** 属性を追加するには、[参照] ボタンを使用します。|\<none>|
|会社名|システムレジストリ内の現在の会社名の名前。|現在の会社名|
|名前|このドメインクラスの名前。|現在の名前|
|名前空間|このドメインクラスに関連付けられている名前空間。|現在の名前空間|
|パッケージ Guid|この DSL 用に生成された Visual Studio パッケージの guid。|\<none>|
|パッケージ名前空間|この DSL 用に生成された Visual Studio パッケージの名前空間。|\<none>|
|製品名|この DSL 用に生成された Visual Studio パッケージに登録される製品の名前。|\<none>|
|ノート|このドメインクラスに関連付けられているメモ。|\<none>|
|説明|このドメインクラスの説明です。|\<none>|
|表示名|このドメインクラスの生成されたデザイナーに表示される名前。|\<none>|
|ヘルプ キーワード|このドメインクラスに関連付けられているヘルプキーワード。|\<none>|
|ビルド|このドメイン固有言語定義のインクリメンタルビルド番号。|0|
|メジャー バージョン|このドメイン固有言語定義の増分メジャービルド番号。|1|
|マイナー バージョン|このドメイン固有言語定義の増分マイナービルド番号。|0|
|リビジョン|このドメイン固有言語定義の増分リビジョンビルド番号。|0|

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](/previous-versions/bb126564(v=vs.100))