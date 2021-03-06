---
title: 生成済みクラスのオーバーライドおよび拡張
description: DSL 定義が、ドメイン固有言語に基づいた強力なツールセットを構築するためのプラットフォームであることについて説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, providing overridable classes
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 78b570601ad273a948f46d95105fcd4054419c71
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99897785"
---
# <a name="override-and-extend-the-generated-classes"></a>生成されたクラスをオーバーライドして拡張する

DSL 定義は、ドメイン固有の言語に基づいた強力なツールセットを構築できるプラットフォームです。 多くの拡張機能と適応は、DSL 定義から生成されたクラスをオーバーライドして拡張することによって作成できます。 これらのクラスには、DSL 定義図で明示的に定義したドメインクラスだけでなく、ツールボックス、エクスプローラー、シリアル化などを定義するその他のクラスも含まれています。

## <a name="extensibility-mechanisms"></a>拡張メカニズム

生成されたコードを拡張できるように、いくつかのメカニズムが用意されています。

### <a name="override-methods-in-a-partial-class"></a>部分クラスのメソッドをオーバーライドする

部分クラス定義を使用すると、クラスを複数の場所で定義できます。 これにより、自分で記述したコードから生成されたコードを分離することができます。 手動で記述したコードでは、生成されたコードによって継承されるクラスをオーバーライドできます。

たとえば、DSL 定義でという名前のドメインクラスを定義する場合、 `Book` オーバーライドメソッドを追加するカスタムコードを記述できます。

```csharp
public partial class Book
{
   protected override void OnDeleting()
   {
      MessageBox.Show("Deleting book " + this.Title);
      base.OnDeleting();
   }
}
```

> [!NOTE]
> 生成されたクラスのメソッドをオーバーライドするには、生成されたファイルから分離されたファイルに必ずコードを記述します。 通常、このファイルは、CustomCode という名前のフォルダーに格納されています。 生成されたコードに変更を加えた場合、DSL 定義からコードを再生成すると、そのコードは失われます。

オーバーライドできるメソッドを検出するには、クラスで「 **override** 」と入力し、その後にスペースを入力します。 IntelliSense ツールヒントには、オーバーライドできるメソッドが示されます。

### <a name="double-derived-classes"></a>Double-Derived クラス

生成されたクラスのメソッドのほとんどは、モデリング名前空間の固定されたクラスのセットから継承されます。 ただし、生成されるコードにはいくつかのメソッドが定義されています。 通常、これはオーバーライドできないことを意味します。1つの部分クラスで、同じクラスの別の部分定義で定義されているメソッドをオーバーライドすることはできません。

それでも、これらのメソッドをオーバーライドするには、ドメインクラスの [ **二重の派生** フラグを生成する] を設定します。 これにより、2つのクラスが生成されます。1つはもう一方の抽象基本クラスです。 すべてのメソッドとプロパティの定義は基底クラスにあり、コンストラクターだけが派生クラスに含まれています。

たとえば、サンプルライブラリの dsl では、 `CirculationBook` ドメインクラスのプロパティがに設定されてい `Generates``Double Derived` `true` ます。 このドメインクラスの生成されたコードには、次の2つのクラスが含まれています。

- `CirculationBookBase`。抽象で、すべてのメソッドとプロパティが含まれています。

- `CirculationBook`。から派生 `CirculationBookBase` します。 コンストラクターを除き、空です。

任意のメソッドをオーバーライドするには、などの派生クラスの部分定義を作成し `CirculationBook` ます。 生成されたメソッドと、モデリングフレームワークから継承されたメソッドの両方をオーバーライドできます。

このメソッドは、モデル要素、リレーションシップ、図形、図、コネクタなど、すべての種類の要素で使用できます。 その他の生成されたクラスのメソッドをオーバーライドすることもできます。 ToolboxHelper などの生成されたクラスの中には、常に二重に派生するものがあります。

### <a name="custom-constructors"></a>カスタムコンストラクター

コンストラクターをオーバーライドすることはできません。 2つの派生クラスであっても、コンストラクターは派生クラスに存在する必要があります。

独自のコンストラクターを指定する場合は、 `Has Custom Constructor` DSL 定義のドメインクラスにを設定します。 [すべての **テンプレートの変換**] をクリックすると、生成されたコードにはそのクラスのコンストラクターが含まれません。 見つからないコンストラクターの呼び出しが含まれます。 これにより、ソリューションのビルド時にエラーレポートが生成されます。 エラーレポートをダブルクリックすると、生成されるコードにコメントが表示され、何を入力すべきかを説明します。

生成されたファイルとは別のファイルに部分クラス定義を記述し、コンストラクターを指定します。

### <a name="flagged-extension-points"></a>フラグ付きの拡張ポイント

フラグ付きの拡張ポイントは DSL 定義内の場所であり、カスタムメソッドを指定するようにプロパティまたはチェックボックスを設定できます。 カスタムコンストラクターの一例を次に示します。 その他の例としては、 `Kind` 計算済みまたはカスタムのストレージへのドメインプロパティの設定、または接続ビルダーでの **カスタム** フラグの設定などがあります。

どちらの場合も、フラグを設定してコードを再生成すると、ビルドエラーが発生します。 エラーをダブルクリックすると、指定する内容を説明するコメントが表示されます。

### <a name="rules"></a>ルール

トランザクションマネージャーでは、プロパティの変更など、指定されたイベントが発生したトランザクションの終了前に実行される規則を定義できます。 通常、ルールは、ストア内の異なる要素間で synchronism を維持するために使用されます。 たとえば、ルールを使用して、モデルの現在の状態がダイアグラムに表示されるようにします。

規則はクラス単位で定義されるため、各オブジェクトに規則を登録するコードを用意する必要はありません。 詳細については、「 [ルールによってモデル内の変更が反映される](../modeling/rules-propagate-changes-within-the-model.md)」を参照してください。

### <a name="store-events"></a>ストアイベント

モデリングストアには、要素の追加と削除、プロパティ値の変更など、ストア内の特定の種類の変更をリッスンするために使用できるイベントメカニズムが用意されています。 イベントハンドラーは、変更が加えられたトランザクションの終了後に呼び出されます。 通常、これらのイベントは、ストアの外部のリソースを更新するために使用されます。

### <a name="net-events"></a>.NET イベント

図形のいくつかのイベントをサブスクライブできます。 たとえば、図形のマウスクリックをリッスンできます。 各オブジェクトのイベントをサブスクライブするコードを記述する必要があります。 このコードは、InitializeInstanceResources () のオーバーライドで記述できます。

一部のイベントは、図形でデコレーターを描画するために使用される、図形フィールドに対して生成されます。 例については、「 [方法: 図形またはデコレータのクリックをインターセプト](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)する」を参照してください。

これらのイベントは、通常、トランザクション内では発生しません。 ストアに変更を加える場合は、トランザクションを作成する必要があります。
