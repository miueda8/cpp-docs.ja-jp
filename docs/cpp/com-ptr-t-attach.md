---
title: _com_ptr_t::Attach |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c48da9a0ff3b9cadf0b7e228f3108277154e8417
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402885"
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach
**Microsoft 固有の仕様**  
  
 このスマート ポインターの型の生のインターフェイス ポインターをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
void Attach( Interface* pInterface ) throw( );  
void Attach( Interface* pInterface, bool fAddRef ) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pInterface*  
 生のインターフェイス ポインター。  
  
 *fAddRef*  
 場合は TRUE、`AddRef`が呼び出されます。 FALSE の場合、`_com_ptr_t`オブジェクト呼び出さずに生のインターフェイス ポインターの所有権を取得する`AddRef`します。  
  
## <a name="remarks"></a>Remarks  
  
-   **アタッチ (***pInterface***)** `AddRef`は呼び出されません。 インターフェイスの所有権は、この `_com_ptr_t` オブジェクトに渡されます。 `Release` 以前にカプセル化されたポインターの参照カウントをデクリメントすると呼びます。  
  
-   **アタッチ (***pInterface* **、***fAddRef***)** 場合*fAddRef*が true の場合、 `AddRef`カプセル化されたインターフェイス ポインターの参照カウントをインクリメントすると呼びます。       場合*fAddRef* false で、この`_com_ptr_t`オブジェクト呼び出さずに生のインターフェイス ポインターの所有権を取得する`AddRef`します。 `Release` 以前にカプセル化されたポインターの参照カウントをデクリメントすると呼びます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)