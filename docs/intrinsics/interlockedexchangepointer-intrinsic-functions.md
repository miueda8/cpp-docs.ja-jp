---
title: _InterlockedExchangePointer の組み込み関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedExchangePointer_cpp
- _InterlockedExchangePointer_rel
- _InterlockedExchangePointer_nf
- _InterlockedExchangePointer_HLERelease
- _InterlockedExchangePointer_acq
- _InterlockedExchangePointer
- _InterlockedExchangePointer_acq_cpp
- _InterlockedExchangePointer_HLEAcquire
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedExchangePointer_rel intrinsic
- _InterlockedExchangePointer_HLERelease intrinsic
- _InterlockedExchangePointer intrinsic
- _InterlockedExchangePointer_nf intrinsic
- _InterlockedExchangePointer_acq intrinsic
- _InterlockedExchangePointer_HLEAcquire intrinsic
- InterlockedExchangePointer_acq intrinsic
- InterlockedExchangePointer intrinsic
ms.assetid: 0eaca0b0-d79e-406b-892d-b3b462c50bbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfeb1453cffac6cfe338f42da8b8efe60e18c9f8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42538754"
---
# <a name="interlockedexchangepointer-intrinsic-functions"></a>_InterlockedExchangePointer の組み込み関数
**Microsoft 固有の仕様**  
  
 アトミック交換操作を実行し、2 番目の引数として渡されたアドレスを最初の引数にコピーして、最初の引数の元のアドレスを返します。  
  
## <a name="syntax"></a>構文  
  
```  
void * _InterlockedExchangePointer(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_acq(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_rel(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_nf(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_HLEAcquire(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_HLERelease(  
   void * volatile * Target,  
   void * Value  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力、出力] `Target`  
 交換する値へのポインターへのポインター。 この関数は `Value` に値を設定し、その前の値を返します。  
  
 [入力] `Value`  
 `Target` が指す値と交換する値。  
  
## <a name="return-value"></a>戻り値  
 この関数は、`Target` が指す初期値を返します。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|Header|  
|---------------|------------------|------------|  
|`_InterlockedExchangePointer`|x86、ARM、x64|\<intrin.h>|  
|`_InterlockedExchangePointer_acq`、`_InterlockedExchangePointer_rel`、`_InterlockedExchangePointer_nf`|ARM|\<intrin.h>|  
|`_InterlockedExchangePointer_HLEAcquire`, `_InterlockedExchangePointer_HLERelease`|HLE 対応 x64|\<immintrin.h>|  
  
 x86 アーキテクチャでは、`_InterlockedExchangePointer` は `_InterlockedExchange` を呼び出すマクロです。  
  
## <a name="remarks"></a>Remarks  
 64 ビット システムではパラメーターは 64 ビットであり、64 ビットの境界に合わせて調整する必要があります。そのようにしない場合は、関数が失敗します。 32 ビット システムではパラメーターは 32 ビットであり、32 ビットの境界に合わせて調整する必要があります。 詳細については、次を参照してください。 [align](../cpp/align-cpp.md)します。  
  
 ARM プラットフォームでは、クリティカル セクションの最初と最後などで取得と解放のセマンティクスを必要とする場合は、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。 `_nf` ("フェンスなし") サフィックスの付いた組み込みはメモリ バリアとしては機能しません。  
  
 Hardware Lock Elision (HLE) 命令をサポートする Intel プラットフォームでは、`_HLEAcquire` および `_HLERelease` サフィックスの付いた組み込みにプロセッサへのヒントが含まれています。このヒントによりハードウェアでのロック書き込み手順を省くことで、パフォーマンスを向上させることができます。 HLE をサポートしていないプラットフォームでこれらの組み込みが呼び出された場合、ヒントは無視されます。  
  
 これらのルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [x86 コンパイラとの競合](../build/conflicts-with-the-x86-compiler.md)