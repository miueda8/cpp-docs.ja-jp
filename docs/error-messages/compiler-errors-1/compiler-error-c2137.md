---
title: コンパイラ エラー C2137 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2137
dev_langs:
- C++
helpviewer_keywords:
- C2137
ms.assetid: 984687ee-7766-4f6b-ae15-0c9a010e2366
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1d546270b5f3edd71dbc0c68f2f40a6e7ba6343
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164386"
---
# <a name="compiler-error-c2137"></a>コンパイラ エラー C2137
空の文字定数  
  
 空の文字定数 (' ') は許可されていません。  
  
 次の例では C2137 が生成されます。  
  
```  
// C2137.cpp  
int main() {  
   char c = '';   // C2137  
   char d = ' ';   // OK  
}  
```