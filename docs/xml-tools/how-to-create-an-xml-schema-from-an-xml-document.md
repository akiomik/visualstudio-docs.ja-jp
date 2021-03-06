---
title: XML スキーマを作成する
description: Visual Studio の XML エディターを使用して、XML ドキュメントから XML スキーマ定義言語 (XSD) スキーマを作成する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 03/05/2019
ms.topic: how-to
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: e33a4add7ebc6a3e323331731f3183d7a0dce26f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99970284"
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>方法: XML ドキュメントから XML スキーマを作成する

XML エディターを使用することで、XML ドキュメントから XML スキーマ定義言語 (XSD) スキーマを作成できます。 スキーマがどのように生成されるかは、XML ファイルによって、次の方法で決定されます。

- XML ドキュメントにスキーマまたはドキュメント型定義 (DTD) が関連付けられていない場合は、新しい XML スキーマを推論するために XML ドキュメント内のデータが使用されます。

- 関連する DTD が XML ドキュメントに含まれている場合は、外部 DTD および内部サブセットが、対応する XML スキーマに変換されます。

- インラインの XDR (XML-Data Reduced) スキーマが XML ドキュメントに含まれている場合は、その XDR スキーマが、対応する XML スキーマに変換されます。

作成されたスキーマは次に、XML ファイルで IntelliSense を利用できるようにするために使用されます。

スキーマ推論エンジンの詳細については、「[XML スキーマの推論](/dotnet/standard/data/xml/inferring-an-xml-schema)」を参照してください。

## <a name="to-create-an-xml-schema"></a>XML スキーマを作成するには

1. Visual Studio で XML ファイルを開きます。

2. メニュー バーで、 **[XML]**  >  **[スキーマの作成]** を選択します。

   XML ファイル内に見つかった名前空間ごとに 1 つの XML スキーマ ドキュメントが作成され、開かれます。 各スキーマは、一時的にその他のファイルとして開かれます。 スキーマは、ディスクに保存するか、プロジェクトに追加するか、破棄することができます。

## <a name="see-also"></a>関連項目

- [XML エディター](../xml-tools/xml-editor.md)
