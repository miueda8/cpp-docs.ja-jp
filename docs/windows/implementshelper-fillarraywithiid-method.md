---
title: Implementshelper::fillarraywithiid メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f60035ee-b7d6-4a08-966d-f88c646944c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 876f2bde68c53a27c1c40e9206b6285b8562bd91
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591140"
---
# <a name="implementshelperfillarraywithiid-method"></a>ImplementsHelper::FillArrayWithIid メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>パラメーター

*index*  
この操作の開始の配列要素を示す 0 から始まるインデックス。 この操作が完了したら、*インデックス*1 ずつインクリメントされます。

*iid*  
Iid 型の配列。

## <a name="remarks"></a>Remarks

指定した配列の要素に現在の 0 番目のテンプレート パラメーターで指定されたインターフェイス ID を挿入します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[ImplementsHelper 構造体](../windows/implementshelper-structure.md)  
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)