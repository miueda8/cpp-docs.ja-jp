---
title: コンパイラ エラー C3287 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3287
dev_langs:
- C++
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66952d5900338ec6840971678c2bbea2ebcf6bff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254433"
---
# <a name="compiler-error-c3287"></a>コンパイラ エラー C3287
型 'type' (GetEnumerator の戻り値の型) は、適切なパブリック MoveNext メンバー関数およびパブリック Current プロパティを含んでいなければなりません  
  
 ユーザー定義のコレクション クラスには、 `MoveNext` と `Current`の定義を含める必要があります。  
  
 詳細については、「 [方法: for each を使用してユーサー定義のコレクションを反復処理する](../../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C3287 が生成されます。  
  
```  
// C3287.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {  
   bool MoveNext() {  
      return true;  
   }  
   property Object^ Current {  
      Object^ get() {  
         Object ^ o = gcnew Object;  
         return o;  
      }  
   }  
};  
  
ref struct R2 {  
   R ^GetEnumerator() {  
      R^ r = gcnew R;  
      return r;  
   }  
};  
  
ref struct T {};  
  
ref struct T2 {  
   T ^GetEnumerator() {  
      T^ t = gcnew T;  
      return t;  
   }  
};  
  
int main() {  
   for each (int i in gcnew T2) {}   // C3287  
   for each (int i in gcnew R2) {}   // OK  
}  
```