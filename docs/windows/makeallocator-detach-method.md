---
title: Makeallocator::detach メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: 78012634-2dda-4ea2-9ffe-40f105d2fe47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d609b685bb5e3d24d561e66050769b6b7728e691
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607163"
---
# <a name="makeallocatordetach-method"></a>MakeAllocator::Detach メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
__forceinline void Detach();
```

## <a name="remarks"></a>Remarks

によって割り当てられたメモリの関連付けを解除、 [Allocate](../windows/makeallocator-allocate-method.md)メソッドは、現在から**MakeAllocator**オブジェクト。

呼び出す場合**Detach()**、によって提供されるメモリの削除を担当、`Allocate`メソッド。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[MakeAllocator クラス](../windows/makeallocator-class.md)  
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)