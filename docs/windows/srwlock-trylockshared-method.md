---
title: Srwlock::trylockshared メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bcad153145432997841753828b3b01b728ff365d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608174"
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared メソッド

取得を試みる、 **SRWLock**オブジェクトの現在または指定した共有モードで**SRWLock**オブジェクト。

## <a name="syntax"></a>構文

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*lock*  
ポインター、 **SRWLock**オブジェクト。

## <a name="return-value"></a>戻り値

成功した場合、 **SRWLock**共有モードと呼び出し元のスレッド内のオブジェクトは、ロックの所有権を取得します。 それ以外の場合、 **SRWLock**オブジェクトの状態が無効です。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[SRWLock クラス](../windows/srwlock-class.md)