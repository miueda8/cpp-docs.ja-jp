---
title: "明示的な型変換演算子: () |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 09afbed7f5a399b9ca192ff57be1c866baf59626
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="explicit-type-conversion-operator-"></a>明示的な型変換演算子: ()
C++ では、関数呼び出しの構文に似た構文を使用して、明示的な型変換を実行できます。  
  
## <a name="syntax"></a>構文  
  
```  
simple-type-name ( expression-list )  
```  
  
## <a name="remarks"></a>コメント  
 A*単純な型名*続けて、*式リスト*かっこの構造体で指定された式を使用して、指定した型のオブジェクトを囲みます。 次の例は、int 型への明示的な型変換を示しています。  
  
```  
int i = int( d );  
```  
  
 次の例は、`Point`クラスです。  
  
## <a name="example"></a>例  
  
```  
// expre_Explicit_Type_Conversion_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
public:  
    // Define default constructor.  
    Point() { _x = _y = 0; }  
    // Define another constructor.  
    Point( int X, int Y ) { _x = X; _y = Y; }  
  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
    void Show()   { cout << "x = " << _x << ", "  
                         << "y = " << _y << "\n"; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
int main()  
{  
    Point Point1, Point2;  
  
    // Assign Point1 the explicit conversion  
    //  of ( 10, 10 ).  
    Point1 = Point( 10, 10 );  
  
    // Use x() as an l-value by assigning an explicit  
    //  conversion of 20 to type unsigned.  
    Point1.x() = unsigned( 20 );  
    Point1.Show();  
  
    // Assign Point2 the default Point object.  
    Point2 = Point();  
    Point2.Show();  
}  
```  
  
## <a name="output"></a>出力  
  
```  
x = 20, y = 10  
x = 0, y = 0  
```  
  
 前の例では定数を使用した明示的な型変換を示しましたが、同じ手法でオブジェクトにこのような変換を実行しても、正常に動作します。 次のコードに、このことを示します。  
  
```  
int i = 7;  
float d;  
  
d = float( i );  
```  
  
 明示的な型変換は、"キャスト" 構文を使用して指定することもできます。 キャスト構文を使用して前の例を書き換えると、次のようになります。  
  
```  
d = (float)i;  
```  
  
 キャストでの変換も関数形式の変換も、1 つの値から変換する場合は同じ結果になります。 ただし、関数形式の構文では、変換に複数の引数を指定できます。 この違いは、ユーザー定義型の場合は重要です。 `Point` クラスとその変換を考えます。  
  
```  
struct Point  
{  
    Point( short x, short y ) { _x = x; _y = y; }  
    ...  
    short _x, _y;  
};  
...  
Point pt = Point( 3, 10 );  
```  
  
 関数形式の変換を使用して、前の例では、2 つの値を変換する方法を示します (のいずれかの*x*と 1 つずつ*y*)、ユーザー定義型を`Point`です。  
  
> [!CAUTION]
>  明示的な型変換は C++ コンパイラの組み込みの型チェックをオーバーライドするため、慎重に使用してください。  
  
 [キャスト](../cpp/cast-operator-parens.md)を持たない型への変換の表記を使用する必要があります、*単純な型名*(ポインターまたは参照型であるなど)。 表すことができる型への変換、*単純な型名*いずれかの形式で記述できます。 参照してください[型指定子](http://msdn.microsoft.com/en-us/34b6c737-0ef1-4470-9b77-b26e46c0bbd4)構成要素の詳細については、*単純な型名*です。  
  
 キャスト内の型定義は無効です。  
  
## <a name="see-also"></a>関連項目  
 [後置式](../cpp/postfix-expressions.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)