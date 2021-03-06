---
title: CAtlFileMapping クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 973501339d05f75414d076cbd22f5dabeb0bec7c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208724"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping クラス
このクラスのメソッドへのキャスト演算子の追加メモリ マップト ファイルを表します[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 キャスト演算子を使用するデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|暗黙的な変換は、`CAtlFileMapping`オブジェクトを`T*`します。|  
  
## <a name="remarks"></a>Remarks  
 このクラスの暗黙的な変換を許可する 1 つのキャスト演算子を追加します`CAtlFileMapping`オブジェクトを`T*`します。 他のメンバーは、基本クラスによって提供される[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlfile.h  
  
##  <a name="operator_t_star"></a>  CAtlFileMapping::operator T *  
 暗黙的な変換は、`CAtlFileMapping`オブジェクトを`T*`します。  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します、`T*`メモリ マップト ファイルの先頭へのポインター。  
  
### <a name="remarks"></a>Remarks  
 呼び出し[CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata)として返されたポインターとして再解釈と、`T*`場所*T*はこのクラスのテンプレート パラメーターとして使用される型です。  
  
## <a name="see-also"></a>関連項目  
 [CAtlFileMappingBase クラス](../../atl/reference/catlfilemappingbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
