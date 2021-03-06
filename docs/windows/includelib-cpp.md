---
title: includelib (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.includelib
dev_langs:
- C++
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 551ae176504e3bbbca034ca91894ef793ea268fd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42584343"
---
# <a name="includelib-c"></a>includelib (C++)

生成された .idl ファイルに含まれる、.idl ファイルまたは .h ファイル。

## <a name="syntax"></a>構文

```cpp
[ includelib(
   name.idl
) ];
```

### <a name="parameters"></a>パラメーター

*name.idl*  
生成された .idl ファイルの一部として含めるする .idl ファイルの名前。

## <a name="remarks"></a>Remarks

**Includelib** C++ 属性により、.idl ファイルまたは .h ファイルの後、生成された .idl ファイルに含まれる、`importlib`ステートメント。

## <a name="example"></a>例

次のコードは、.cpp ファイルで示されます。

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|[はい]|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[スタンドアロン属性](../windows/stand-alone-attributes.md)  
[import](../windows/import.md)  
[importidl](../windows/importidl.md)  
[include](../windows/include-cpp.md)  
[importlib](../windows/importlib.md)  