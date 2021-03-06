---
title: IsBaseOfStrict 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs:
- C++
helpviewer_keywords:
- IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e20748f1929a00084b0fb7bf16342e48e16a82b2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610126"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <
   typename Base,
   typename Derived
>

struct IsBaseOfStrict;
template <
   typename Base
>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>パラメーター

*ベース*  
基本データ型。

*派生*  
派生型。

## <a name="remarks"></a>Remarks

一方の型がもう一方の型の基本クラスであるかどうかをテストします。

最初のテンプレートが生じる場合の基本型から派生する型かどうかをテストする**true**または**false**します。 2 番目のテンプレートはから派生した型自体には、常に生成するかどうかをテストする**false**します。

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

|name|説明|
|----------|-----------------|
|[IsBaseOfStrict::value 定数](../windows/isbaseofstrict-value-constant.md)|1 つの型が別のベースであるかどうかを示します。|

## <a name="inheritance-hierarchy"></a>継承階層

`IsBaseOfStrict`

## <a name="requirements"></a>要件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)