---
title: 読み取り専用 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.readonly
dev_langs:
- C++
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 93a7adbca8c659a757e0e8fbb05b8fb926b237d2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210311"
---
# <a name="readonly-c"></a>readonly (C++)

データ メンバーへの割り当てを禁止します。

## <a name="syntax"></a>構文

```cpp
[readonly]
```

## <a name="remarks"></a>Remarks

**Readonly** C++ 属性と同じ機能を持つ、 [readonly](/windows/desktop/Midl/readonly) MIDL 属性。

メソッド パラメーターの変更を禁止する場合は、 [in](../windows/in-cpp.md) 属性を使用します。

## <a name="example"></a>例

**readonly** 属性の使用方法は、次のコードのとおりです。

```cpp
// cpp_attr_ref_readonly.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]
__interface IFireTabCtrl
{
   [readonly, id(1)] int i();
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[データ メンバー属性](../windows/data-member-attributes.md)  