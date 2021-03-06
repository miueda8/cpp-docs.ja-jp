---
title: 関数の移動 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
dev_langs:
- C++
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fc1d0c7ed8655037eebfc12097789253b3027e9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603896"
---
# <a name="move-function"></a>Move 関数

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>パラメーター

*T*  
引数の型。

*arg*  
移動する引数。

## <a name="return-value"></a>戻り値

パラメーター *arg*参照または右辺値参照の特徴の後に存在する場合、削除されました。

## <a name="remarks"></a>Remarks

指定した引数を 1 つの場所から移動します。

詳細については、次を参照してください。、**移動セマンティクス**の[右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)