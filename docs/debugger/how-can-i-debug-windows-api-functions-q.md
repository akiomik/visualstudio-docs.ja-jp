---
title: Windows API 関数をデバッグする |Microsoft Docs
Description: NT シンボルを読み込んだ状態で Windows API 関数をデバッグする方法について説明します。 32 ビット コードでは、関数名の装飾形式を使用してブレークポイントを設定します。
ms.custom: SEO-VS-2020, seodec18
ms.date: 06/03/2020
ms.topic: how-to
f1_keywords:
- vs.debug.api
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], Windows API functions
- NT symbols and debugging Windows API functions
- Windows API functions, debugging
- Windows API, debugging API functions
- APIs, debugging
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: e1bd0a31f99812efefe937ce179b8f23d66c38d4
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99904300"
---
# <a name="how-can-i-debug-windows-api-functions"></a>Windows API 関数をデバッグするには
NT シンボルを読み込んだ状態で Windows API 関数をデバッグするには、次の手順を実行する必要があります。

### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>NT シンボルを読み込んだ状態で Windows API 関数にブレークポイントを設定するには

- [関数のブレークポイント](../debugger/using-breakpoints.md#BKMK_Set_a_breakpoint_in_a_source_file)に、関数が存在する DLL の名前と共に関数名を入力します ([コンテキスト演算子](../debugger/context-operator-cpp.md)に関するページを参照してください)。 32 ビット コードでは、関数名の装飾形式を使用します。 たとえば、**MessageBeep** にブレークポイントを設定するには、次のように入力します。

    ```cpp
    {,,USER32.DLL}_MessageBeep@4
    ```

     装飾名を取得するには、「[装飾名の表示](/previous-versions/5x49w699(v=vs.140))」を参照してください 。

     装飾名をテストし、逆アセンブリ コードで表示できます。 Visual Studio デバッガーの関数で一時停止しているときに、コード エディターまたは呼び出し履歴ウィンドウで関数を右クリックし、 **[逆アセンブリへ移動]** を選択します。

- 64 ビット コードでは、非装飾名を使用できます。

    ```cpp
    {,,USER32.DLL}MessageBeep
    ```

## <a name="see-also"></a>関連項目
- [ネイティブ コードのデバッグに関する FAQ](../debugger/debugging-native-code-faqs.md)
- [ネイティブ コードのデバッグ](../debugger/debugging-native-code.md)