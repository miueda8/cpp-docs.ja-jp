---
title: is_signed クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_signed
dev_langs:
- C++
helpviewer_keywords:
- is_signed class
- is_signed
ms.assetid: 20ae44d9-22ad-4fbd-b26a-f18c62689451
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b9b58235d404b523629a0e9d24121182d1119c3
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960331"
---
# <a name="issigned-class"></a>is_signed クラス

型が符号付き整数であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_signed;
```

### <a name="parameters"></a>パラメーター

*Ty*照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*は符号付き整数型または`cv-qualified`符号付き整数型、それ以外の場合は false を保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_signed.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_signed<trivial> == " << std::boolalpha
        << std::is_signed<trivial>::value << std::endl;
    std::cout << "is_signed<int> == " << std::boolalpha
        << std::is_signed<int>::value << std::endl;
    std::cout << "is_signed<unsigned int> == " << std::boolalpha
        << std::is_signed<unsigned int>::value << std::endl;
    std::cout << "is_signed<float> == " << std::boolalpha
        << std::is_signed<float>::value << std::endl;

    return (0);
    }

```

```Output
is_signed<trivial> == false
is_signed<int> == true
is_signed<unsigned int> == false
is_signed<float> == false
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_unsigned クラス](../standard-library/is-unsigned-class.md)<br/>
