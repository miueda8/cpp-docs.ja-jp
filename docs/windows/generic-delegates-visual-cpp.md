---
title: 汎用デリゲート (Visual C) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9556aee6ef2d9d7cf10e0bb2bd24bdc61c9a0ecd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583474"
---
# <a name="generic-delegates-visual-c"></a>汎用デリゲート (Visual C++)

デリゲートでジェネリック型パラメーターを使用できます。 デリゲートの詳細については、次を参照してください。[デリゲート (C++ コンポーネント拡張)](../windows/delegate-cpp-component-extensions.md)します。

## <a name="syntax"></a>構文

```cpp
[attributes]
generic < [class | typename] type-parameter-identifiers>
[type-parameter-constraints-clauses]
[accessibility-modifiers] delegate result-type identifier
([formal-parameters]);
```

### <a name="parameters"></a>パラメーター

*属性*(省略可能)  
追加の宣言情報。 属性と属性クラスの詳細については、属性を参照してください。

*type-parameter-identifier(s)*  
型パラメーターの識別子のコンマ区切りリスト。

*型パラメーター制約句*  
指定された形式の[ジェネリック型パラメーターの制約 (C +/cli CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)

*アクセシビリティ修飾子*(省略可能)  
アクセシビリティ修飾子 (例:**パブリック**、**プライベート**)。

*result-type*  
デリゲートの戻り値の型。

*identifier*  
デリゲートの名前。

*仮パラメーター* (省略可能)  
デリゲートのパラメーターのリスト。

## <a name="example"></a>例

デリゲートの型パラメーターは、デリゲート オブジェクトが作成されている時点で指定されます。 デリゲートとそれに関連付けられているメソッドの両方が同じシグネチャを持つ必要があります。 次は、汎用デリゲートの宣言の例です。

```cpp
// generics_generic_delegate1.cpp
// compile with: /clr /c
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);
```

## <a name="example"></a>例

次の例を表示します。

- 同じデリゲート オブジェクトは、異なる構築された型を使用できません。 別のデリゲートにさまざまな種類のオブジェクトを作成します。

- 汎用デリゲートは、ジェネリック メソッドを関連付けることができます。

- ジェネリック メソッドが型引数を指定せずに呼び出されると、コンパイラは呼び出しの型引数の推論しようとします。

```cpp
// generics_generic_delegate2.cpp
// compile with: /clr
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);

generic <class ItemType>
ref struct MyGenClass {
   ItemType MyMethod(ItemType i, ItemType % j) {
      return ItemType();
   }
};

ref struct MyClass {
   generic <class ItemType>
   static ItemType MyStaticMethod(ItemType i, ItemType % j) {
      return ItemType();
   }
};

int main() {
   MyGenClass<int> ^ myObj1 = gcnew MyGenClass<int>();
   MyGenClass<double> ^ myObj2 = gcnew MyGenClass<double>();
   GenDelegate<int>^ myDelegate1 =
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);

   GenDelegate<double>^ myDelegate2 =
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);

   GenDelegate<int>^ myDelegate =
      gcnew GenDelegate<int>(&MyClass::MyStaticMethod<int>);
}
```

## <a name="example"></a>例

次の例は、汎用デリゲートを宣言`GenDelegate<ItemType>`、し、メソッドに関連付けることによってインスタンス化`MyMethod`型パラメーターを使用する`ItemType`します。 (整数と double) デリゲートの 2 つのインスタンスが作成され、呼び出されます。

```cpp
// generics_generic_delegate.cpp
// compile with: /clr
using namespace System;

// declare generic delegate
generic <typename ItemType>
delegate ItemType GenDelegate (ItemType p1, ItemType% p2);

// Declare a generic class:
generic <typename ItemType>
ref class MyGenClass {
public:
   ItemType MyMethod(ItemType p1, ItemType% p2) {
      p2 = p1;
      return p1;
    }
};

int main() {
   int i = 0, j = 0;
   double m = 0.0, n = 0.0;

   MyGenClass<int>^ myObj1 = gcnew MyGenClass<int>();
   MyGenClass<double>^ myObj2 = gcnew MyGenClass<double>();

   // Instantiate a delegate using int.
   GenDelegate<int>^ MyDelegate1 =
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);

   // Invoke the integer delegate using MyMethod.
   i = MyDelegate1(123, j);

   Console::WriteLine(
      "Invoking the integer delegate: i = {0}, j = {1}", i, j);

   // Instantiate a delegate using double.
   GenDelegate<double>^ MyDelegate2 =
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);

   // Invoke the integer delegate using MyMethod.
   m = MyDelegate2(0.123, n);

   Console::WriteLine(
      "Invoking the double delegate: m = {0}, n = {1}", m, n);
}
```

```Output
Invoking the integer delegate: i = 123, j = 123
Invoking the double delegate: m = 0.123, n = 0.123
```

## <a name="see-also"></a>関連項目

[ジェネリック](../windows/generics-cpp-component-extensions.md)