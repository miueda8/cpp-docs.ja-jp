---
title: importidl |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9bb6c1bd23eaf705f6ceb57e5fc4ea3354c0ddfc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42571359"
---
# <a name="importidl"></a>importidl

生成された .idl ファイルには、指定された .idl ファイルを挿入します。

## <a name="syntax"></a>構文

```cpp
[ importidl(
   idl_file
) ];
```

### <a name="parameters"></a>パラメーター

*idl_file*  
アプリケーション用に生成される .idl ファイルにマージする .idl ファイルの名前を示します。

## <a name="remarks"></a>Remarks

**Importidl** C++ 属性ライブラリ ブロックの外側でセクションの配置 (で*idl_file*)、プログラムの生成された .idl ファイルとライブラリ セクションに (で*idl_file*) のプログラムのセクションは、ライブラリに .idl ファイルを生成します。

使用することがあります**importidl**、たとえば、生成された .idl ファイルを手動でコーディングの .idl ファイルを使用する場合。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](../windows/compiler-attributes.md)  
[スタンドアロン属性](../windows/stand-alone-attributes.md)  
[import](../windows/import.md)  
[importlib](../windows/importlib.md)  
[include](../windows/include-cpp.md)  
[includelib](../windows/includelib-cpp.md)  