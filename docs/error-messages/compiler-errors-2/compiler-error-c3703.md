---
title: コンパイラ エラー C3703 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3703
dev_langs:
- C++
helpviewer_keywords:
- C3703
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 344554875e771a1a5c3412613fd77307651a5c7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264791"
---
# <a name="compiler-error-c3703"></a>コンパイラ エラー C3703
'イベント ハンドラー': イベント ハンドラー メソッドでは、ソース 'event' として同じストレージ クラスがあります  
  
 [イベント](../../cpp/event-handling.md)は、イベント ハンドラーをフックするよりも別のストレージ クラスがあります。 たとえば、このエラーは、イベント ハンドラーが、静的メンバー関数と、イベントが静的でない場合に発生します。 このエラーを解決するには、イベントとイベント ハンドラー、同じストレージ クラスを付けます。  
  
 次の例では、C3703 が生成されます。  
  
```  
// C3703.cpp  
// C3703 expected  
#include <stdio.h>  
  
[event_source(type=native)]  
class CEventSrc {  
public:  
   __event static void MyEvent();  
};  
  
[event_receiver(type=native)]  
class CEventHandler {  
public:  
   // delete the following line to resolve  
   void MyHandler() {}  
  
   // try the following line instead  
   // static void MyHandler() {}  
  
   void HookIt(CEventSrc* pSource) {  
      __hook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);  
   }  
  
   void UnhookIt(CEventSrc* pSource) {  
      __unhook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);  
   }  
};  
  
int main() {  
   CEventSrc src;  
   CEventHandler hnd;  
  
   hnd.HookIt(&src);  
   __raise src.MyEvent();  
   hnd.UnhookIt(&src);  
}  
```