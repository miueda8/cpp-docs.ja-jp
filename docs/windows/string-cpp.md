---
title: 文字列 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.string
dev_langs:
- C++
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 86a6437e7a30fb92d2af66c3d657150549273cd3
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208450"
---
# <a name="string-c"></a>string (C++)

示します、1 次元**char**、 **wchar_t**、 `byte` (または同等の) このような配列へのポインターまたは配列を文字列として扱う必要があります。

## <a name="syntax"></a>構文

```cpp
[string]
```

## <a name="remarks"></a>Remarks

**文字列**C++ 属性と同じ機能を持つ、[文字列](/windows/desktop/Midl/string)MIDL 属性。

## <a name="example"></a>例

次のコードは、使用する方法を示しています**文字列**インターフェイスと typedef:。

```cpp
// cpp_attr_ref_string.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, string] typedef char a[21];
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1)] HRESULT Method3([in, string] char *pC);
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|配列またはポインター、配列、インターフェイスのパラメーター、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[配列属性](../windows/array-attributes.md)  
[export](../windows/export.md)  