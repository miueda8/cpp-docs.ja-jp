---
title: Ftmbase::releasemarshaldata メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
dev_langs:
- C++
helpviewer_keywords:
- ReleaseMarshalData method
ms.assetid: a94f9940-183a-4fde-8504-d223f346a0a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2d4bccbcd9f3c3b13fa8be0ccc7afa493751cd9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593540"
---
# <a name="ftmbasereleasemarshaldata-method"></a>FtmBase::ReleaseMarshalData メソッド

データのマーシャ リングされたパケットは破棄されます。

## <a name="syntax"></a>構文

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>パラメーター

*pStm*  
破棄するデータ パケットを格納するストリームへのポインター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="requirements"></a>要件

**ヘッダー:** ftm.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[FtmBase クラス](../windows/ftmbase-class.md)