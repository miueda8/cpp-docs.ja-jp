---
title: コンパイラの警告 (レベル 1) C4003 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4003
dev_langs:
- C++
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a90202bfc06d50089e2ac283a5060bc431b9549c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274259"
---
# <a name="compiler-warning-level-1-c4003"></a>コンパイラの警告 (レベル 1) C4003
マクロ 'identifier' に指定された実引数の数が少なすぎます  
  
 マクロ定義の仮パラメーターの数は、マクロの実引数の数を超えています。 マクロの展開には、不足しているパラメーターに空のテキストが置換されます。  
  
 次の例では、C4003 が生成されます。  
  
```  
// C4003.cpp  
// compile with: /WX  
#define test(a,b) (a+b)  
  
int main()  
{  
   int a = 1;  
   int b = 2;  
   a = test(b);   // C4003  
   // try..  
   a = test(a,b);  
}  
```