---
title: Weakreference::weakreference コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference, constructor
ms.assetid: 4959a9d7-78ea-423d-a46b-50d010d29fff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d506bc99d584222de55de56c9efbe40f9c71434a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593494"
---
# <a name="weakreferenceweakreference-constructor"></a>WeakReference::WeakReference コンストラクター

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
WeakReference();
```

## <a name="remarks"></a>Remarks

新しいインスタンスを初期化、 [WeakReference クラス](../windows/weakreference-class1.md)します。

強い参照ポインター、 **WeakReference**オブジェクトが初期化**nullptr**、し、強力な参照カウントは 1 に初期化されます。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)