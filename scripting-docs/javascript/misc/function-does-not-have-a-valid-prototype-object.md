---
title: 関数に有効なプロトタイプオブジェクト | がありません。Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: error-reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b9e34652-190f-4b57-b253-df2e8c4d09c6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 15b00087cd66b873044b7bafb1bfecf4fc91f8d9
ms.sourcegitcommit: e38419bb842d587fd9e37c24b6cf3fc5c2e74817
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "91862399"
---
# <a name="function-does-not-have-a-valid-prototype-object"></a>関数には、有効なプロトタイプ オブジェクトが存在しません。
**Instanceof**を使用して、オブジェクトが特定の関数クラスから派生したかどうかを判断しようとしましたが、オブジェクトの `prototype` プロパティを `null` または外部オブジェクト型 (両方とも有効なオブジェクト) として再定義しました [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 。 外部オブジェクトには、ホストオブジェクトモデル (Internet Explorer のドキュメントまたはウィンドウオブジェクトなど) のオブジェクト、または外部 COM オブジェクトを指定できます。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 関数のプロパティが `prototype` 有効なオブジェクトを参照していることを確認し [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ます。  
  
## <a name="see-also"></a>関連項目  
 [関数オブジェクト](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Function)   
 [prototype プロパティ (Object)](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)