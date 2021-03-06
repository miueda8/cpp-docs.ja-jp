---
title: Synclockt::synclockt コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3dfee1d923536f519917a50ed44fd5c115007c27
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601968"
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT コンストラクター

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);
```

### <a name="parameters"></a>パラメーター

*other*  
別の右辺値参照**SyncLockT**オブジェクト。

*sync*  
別の参照`SyncLockWithStatusT`オブジェクト。

## <a name="remarks"></a>Remarks

新しいインスタンスを初期化、 **SyncLockT**クラス。

最初のコンス トラクターは、現在**SyncLockT**から別のオブジェクト**SyncLockT**パラメーターで指定されたオブジェクト*他*、し、その他のを無効にし、**SyncLockT**オブジェクト。 2 番目のコンス トラクターは**保護**、し、現在の初期化**SyncLockT**オブジェクトを無効な状態にします。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>関連項目

[SyncLockT クラス](../windows/synclockt-class.md)