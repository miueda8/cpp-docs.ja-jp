---
title: regex_error クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
dev_langs:
- C++
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7983857b3814f8ddd9c10ab37676bc2e87e9a59c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964146"
---
# <a name="regexerror-class"></a>regex_error クラス

正しくない basic_regex オブジェクトを報告します。

## <a name="syntax"></a>構文

```cpp
class regex_error
 : public std::runtime_error {
public:
    explicit regex_error(regex_constants::error_code error);

    regex_constants::error_code code() const;


};
```

## <a name="remarks"></a>Remarks

このクラスは、 `basic_regex` オブジェクトの構築時または使用時に発生したエラーを報告するためにスローされる例外オブジェクトを表します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<regex>

**名前空間:** std

## <a name="code"></a>  regex_error::code

エラー コードを返します。

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>Remarks

このメンバー関数は、オブジェクトのコンストラクターに渡された値を返します。

### <a name="example"></a>例

```cpp
// std__regex__regex_error_code.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code()
                 "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }

```

```Output
regex error: unbalanced parentheses
```

## <a name="regex_error"></a>  regex_error::regex_error

オブジェクトを構築します。

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>パラメーター

*エラー*エラー コード。

### <a name="remarks"></a>Remarks

コンス トラクターは、値を保持するオブジェクトを構築します。*エラー*します。

### <a name="example"></a>例

```cpp
// std__regex__regex_error_construct.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code()
                 "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }

```

```Output
regex error: unbalanced parentheses
```

## <a name="see-also"></a>関連項目

[\<regex>](../standard-library/regex.md)<br/>
[regex_constants クラス](../standard-library/regex-constants-class.md)<br/>
[\<regex> 系関数](../standard-library/regex-functions.md)<br/>
[regex_iterator クラス](../standard-library/regex-iterator-class.md)<br/>
[\<regex> 系演算子](../standard-library/regex-operators.md)<br/>
[regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits クラス](../standard-library/regex-traits-class.md)<br/>
[\<regex> typedefs](../standard-library/regex-typedefs.md)<br/>
