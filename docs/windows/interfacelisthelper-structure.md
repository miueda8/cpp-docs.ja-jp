---
title: InterfaceListHelper 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
dev_langs:
- C++
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b2336562abb82ae89bd2f6864d0678023a3ccf69
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600529"
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <
   typename T0,
   typename T1 = Nil,
   typename T2 = Nil,
   typename T3 = Nil,
   typename T4 = Nil,
   typename T5 = Nil,
   typename T6 = Nil,
   typename T7 = Nil,
   typename T8 = Nil,
   typename T9 = Nil
>
struct InterfaceListHelper;

template <
   typename T0
>
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;
```

### <a name="parameters"></a>パラメーター

*T0*  
テンプレート パラメーター 0 の場合は必要です。

*T1*  
テンプレート パラメーター 1 が既定では指定されていません。

*T2*  
テンプレート パラメーター 2、既定では指定されていません。3 番目のテンプレート パラメーター。

*T3*  
テンプレート パラメーター 3、既定では指定されていません。

*T4*  
テンプレート パラメーター 4、既定では指定されていません。

*T5*  
テンプレート パラメーター 5、既定では指定されていません。

*T6*  
テンプレート パラメーター 6、既定では指定されていません。

*T7*  
テンプレート パラメーター 7 では、既定では指定されていません。

*T8*  
テンプレート パラメーター 8 では、既定では指定されていません。

*T9*  
テンプレート パラメーター 9、既定では指定されていません。

## <a name="remarks"></a>Remarks

ビルド、`InterfaceList`型パラメーターの引数が指定したテンプレートの適用を再帰的にします。

**InterfaceListHelper**テンプレートがテンプレート パラメーターを使用して*T0*の最初のデータ メンバーを定義する、`InterfaceList`構造、および、再帰的に適用されます、 **InterfaceListHelper**テンプレートの残りのテンプレート パラメーター。 **InterfaceListHelper**残りのテンプレート パラメーターがない場合は停止します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`TypeT`|InterfaceList 型のシノニム。|

## <a name="inheritance-hierarchy"></a>継承階層

`InterfaceListHelper`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)