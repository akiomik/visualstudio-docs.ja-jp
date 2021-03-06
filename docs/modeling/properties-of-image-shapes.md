---
title: イメージ シェイプのプロパティ
description: イメージ図形について、およびイメージ図形を使用して生成されたデザイナーでドメインクラスを表示する方法を指定する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.selectimagedialog
- vs.dsltools.dsldesigner.imageshape
helpviewer_keywords:
- Domain-Specific Language, image shape
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 8bbd2fff30ab59d14c8aa2762d8cca942063bd79
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99918349"
---
# <a name="properties-of-image-shapes"></a>イメージ シェイプのプロパティ

イメージ図形を使用して、生成されたデザイナーでのドメインクラスの表示方法を指定できます。 `Image`クラスのプロパティを定義済みのイメージファイルに設定して、イメージシェイプを定義します。 次の形式がサポートされています。

- .gif

- .jpg

- .jpeg

- .bmp

- .wmf

- .emf

- .png

既定では、イメージファイルなどのデザイナーリソースファイルは、 **Dsl** プロジェクトの **Resources** フォルダーに配置されます。

詳細については、「 [Domain-Specific 言語を定義する方法](../modeling/how-to-define-a-domain-specific-language.md)」を参照してください。 これらのプロパティの使用方法の詳細については、「 [Domain-Specific 言語のカスタマイズと拡張](../modeling/customizing-and-extending-a-domain-specific-language.md)」を参照してください。

イメージ図形には、次の表に示すプロパティがあります。

|プロパティ|説明|Default|
|-|-|-|
|[塗りつぶしの色]|この図形の塗りつぶしの色。|白|
|塗りつぶしのグラデーションモード|この図形の塗りつぶしのグラデーションモード。|水平|
|既定の接続ポイントがある|の場合 `True` 、図形は生成されたデザイナーで top、bottom、left、および right の各接続ポイントを使用します。|False|
|輪郭の色|この図形の輪郭の色。|Black|
|輪郭の破線のスタイル|この図形の輪郭の破線のスタイル (実線、ダッシュ、ドット、ダッシュドット、ダッシュ Dotドット、またはカスタム)。|[実線]|
|アウトラインの太さ|この図形の輪郭の太さ。|0.03125|
|テキストの色|この図形に関連付けられているテキストデコレーターに使用される色。|Black|
|アクセス修飾子|ジオメトリシェイプのアクセス修飾子 (パブリックまたは内部)。|パブリック|
|カスタム属性|この図形から生成されるソースコードクラスに属性を追加するために使用します。|\<none>|
|2つの派生を生成します|`True`の場合、基本クラスと部分クラス (オーバーライドによるカスタマイズをサポートする) の両方が生成されます。 詳細については、「 [生成されたクラスのオーバーライドと拡張](../modeling/overriding-and-extending-the-generated-classes.md)」を参照してください。|False|
|カスタムコンストラクターがある|`True`の場合、カスタムコンストラクターがソースコードで提供されます。 詳細については、「 [生成されたクラスのオーバーライドと拡張](../modeling/overriding-and-extending-the-generated-classes.md)」を参照してください。|False|
|継承修飾子|イメージシェイプ ( `none` 、または) から生成されるソースコードクラスの継承の種類について説明し `abstract` `sealed` ます。|なし|
|基本イメージシェイプ|この図形の基本クラス。|(なし)|
|名前|この図形の名前。|現在の名前|
|名前空間|この図形に関連付けられている名前空間。|現在の名前空間|
|ツールヒントの種類|ツールヒントが定義されている場所 (fixed、variable、none)。 固定されている場合は、 `Fixed Tooltip Text` プロパティの値がツールヒントとして使用されます。変数の場合は、ツールヒントがカスタムコードで定義されます。|なし|
|ノート|この図形に関連付けられている非公式のメモ。|\<none>|
|初期の高さ|この図形の初期の高さ (インチ単位)。|1|
|初期の幅|この図形の初期の幅 (インチ単位)。|1.5|
|プロパティとして塗りつぶされた塗りつぶしの色<br /><br /> 露出塗りつぶしのグラデーションモード<br /><br /> プロパティとして公開されたアウトラインの色<br /><br /> プロパティとしてアウトラインの破線のスタイルを公開<br /><br /> プロパティとしてアウトラインの太さを公開<br /><br /> テキストの色を公開します|の場合 `True` 、ユーザーは図形の指定されたプロパティを設定できます。 これを設定するには、図形定義を右クリックし、[ **公開の追加**] をクリックします。|False|
|Description|生成されたデザイナーを文書化するために使用します。|\<none>|
|表示名|この図形に対して生成されたデザイナーに表示される名前。|\<none>|
|固定ツールヒントのテキスト|固定のツールヒントに使用されるテキスト。|\<none>|
|ヘルプ キーワード|この要素の F1 ヘルプのインデックスを作成するために使用されるキーワード。|\<none>|
|イメージ|この図形に使用されるイメージファイルのパス。|\<none>|

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](/previous-versions/bb126564(v=vs.100))