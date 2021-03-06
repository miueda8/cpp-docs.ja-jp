---
title: Mutex::mutex コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 62a1fc796188c38dfbd3aff004eba15b7e30ea89
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600506"
---
# <a name="mutexmutex-constructor"></a>Mutex::Mutex コンストラクター

新しいインスタンスを初期化、**ミュー テックス**クラス。

## <a name="syntax"></a>構文

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>パラメーター

*h*  
ハンドル、または、ハンドルへの右辺値参照を**ミュー テックス**オブジェクト。

## <a name="remarks"></a>Remarks

最初のコンス トラクターの初期化、**ミュー テックス**オブジェクト指定したハンドルから。 2 番目のコンス トラクターによって初期化、**ミュー テックス**指定のハンドルとし、ミュー テックスの所有権を移動しますから、現在にオブジェクト**ミュー テックス**オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目
[Mutex クラス](../windows/mutex-class1.md)