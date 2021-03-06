---
title: 'IPropertyProxyEESide:: GetManagedViewerCreationData |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
helpviewer_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
ms.assetid: c4eb4d60-8816-4d52-bc8d-dffd4f066499
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ee551ba78ceb91c2622af217d8863597e028be9d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "99896013"
---
# <a name="ipropertyproxyeesidegetmanagedviewercreationdata"></a>IPropertyProxyEESide::GetManagedViewerCreationData
ビューアーをインスタンス化するために、このプロパティ型のビューアーに関する情報を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetManagedViewerCreationData(
   BSTR*                  assemName,
   IEEDataStorage**       assemBytes,
   IEEDataStorage**       assemPdb,
   BSTR*                  className,
   ASSEMBLYLOCRESOLUTION* alr,
   BOOL*                  replacementOk
);
```

```csharp
int GetManagedViewerCreationData(
   out string                     assemName,
   out IEEDataStorage             assemBytes,
   out IEEDataStorage             assemPdb,
   out string                     className,
   out enum_ASSEMBLYLOCRESOLUTION alr,
   out int                        replacementOk
);
```

## <a name="parameters"></a>パラメーター
`assemName`\
入出力このオブジェクトを保持しているアセンブリの名前を返します。

`assemBytes`\
入出力このオブジェクトのアセンブリバイトを格納している [Ieedatastorage](../../../extensibility/debugger/reference/ieedatastorage.md) オブジェクトを返します (バイトが使用できない場合は null 値です)。

`assemPdb`\
入出力 `IEEDataStorage` このオブジェクトのシンボルストア情報を格納しているオブジェクトを返します (シンボルストアが使用できない場合は null 値です)。

`className`\
入出力このオブジェクトを格納しているクラス名を返します。

`alr`\
入出力アセンブリの場所を示す値を [Assemblylocresolution](../../../extensibility/debugger/reference/assemblylocresolution.md) 列挙から返します。

`replacementOk`\
入出力`TRUE`このオブジェクトの値を変更できる場合は0以外 () を返します。オブジェクトが読み取り専用の場合は 0 () を返し `FALSE` ます。

## <a name="return-value"></a>戻り値
 成功した場合はを返し `S_OK` ます。それ以外の場合はエラーコードを返します。

## <a name="remarks"></a>解説
 このメソッドは、マネージビューアーをインスタンス化するために型ビジュアライザーによって使用されます。

## <a name="see-also"></a>関連項目
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
