---
title: Mutex::lock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38bd11620f8d403bbd1667ab6fa4f3f827362c88
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600874"
---
# <a name="mutexlock-method"></a>Mutex::Lock メソッド

現在のオブジェクトまでの待機、または**ミュー テックス**リリース ミュー テックス、または指定されたタイムアウト期間が経過した、指定したハンドルに関連付けられているオブジェクト。

## <a name="syntax"></a>構文

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>パラメーター

*(ミリ秒)*  
タイムアウト間隔 (ミリ秒単位)。 既定値は、INFINITE で、無期限に待機します。

*h*  
ハンドルを**ミュー テックス**オブジェクト。

## <a name="return-value"></a>戻り値

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目
[Mutex クラス](../windows/mutex-class1.md)