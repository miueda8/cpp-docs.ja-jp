---
title: Comptrrefbase::operator IInspectable * * 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs:
- C++
helpviewer_keywords:
- operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f711a9d1f5fe92e5f35bf333fc0b3473fc0eebf4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604407"
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>Comptrrefbase::operator IInspectable\* \*演算子

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>Remarks

現在ではキャスト[ptr _](../windows/comptrrefbase-ptr-data-member.md)をポインターを-、-ポインターのデータ メンバー、`IInspectable`インターフェイス。

場合に、エラーが出力されますが、現在**ComPtrRefBase**から派生していない`IInspectable`。

このキャストは使用可能な場合にのみ`__WRL_CLASSIC_COM__`が定義されています。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[ComPtrRefBase クラス](../windows/comptrrefbase-class.md)  
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)