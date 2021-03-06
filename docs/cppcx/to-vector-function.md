---
title: to_vector 関数 |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
dev_langs:
- C++
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00ecb00a890629c69994019c9232ff559ea93c96
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609739"
---
# <a name="tovector-function"></a>to_vector 関数
値が、指定された IVector または IVectorView パラメーターの基になるコレクションと同じである `std::vector` を返します。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename T>  
inline ::std::vector<T> to_vector(IVector<T>^ v); 
 
template <typename T>  
inline ::std::vector<T> to_vector(IVectorView<T>^ v);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 テンプレート型パラメーター。  
  
 `v`  
 基になる Vector または VectorView オブジェクトへのアクセスを提供する IVector または IVectorView インターフェイス。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>関連項目  
 [:Foundation Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)