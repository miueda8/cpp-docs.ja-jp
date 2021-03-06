---
title: 関数呼び出し (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, C++ functions
- functions [C++], calling
- operator overloading [C++], function calls
- function overloading [C++], function-call operator
- function calls, operator
- operators [C++], overloading
- operator overloading [C++], examples
- function call operator ()
ms.assetid: 5094254a-045b-46f7-8653-69bc91e80dce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2c3e28d4d69265c86e3c88d07de460558b3f71b
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409357"
---
# <a name="function-call-c"></a>関数呼び出し (C++)
かっこを使用して呼び出される関数呼び出し演算子は二項演算子です。  
  
## <a name="syntax"></a>構文  
  
```  
primary-expression ( expression-list )  
```  
  
## <a name="remarks"></a>Remarks  
 このコンテキストでは、`primary-expression` は最初のオペランドであり、`expression-list` (空の可能性がある引数リスト) は 2 番目のオペランドです。 関数呼び出し演算子は、多数のパラメーターを必要とする演算で使用されます。 これが機能するのは、`expression-list` が単一オペランドではなくリストであるためです。 関数呼び出し演算子は、非静的メンバー関数である必要があります。  
  
 関数呼び出し演算子は、オーバーロードしたとき、関数をどのように呼び出すかを変更するのではなく、特定のクラス型のオブジェクトに適用されるときに演算子をどのように解釈するかを変更します。 たとえば、次のコードは、通常、無意味です。  
  
```cpp 
Point pt;  
pt( 3, 2 );  
```  
  
 ただし、適切にオーバーロードされた関数呼び出し演算子を指定すると、この構文を使用して `x` 座標の 3 つの単位と `y` 座標の 2 つの単位をオフセットできます。 次のコードは、そのような定義を示しています。  
  
```cpp 
// function_call.cpp  
class Point  
{  
public:  
    Point() { _x = _y = 0; }  
    Point &operator()( int dx, int dy )  
        { _x += dx; _y += dy; return *this; }  
private:  
    int _x, _y;  
};  
  
int main()  
{  
   Point pt;  
   pt( 3, 2 );  
}  
```  
  
 関数呼び出し演算子は、関数の名前ではなく、オブジェクトの名前に適用されることに注意してください。  
  
 関数へのポインター (関数そのものではなく) を使用して関数呼び出し演算子をオーバーロードすることもできます。  
  
```cpp  
typedef void(*ptf)();  
void func()  
{  
}  
struct S  
{  
   operator ptf()  
   {  
      return func;  
   }  
};  
  
int main()  
{  
   S s;  
   s();//operates as s.operator ptf()()  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [演算子のオーバーロード](../cpp/operator-overloading.md)