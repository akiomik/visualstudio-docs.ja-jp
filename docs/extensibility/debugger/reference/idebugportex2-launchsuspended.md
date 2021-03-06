---
title: 'IDebugPortEx2:: LaunchSuspended |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEx2::LaunchSuspended
helpviewer_keywords:
- IDebugPortEx2::LaunchSuspended
ms.assetid: 34b2cf99-2e52-4757-8969-1d12ac517ec0
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 3cfaf6dd332f17bd934a55f700e4d28096fba8b8
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99844776"
---
# <a name="idebugportex2launchsuspended"></a>IDebugPortEx2::LaunchSuspended
実行可能ファイルを起動します。

## <a name="syntax"></a>構文

```cpp
HRESULT LaunchSuspended( 
   LPCOLESTR        pszExe,
   LPCOLESTR        pszArgs,
   LPCOLESTR        pszDir,
   BSTR             bstrEnv,
   DWORD            hStdInput,
   DWORD            hStdOutput,
   DWORD            hStdError,
   IDebugProcess2** ppPortProcess
);
```

```csharp
int LaunchSuspended( 
   string             pszExe,
   string             pszArgs,
   string             pszDir,
   string             bstrEnv,
   uint               hStdInput,
   uint               hStdOutput,
   uint               hStdError,
   out IDebugProcess2 ppPortProcess
);
```

## <a name="parameters"></a>パラメーター
`pszExe`\
から起動する実行可能ファイルの名前。 これは、パラメーターに指定されている作業ディレクトリに対する完全なパスまたは相対パスにすることができ `pszDir` ます。

`pszArgs`\
から実行可能ファイルに渡す引数。 引数がない場合は、null 値を指定できます。

`pszDir`\
から実行可能ファイルによって使用される作業ディレクトリの名前。 作業ディレクトリが不要な場合は、null 値を指定できます。

`bstrEnv`\
からNull で終わる文字列の環境ブロックの後に、追加の NULL ターミネータが続きます。

`hStdInput`\
から代替入力ストリームを処理します。 リダイレクトが不要な場合は0を指定できます。

`hStdOutput`\
から代替出力ストリームへのハンドル。 リダイレクトが不要な場合は0を指定できます。

`hStdError`\
から代替エラー出力ストリームへのハンドル。 リダイレクトが不要な場合は0を指定できます。

`ppPortProcess`\
入出力起動されたプロセスを表す [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。

## <a name="remarks"></a>解説
 このメソッドはプロセスを起動して、中断され、コードが実行されないようにする必要があります。 [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)メソッドが呼び出され、プロセスが再開されます。

 プログラムは、デバッグエンジンから起動することもできます。 詳細については、「 [プログラムの起動](../../../extensibility/debugger/launching-a-program.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)
- [プログラムの起動](../../../extensibility/debugger/launching-a-program.md)
