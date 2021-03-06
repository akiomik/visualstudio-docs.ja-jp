---
title: SetCurrentProcess
description: SetCurrentProcess コマンドについて、およびそれを使用して指定されたプロセスをデバッガーでアクティブなプロセスとして設定する方法について説明します。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: cef9475e9336acd5c10cee604d453706ea7321c5
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99957804"
---
# <a name="set-current-process"></a>SetCurrentProcess
指定されたプロセスをデバッガーでアクティブなプロセスとして設定します。

## <a name="syntax"></a>構文

```cmd
Debug.SetCurrentProcess index
```

## <a name="arguments"></a>引数
`index`

必須です。 プロセスのインデックスです。

## <a name="remarks"></a>解説
デバッグ中には複数のプロセスにアタッチできますが、デバッガーでアクティブになっているプロセスは常に 1 つだけです。 `SetCurrentProcess` コマンドを使用すると、アクティブなプロセスを設定できます。

## <a name="example"></a>例

```cmd
>Debug.SetCurrentProcess 1
```

## <a name="see-also"></a>関連項目

- [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)
- [コマンド ウィンドウ](../../ide/reference/command-window.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
