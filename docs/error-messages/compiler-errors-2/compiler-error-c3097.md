---
title: コンパイラ エラー C3097 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3097
dev_langs:
- C++
helpviewer_keywords:
- C3097
ms.assetid: b24bd8f8-e04f-4fbb-be57-4feb9165572e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 817e6095a0141d33352946acf52a765578dafcb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247480"
---
# <a name="compiler-error-c3097"></a>コンパイラ エラー C3097
'attribute': 属性は、'assembly:' または 'module:' と共にスコープされなければなりません  
  
 グローバル属性が正しく使用されていません。  
  
 詳細については、「 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C3097 が生成されます。  
  
```  
// C3097.cpp  
// compile with: /clr /c  
using namespace System;   
  
[AttributeUsage(AttributeTargets::All, AllowMultiple = true)]  
public ref class Attr : public Attribute {  
public:  
   Attr(int t) : m_t(t) {}  
   int m_t;  
};  
  
[Attr(10)];   // C3097  
[assembly:Attr(10)];   // OK  
  
[Attr(10)]   // OK  
public ref class MyClass {};  
```