---
title: コンパイラ エラー C2714 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2714
dev_langs:
- C++
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b012acdebd5ccddb056d9558bb1034ac2ba0b49
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235161"
---
# <a name="compiler-error-c2714"></a>コンパイラ エラー C2714
__alignof(void) は許可されていません  
  
 無効な値は、演算子に渡されました。  
  
 参照してください[_ _alignof 演算子](../../cpp/alignof-operator.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では、C2714 を生成します。  
  
```  
// C2714.cpp  
int main() {  
   return __alignof(void);   // C2714  
   return __alignof(char);   // OK  
}  
```