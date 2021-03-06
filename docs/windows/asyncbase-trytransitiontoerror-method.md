---
title: Asyncbase::trytransitiontoerror メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1244b87410a09996d946408ff77dbb552b339c85
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591155"
---
# <a name="asyncbasetrytransitiontoerror-method"></a>AsyncBase::TryTransitionToError メソッド

指定したエラー コードが内部エラー状態を変更できるかどうかを示します。

## <a name="syntax"></a>構文

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>パラメーター

*error*  
エラーの hresult 値。

## <a name="return-value"></a>戻り値

**true**内部エラー状態が変更された。 それ以外の場合**false**します。

## <a name="remarks"></a>Remarks

この操作は、エラー状態は S_OK を既に設定されている場合にのみ、エラー状態を変更します。 エラー状態であるエラー、キャンセル、完了すると、または閉じられた場合は、この操作を指定しても効果はありません。

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)