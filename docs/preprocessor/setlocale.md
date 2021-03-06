---
title: setlocale |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
dev_langs:
- C++
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa6ba2bec5c862bb336d4b9bea0f47aad91fe0c1
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540200"
---
# <a name="setlocale"></a>setlocale
ワイド文字定数、リテラル文字列を変換するときに使用するロケール (国/地域および言語) を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma setlocale( "[locale-string]" )  
```  
  
## <a name="remarks"></a>Remarks  
 
マルチバイト文字をワイド文字に変換するアルゴリズムはロケールやコンパイルによって異なる場合や、実行可能ファイルを実行するロケールとは別のロケールでコンパイルされる場合があるため、このプラグマはコンパイル時にターゲットのロケールを指定する方法を提供します。 これによって、ワイド文字列が必ず正しい形式で保存されるようになります。  
  
既定の*ロケール文字列*は""です。  
  
"C"ロケールでは、文字列内の各文字をマップとしてその値を**wchar_t** (unsigned short 型)。 その他の値に対して有効な`setlocale`内にあるこれらのエントリには、[言語識別文字列](../c-runtime-library/language-strings.md)一覧。 たとえば、次のように発行します。  
  
```  
#pragma setlocale("dutch")  
```  
  
言語文字列を発行する機能は、コンピューター上でのコード ページおよび言語 ID のサポートによって異なります。  
  
## <a name="see-also"></a>関連項目  
 
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)