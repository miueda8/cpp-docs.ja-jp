---
title: __shiftright128 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __shiftright128
dev_langs:
- C++
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0aa5b4028863ff31084e8d01892a86b990de51fb
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540448"
---
# <a name="shiftright128"></a>__shiftright128
**Microsoft 固有の仕様**  
  
 64 ビットの 2 つの数 `LowPart` および `HighPart` で表される 128 ビットの数を、`Shift` で指定されたビット数だけ右にシフトし、結果の下位 64 ビットを返します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned __int64 __shiftright128(   
   unsigned __int64 LowPart,   
   unsigned __int64 HighPart,   
   unsigned char Shift   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `LowPart`  
 シフトする 128 ビット数の下位 64 ビット。  
  
 [入力] `HighPart`  
 シフトする 128 ビット数の上位 64 ビット。  
  
 [入力] `Shift`  
 シフトするビット数。  
  
## <a name="return-value"></a>戻り値  
 結果の下位 64 ビット。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__shiftright128`|X64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 `Shift` の値は常にモジュロ 64 です。このため、たとえば `__shiftright128(0, 1, 64)` をコールすると、上位部分が `0` ビット右にシフトされ、下位部分である `0` が返されます。`1` ではありません。  
  
## <a name="example"></a>例  
 例については、次を参照してください。 [_ _shiftleft128](../intrinsics/shiftleft128.md)します。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_ _shiftleft128](../intrinsics/shiftleft128.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)