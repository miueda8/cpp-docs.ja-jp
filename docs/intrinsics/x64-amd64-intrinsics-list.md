---
title: x64 (amd64) 組み込み一覧 |Microsoft Docs
ms.custom: ''
ms.date: 06/01/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl-exe compiler, intrinsics
- intrinsics, x64
- intrinsics, amd64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eedbc29b5012c3a4355178d0fbd83aad81e9cb95
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680413"
---
# <a name="x64-amd64-intrinsics-list"></a>x64 (amd64) 組み込み一覧

このドキュメントでは、Visual C++ コンパイラがサポートする、x64 (amd64 とも呼ばれます) 対応の組み込みの一覧を示します。

各組み込みの詳細については、対象とするプロセッサに応じて、次の技術情報も参照してください。

- ヘッダー ファイル。 多数の組み込みが、ヘッダー ファイル内のコメント内に文書化されています。

- [Intel Intrinsics Guide](https://software.intel.com/sites/landingpage/IntrinsicsGuide)します。 検索ボックスを使って特定の組み込みを見つけてください。

- [Intel 64 および ia-32 アーキテクチャ ソフトウェア デベロッパーズ マニュアル](https://software.intel.com/articles/intel-sdm)

- [Intel アーキテクチャ命令セット拡張機能プログラミング リファレンス](https://software.intel.com/isa-extensions)

- [Intel Advanced Vector 拡張の概要](https://software.intel.com/articles/introduction-to-intel-advanced-vector-extensions)

- [AMD 開発者ガイド、マニュアル、および ISA ドキュメント](https://developer.amd.com/resources/developer-guides-manuals/)

次の表は、x64 プロセッサで利用可能な組み込みの一覧です。 [テクノロジ] 列に、必要な命令セットのサポートを示します。 [__cpuid](../intrinsics/cpuid-cpuidex.md) 組み込みを使用して、実行時に命令セットのサポートを確認します。 1 つの行に 2 つのエントリがある場合は、同じ組み込みに対する異なるエントリ ポイントを表しています。 [1] は、組み込みが AMD プロセッサでのみ利用可能であることを示します。 [2] は、組み込みが Intel プロセッサでのみ利用可能であることを示します。 [3] は、プロトタイプがマクロであることを示します。 関数プロトタイプに必要なヘッダーが "ヘッダー" 列に示されています。 分かりやすくするために、Intrin.h ヘッダーには immintrin.h と ammintrin.h の両方を含めています。

|組み込みの名前|テクノロジ|Header|関数プロトタイプ|
|--------------------|----------------|------------|------------------------|
|_addcarry_u16||intrin.h|unsigned char _addcarry_u16 (unsigned char c_in、符号なし short src1、短い符号なしの符号なしの短い src2\*合計)|
|[_addcarry_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_addcarry_u32)||intrin.h|unsigned char _addcarry_u32 (unsigned char c_in、符号なし int src1、符号なし int src2、符号なし int\*合計)|
|[_addcarry_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_addcarry_u64)||intrin.h|unsigned char _addcarry_u64 (unsigned char c_in、符号なしの\_符号なしの _ _int64 src1 \__ _int64 src2、署名されていない\__ _int64\*合計)|
|_addcarry_u8||intrin.h|unsigned char _addcarry_u8 (unsigned char c_in、src1 の符号なしの char、unsigned char src2、符号なしの char\*合計)|
|[_addcarryx_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_addcarryx_u32)|ADX [2]|immintrin.h|unsigned char _addcarryx_u32 (unsigned char c_in、符号なし int src1、符号なし int src2、符号なし int\*合計)|
|[_addcarryx_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_addcarryx_u64)|ADX [2]|immintrin.h|unsigned char _addcarryx_u64 (unsigned char c_in、符号なしの\_符号なしの _ _int64 src1 \__ _int64 src2、署名されていない\__ _int64\*合計)|
|[__addgsbyte](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)||intrin.h|void __addgsbyte(unsigned long,unsigned char)|
|[__addgsdword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)||intrin.h|void __addgsdword(unsigned long,unsigned int)|
|[__addgsqword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)||intrin.h|void __addgsqword(unsigned long,unsigned \__int64)|
|[__addgsword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)||intrin.h|void __addgsword(unsigned long,unsigned short)|
|[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)||intrin.h|void \* _AddressOfReturnAddress(void)|
|_andn_u32|BMI [1]|ammintrin.h|unsigned int _andn_u32(unsigned int,unsigned int)|
|_andn_u64|BMI [1]|ammintrin.h|unsigned __int64 _andn_u64(unsigned \__int64,unsigned \__int64)|
|[_bextr_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_bextr_u32)|BMI|ammintrin.h, immintrin.h|unsigned int _bextr_u32(unsigned int,unsigned int,unsigned int)|
|[_bextr_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_bextr_u64)|BMI|ammintrin.h, immintrin.h|unsigned _ _int64 _bextr_u64 (unsigned \__ _int64、unsigned int、unsigned int)|
|_bextri_u32|ABM [1]|ammintrin.h|unsigned int _bextri_u32(unsigned int,unsigned int)|
|_bextri_u64|ABM [1]|ammintrin.h|unsigned __int64 _bextri_u64(unsigned \__int64,unsigned int)|
|[_BitScanForward](../intrinsics/bitscanforward-bitscanforward64.md)||intrin.h|ブール _BitScanForward (ULONG アウト\*インデックス、IN ULONG マスク)|
|[_BitScanForward64](../intrinsics/bitscanforward-bitscanforward64.md)||intrin.h|ブール _BitScanForward64 (ULONG アウト\*インデックス、IN ULONG64 マスク)|
|[_BitScanReverse](../intrinsics/bitscanreverse-bitscanreverse64.md)||intrin.h|ブール _BitScanReverse (ULONG アウト\*インデックス、IN ULONG マスク)|
|[_BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md)||intrin.h|ブール _BitScanReverse64 (ULONG アウト\*インデックス、IN ULONG64 マスク)|
|[_bittest](../intrinsics/bittest-bittest64.md)||intrin.h|unsigned char _bittest (時間の長い const\*時間の長い b)。|
|[_bittest64](../intrinsics/bittest-bittest64.md)||intrin.h|符号なしの char _bittest64 (\__ _int64 const \*、\__ _int64 b)。|
|[_bittestandcomplement](../intrinsics/bittestandcomplement-bittestandcomplement64.md)||intrin.h|unsigned char _bittestandcomplement (時間の長い\*時間の長い a、b)。|
|[_bittestandcomplement64](../intrinsics/bittestandcomplement-bittestandcomplement64.md)||intrin.h|符号なしの char _bittestandcomplement64 (\__ _int64 \*、\__ _int64 b)。|
|[_bittestandreset](../intrinsics/bittestandreset-bittestandreset64.md)||intrin.h|unsigned char _bittestandreset (時間の長い\*時間の長い a、b)。|
|[_bittestandreset64](../intrinsics/bittestandreset-bittestandreset64.md)||intrin.h|符号なしの char _bittestandreset64 (\__ _int64 \*、\__ _int64 b)。|
|[_bittestandset](../intrinsics/bittestandset-bittestandset64.md)||intrin.h|unsigned char _bittestandset (時間の長い\*時間の長い a、b)。|
|[_bittestandset64](../intrinsics/bittestandset-bittestandset64.md)||intrin.h|符号なしの char _bittestandset64 (\__ _int64 \*、\__ _int64 b)。|
|_blcfill_u32|ABM [1]|ammintrin.h|unsigned int _blcfill_u32(unsigned int)|
|_blcfill_u64|ABM [1]|ammintrin.h|unsigned __int64 _blcfill_u64(unsigned \__int64)|
|_blci_u32|ABM [1]|ammintrin.h|unsigned int _blci_u32(unsigned int)|
|_blci_u64|ABM [1]|ammintrin.h|unsigned __int64 _blci_u64(unsigned \__int64)|
|_blcic_u32|ABM [1]|ammintrin.h|unsigned int _blcic_u32(unsigned int)|
|_blcic_u64|ABM [1]|ammintrin.h|unsigned __int64 _blcic_u64(unsigned \__int64)|
|_blcmsk_u32|ABM [1]|ammintrin.h|unsigned int _blcmsk_u32(unsigned int)|
|_blcmsk_u64|ABM [1]|ammintrin.h|unsigned __int64 _blcmsk_u64(unsigned \__int64)|
|_blcs_u32|ABM [1]|ammintrin.h|unsigned int _blcs_u32(unsigned int)|
|_blcs_u64|ABM [1]|ammintrin.h|unsigned __int64 _blcs_u64(unsigned \__int64)|
|_blsfill_u32|ABM [1]|ammintrin.h|unsigned int _blsfill_u32(unsigned int)|
|_blsfill_u64|ABM [1]|ammintrin.h|unsigned __int64 _blsfill_u64(unsigned \__int64)|
|[_blsi_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_blsi_u32)|BMI|ammintrin.h, immintrin.h|unsigned int _blsi_u32(unsigned int)|
|[_blsi_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_blsi_u64)|BMI|ammintrin.h, immintrin.h|unsigned __int64 _blsi_u64(unsigned \__int64)|
|_blsic_u32|ABM [1]|ammintrin.h|unsigned int _blsic_u32(unsigned int)|
|_blsic_u64|ABM [1]|ammintrin.h|unsigned __int64 _blsic_u64(unsigned \__int64)|
|[_blsmsk_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_blsmsk_u32)|BMI|ammintrin.h, immintrin.h|unsigned int _blsmsk_u32(unsigned int)|
|[_blsmsk_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_blsmsk_u64)|BMI|ammintrin.h, immintrin.h|unsigned __int64 _blsmsk_u64(unsigned \__int64)|
|[_blsr_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_blsr_u32)|BMI|ammintrin.h, immintrin.h|unsigned int _blsr_u32(unsigned int)|
|[_blsr_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_blsr_u64)|BMI|ammintrin.h, immintrin.h|unsigned __int64 _blsr_u64(unsigned \__int64)|
|[_bzhi_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_bzhi_u32)|BMI [2]|immintrin.h|unsigned int _bzhi_u32(unsigned int,unsigned int)|
|[_bzhi_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_bzhi_u64)|BMI [2]|immintrin.h|unsigned __int64 _bzhi_u64(unsigned \__int64,unsigned int)|
|_clac|SMAP|intrin.h|void _clac(void)|
|[__cpuid](../intrinsics/cpuid-cpuidex.md)||intrin.h|void _ _cpuid (int \*int a, b)。|
|[__cpuidex](../intrinsics/cpuid-cpuidex.md)||intrin.h|void _ _cpuidex (int \*int、int b c).|
|[__debugbreak](../intrinsics/debugbreak.md)||intrin.h|void __debugbreak(void)|
|[_disable](../intrinsics/disable.md)||intrin.h|void _disable(void)|
|[__emul](../intrinsics/emul-emulu.md)||intrin.h|_ _int64 [pascal/cdecl] \__emul(int,int)|
|[__emulu](../intrinsics/emul-emulu.md)||intrin.h|unsigned __int64 [pascal/cdecl]\__emulu(unsigned int,unsigned int)|
|[_enable](../intrinsics/enable.md)||intrin.h|void _enable(void)|
|[__fastfail](../intrinsics/fastfail.md)||intrin.h|void __fastfail(unsigned int)|
|[__faststorefence](../intrinsics/faststorefence.md)||intrin.h|void __faststorefence(void)|
|[_fxrstor](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_fxrstor)|FXSR [2]|immintrin.h|void _fxrstor (const void\*)|
|[_fxrstor64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_fxrstor64)|FXSR [2]|immintrin.h|void _fxrstor64 (const void\*)|
|[_fxsave](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_fxsave)|FXSR [2]|immintrin.h|void _fxsave (void\*)|
|[_fxsave64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_fxsave64)|FXSR [2]|immintrin.h|void _fxsave64 (void\*)|
|[__getcallerseflags](../intrinsics/getcallerseflags.md)||intrin.h|(unsigned int __getcallerseflags())|
|[__halt](../intrinsics/halt.md)||intrin.h|void __halt(void)|
|[__inbyte](../intrinsics/inbyte.md)||intrin.h|unsigned char __inbyte(unsigned short Port)|
|[__inbytestring](../intrinsics/inbytestring.md)||intrin.h|void _ _inbytestring (符号なし short ポート、unsigned char\*バッファー、時間数の符号なし)|
|[__incgsbyte](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)||intrin.h|void __incgsbyte(unsigned long)|
|[__incgsdword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)||intrin.h|void __incgsdword(unsigned long)|
|[__incgsqword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)||intrin.h|void __incgsqword(unsigned long)|
|[__incgsword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)||intrin.h|void __incgsword(unsigned long)|
|[__indword](../intrinsics/indword.md)||intrin.h|unsigned long __indword(unsigned short Port)|
|[__indwordstring](../intrinsics/indwordstring.md)||intrin.h|void _ _indwordstring (符号なしの時間の長い符号なし short のポート\*バッファー、時間数の符号なし)|
|[__int2c](../intrinsics/int2c.md)||intrin.h|void __int2c(void)|
|[_InterlockedAnd](../intrinsics/interlockedand-intrinsic-functions.md)||intrin.h|long _InterlockedAnd (long volatile \*, long)|
|[_InterlockedAnd_HLEAcquire](../intrinsics/interlockedand-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedAnd_HLEAcquire (long volatile \*, long)|
|[_InterlockedAnd_HLERelease](../intrinsics/interlockedand-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedAnd_HLERelease (long volatile \*, long)|
|[_InterlockedAnd_np](../intrinsics/interlockedand-intrinsic-functions.md)||intrin.h|長い _InterlockedAnd_np (時間の長い\*, long)|
|[_InterlockedAnd16](../intrinsics/interlockedand-intrinsic-functions.md)||intrin.h|short _InterlockedAnd16 (short volatile \*, short)|
|[_InterlockedAnd16_np](../intrinsics/interlockedand-intrinsic-functions.md)||intrin.h|_InterlockedAnd16_np 短い (short \*, short)|
|[_InterlockedAnd64](../intrinsics/interlockedand-intrinsic-functions.md)||intrin.h|_ _ int64 _InterlockedAnd64 (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedAnd64_HLEAcquire](../intrinsics/interlockedand-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedAnd64_HLEAcquire (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedAnd64_HLERelease](../intrinsics/interlockedand-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedAnd64_HLERelease (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedAnd64_np](../intrinsics/interlockedand-intrinsic-functions.md)||intrin.h|_ _int64 _InterlockedAnd64_np (\__ _int64 \*、\__ _int64)|
|[_InterlockedAnd8](../intrinsics/interlockedand-intrinsic-functions.md)||intrin.h|char _InterlockedAnd8 (char volatile \*char)|
|[_InterlockedAnd8_np](../intrinsics/interlockedand-intrinsic-functions.md)||intrin.h|_InterlockedAnd8_np を char (char \*char)|
|[_interlockedbittestandreset](../intrinsics/interlockedbittestandreset-intrinsic-functions.md)||intrin.h|unsigned char _interlockedbittestandreset (時間の長い\*時間の長い a、b)。|
|[_interlockedbittestandreset_HLEAcquire](../intrinsics/interlockedbittestandreset-intrinsic-functions.md)|HLE [2]|immintrin.h|unsigned char _interlockedbittestandreset_HLEAcquire (時間の長い\*時間の長い a、b)。|
|[_interlockedbittestandreset_HLERelease](../intrinsics/interlockedbittestandreset-intrinsic-functions.md)|HLE [2]|immintrin.h|unsigned char _interlockedbittestandreset_HLERelease (時間の長い\*時間の長い a、b)。|
|[_interlockedbittestandreset64](../intrinsics/interlockedbittestandreset-intrinsic-functions.md)||intrin.h|符号なしの char _interlockedbittestandreset64 (\__ _int64 \*、\__ _int64 b)。|
|[_interlockedbittestandreset64_HLEAcquire](../intrinsics/interlockedbittestandreset-intrinsic-functions.md)|HLE [2]|immintrin.h|符号なしの char _interlockedbittestandreset64_HLEAcquire (\__ _int64 \*、\__ _int64 b)。|
|[_interlockedbittestandreset64_HLERelease](../intrinsics/interlockedbittestandreset-intrinsic-functions.md)|HLE [2]|immintrin.h|符号なしの char _interlockedbittestandreset64_HLERelease (\__ _int64 \*、\__ _int64 b)。|
|[_interlockedbittestandset](../intrinsics/interlockedbittestandset-intrinsic-functions.md)||intrin.h|unsigned char _interlockedbittestandset (時間の長い\*時間の長い a、b)。|
|[_interlockedbittestandset_HLEAcquire](../intrinsics/interlockedbittestandset-intrinsic-functions.md)|HLE [2]|immintrin.h|unsigned char _interlockedbittestandset_HLEAcquire (時間の長い\*時間の長い a、b)。|
|[_interlockedbittestandset_HLERelease](../intrinsics/interlockedbittestandset-intrinsic-functions.md)|HLE [2]|immintrin.h|unsigned char _interlockedbittestandset_HLERelease (時間の長い\*時間の長い a、b)。|
|[_interlockedbittestandset64](../intrinsics/interlockedbittestandset-intrinsic-functions.md)||intrin.h|符号なしの char _interlockedbittestandset64 (\__ _int64 \*、\__ _int64 b)。|
|[_interlockedbittestandset64_HLEAcquire](../intrinsics/interlockedbittestandset-intrinsic-functions.md)|HLE [2]|immintrin.h|符号なしの char _interlockedbittestandset64_HLEAcquire (\__ _int64 \*、\__ _int64 b)。|
|[_interlockedbittestandset64_HLERelease](../intrinsics/interlockedbittestandset-intrinsic-functions.md)|HLE [2]|immintrin.h|符号なしの char _interlockedbittestandset64_HLERelease (\__ _int64 \*、\__ _int64 b)。|
|[_InterlockedCompareExchange](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)||intrin.h|長い _InterlockedCompareExchange (long volatile \*、long, long)|
|[_InterlockedCompareExchange_HLEAcquire](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedCompareExchange_HLEAcquire (long volatile \*、long, long)|
|[_InterlockedCompareExchange_HLERelease](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedCompareExchange_HLERelease (long volatile \*、long, long)|
|[_InterlockedCompareExchange_np](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)||intrin.h|長い _InterlockedCompareExchange_np (長い\*、long, long)|
|[_InterlockedCompareExchange128](../intrinsics/interlockedcompareexchange128.md)||intrin.h|符号なしの char _InterlockedCompareExchange128 (\__ _int64 volatile \*、\__ _int64、\__ _int64、\__ _int64\*)|
|[_InterlockedCompareExchange128_np](../intrinsics/interlockedcompareexchange128.md)||intrin.h|符号なしの char _InterlockedCompareExchange128 (\__ _int64 volatile \*、\__ _int64、\__ _int64、\__ _int64\*)|
|[_InterlockedCompareExchange16](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)||intrin.h|短い _InterlockedCompareExchange16 (short volatile\*変換先、短い Exchange は、短い比較対照値)|
|[_InterlockedCompareExchange16_np](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)||intrin.h|短い _InterlockedCompareExchange16_np (short volatile\*変換先、短い Exchange は、短い比較対照値)|
|[_InterlockedCompareExchange64](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)||intrin.h|_ _int64 _InterlockedCompareExchange64 (\__ _int64 volatile \*、\__ _int64、\__ _int64)|
|[_InterlockedCompareExchange64_HLEAcquire](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedCompareExchange64_HLEAcquire (\__ _int64 volatile \*、\__ _int64、\__ _int64)|
|[_InterlockedCompareExchange64_HLERelease](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedCompareExchange64_HLERelease (\__ _int64 volatile \*、\__ _int64、\__ _int64)|
|[_InterlockedCompareExchange64_np](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)||intrin.h|_ _int64 _InterlockedCompareExchange64_np (\__ _int64 \*、\__ _int64、\__ _int64)|
|[_InterlockedCompareExchange8](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)||intrin.h|_InterlockedCompareExchange8 を char (char volatile\*文字比較対照値の変換先、char、Exchange)|
|[_InterlockedCompareExchangePointer](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)||intrin.h|void \*_InterlockedCompareExchangePointer (void\*揮発性\*, void \*, void \*)|
|[_InterlockedCompareExchangePointer_HLEAcquire](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)|HLE [2]|immintrin.h|void * _InterlockedCompareExchangePointer_HLEAcquire (void \*volatile \*, void \*, void \*)|
|[_InterlockedCompareExchangePointer_HLERelease](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)|HLE [2]|immintrin.h|void *_InterlockedCompareExchangePointer_HLERelease(void \*volatile \*,void \*,void \*)|
|[_InterlockedCompareExchangePointer_np](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)||intrin.h|void \*_InterlockedCompareExchangePointer_np (void \* \*, void \*, void \*)|
|[_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)||intrin.h|長い _InterlockedDecrement (long volatile \*)|
|[_InterlockedDecrement16](../intrinsics/interlockeddecrement-intrinsic-functions.md)||intrin.h|_InterlockedDecrement16 短い (short volatile\*加数)|
|[_InterlockedDecrement64](../intrinsics/interlockeddecrement-intrinsic-functions.md)||intrin.h|_ _int64 _InterlockedDecrement64 (\__ _int64 volatile \*)|
|[_InterlockedExchange](../intrinsics/interlockedexchange-intrinsic-functions.md)||intrin.h|長い _InterlockedExchange (long volatile \*, long)|
|[_InterlockedExchange_HLEAcquire](../intrinsics/interlockedexchange-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedExchange_HLEAcquire (long volatile \*, long)|
|[_InterlockedExchange_HLERelease](../intrinsics/interlockedexchange-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedExchange_HLERelease (long volatile \*, long)|
|[_InterlockedExchange16](../intrinsics/interlockedexchange-intrinsic-functions.md)||intrin.h|短い _InterlockedExchange16 (short volatile \*, short)|
|[_InterlockedExchange64](../intrinsics/interlockedexchange-intrinsic-functions.md)||intrin.h|_ _int64 _InterlockedExchange64 (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedExchange64_HLEAcquire](../intrinsics/interlockedexchange-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedExchange64_HLEAcquire (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedExchange64_HLERelease](../intrinsics/interlockedexchange-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedExchange64_HLERelease (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedExchange8](../intrinsics/interlockedexchange-intrinsic-functions.md)||intrin.h|_InterlockedExchange8 を char (char volatile \*char)|
|[_InterlockedExchangeAdd](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)||intrin.h|長い _InterlockedExchangeAdd (long volatile \*, long)|
|[_InterlockedExchangeAdd_HLEAcquire](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedExchangeAdd_HLEAcquire (long volatile \*, long)|
|[_InterlockedExchangeAdd_HLERelease](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedExchangeAdd_HLERelease (long volatile \*, long)|
|[_InterlockedExchangeAdd16](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)||intrin.h|short _InterlockedExchangeAdd16 (short volatile \*, short)|
|[_InterlockedExchangeAdd64](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)||intrin.h|_ _ int64 _InterlockedExchangeAdd64 (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedExchangeAdd64_HLEAcquire](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedExchangeAdd64_HLEAcquire (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedExchangeAdd64_HLERelease](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedExchangeAdd64_HLERelease (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedExchangeAdd8](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)||intrin.h|char _InterlockedExchangeAdd8 (char volatile \*char)|
|[_InterlockedExchangePointer](../intrinsics/interlockedexchangepointer-intrinsic-functions.md)||intrin.h|void \* _InterlockedExchangePointer (void \*volatile \*, void \*)|
|[_InterlockedExchangePointer_HLEAcquire](../intrinsics/interlockedexchangepointer-intrinsic-functions.md)|HLE [2]|immintrin.h|void \* _InterlockedExchangePointer_HLEAcquire (void \*volatile \*, void \*)|
|[_InterlockedExchangePointer_HLERelease](../intrinsics/interlockedexchangepointer-intrinsic-functions.md)|HLE [2]|immintrin.h|void * _InterlockedExchangePointer_HLERelease(void \*volatile \*,void \*)|
|[_InterlockedIncrement](../intrinsics/interlockedincrement-intrinsic-functions.md)||intrin.h|長い _InterlockedIncrement (long volatile \*)|
|[_InterlockedIncrement16](../intrinsics/interlockedincrement-intrinsic-functions.md)||intrin.h|_InterlockedIncrement16 短い (short volatile\*加数)|
|[_InterlockedIncrement64](../intrinsics/interlockedincrement-intrinsic-functions.md)||intrin.h|_ _int64 _InterlockedIncrement64 (\__ _int64 volatile \*)|
|[_InterlockedOr](../intrinsics/interlockedor-intrinsic-functions.md)||intrin.h|long _InterlockedOr (long volatile \*, long)|
|[_InterlockedOr_HLEAcquire](../intrinsics/interlockedor-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedOr_HLEAcquire (long volatile \*, long)|
|[_InterlockedOr_HLERelease](../intrinsics/interlockedor-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedOr_HLERelease (long volatile \*, long)|
|[_InterlockedOr_np](../intrinsics/interlockedor-intrinsic-functions.md)||intrin.h|長い _InterlockedOr_np (時間の長い\*, long)|
|[_InterlockedOr16](../intrinsics/interlockedor-intrinsic-functions.md)||intrin.h|short _InterlockedOr16 (short volatile \*, short)|
|[_InterlockedOr16_np](../intrinsics/interlockedor-intrinsic-functions.md)||intrin.h|_InterlockedOr16_np 短い (short \*, short)|
|[_InterlockedOr64](../intrinsics/interlockedor-intrinsic-functions.md)||intrin.h|_ _ int64 _InterlockedOr64 (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedOr64_HLEAcquire](../intrinsics/interlockedor-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedOr64_HLEAcquire (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedOr64_HLERelease](../intrinsics/interlockedor-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedOr64_HLERelease (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedOr64_np](../intrinsics/interlockedor-intrinsic-functions.md)||intrin.h|_ _int64 _InterlockedOr64_np (\__ _int64 \*、\__ _int64)|
|[_InterlockedOr8](../intrinsics/interlockedor-intrinsic-functions.md)||intrin.h|char _InterlockedOr8 (char volatile \*char)|
|[_InterlockedOr8_np](../intrinsics/interlockedor-intrinsic-functions.md)||intrin.h|_InterlockedOr8_np を char (char \*char)|
|[_InterlockedXor](../intrinsics/interlockedxor-intrinsic-functions.md)||intrin.h|long _InterlockedXor (long volatile \*, long)|
|[_InterlockedXor_HLEAcquire](../intrinsics/interlockedxor-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedXor_HLEAcquire (long volatile \*, long)|
|[_InterlockedXor_HLERelease](../intrinsics/interlockedxor-intrinsic-functions.md)|HLE [2]|immintrin.h|長い _InterlockedXor_HLERelease (long volatile \*, long)|
|[_InterlockedXor_np](../intrinsics/interlockedxor-intrinsic-functions.md)||intrin.h|長い _InterlockedXor_np (時間の長い\*, long)|
|[_InterlockedXor16](../intrinsics/interlockedxor-intrinsic-functions.md)||intrin.h|short _InterlockedXor16 (short volatile \*, short)|
|[_InterlockedXor16_np](../intrinsics/interlockedxor-intrinsic-functions.md)||intrin.h|短い _InterlockedXor16_np (短い\*, short)|
|[_InterlockedXor64](../intrinsics/interlockedxor-intrinsic-functions.md)||intrin.h|_ _ int64 _InterlockedXor64 (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedXor64_HLEAcquire](../intrinsics/interlockedxor-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedXor64_HLEAcquire (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedXor64_HLERelease](../intrinsics/interlockedxor-intrinsic-functions.md)|HLE [2]|immintrin.h|_ _int64 _InterlockedXor64_HLERelease (\__ _int64 volatile \*、\__ _int64)|
|[_InterlockedXor64_np](../intrinsics/interlockedxor-intrinsic-functions.md)||intrin.h|_ _int64 _InterlockedXor64_np (\__ _int64 \*、\__ _int64)|
|[_InterlockedXor8](../intrinsics/interlockedxor-intrinsic-functions.md)||intrin.h|char _InterlockedXor8 (char volatile \*char)|
|[_InterlockedXor8_np](../intrinsics/interlockedxor-intrinsic-functions.md)||intrin.h|_InterlockedXor8_np を char (char \*char)|
|[__invlpg](../intrinsics/invlpg.md)||intrin.h|void _ _invlpg (void\*)|
|[_invpcid](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_invpcid)|INVPCID [2]|immintrin.h|void _invpcid (符号なしの int、void \*)|
|[__inword](../intrinsics/inword.md)||intrin.h|unsigned short __inword(unsigned short Port)|
|[__inwordstring](../intrinsics/inwordstring.md)||intrin.h|void _ _inwordstring (符号なしの短い符号なし short のポート\*バッファー、時間数の符号なし)|
|_lgdt||intrin.h|void _lgdt (void\*)|
|[__lidt](../intrinsics/lidt.md)||intrin.h|void _ _lidt (void\*)|
|[__ll_lshift](../intrinsics/ll-lshift.md)||intrin.h|unsigned __int64 [pascal/cdecl] \__ll_lshift(unsigned \__int64,int)|
|[__ll_rshift](../intrinsics/ll-rshift.md)||intrin.h|_ _int64 [pascal/cdecl] \__ll_rshift (\_int、_ _int64)|
|__llwpcb|LWP [1]|ammintrin.h|void __llwpcb (void \*)|
|_load_be_u16<br /><br /> [_loadbe_i16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_loadbe_i16&expand=3071)|MOVBE|immintrin.h|符号なし short _load_be_u16 (const void\*)。<br /><br /> 短い _loadbe_i16 (const void\*)。[3]|
|_load_be_u32<br /><br /> [_loadbe_i32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_loadbe_i32&expand=3072)|MOVBE|immintrin.h|符号なしの int _load_be_u32 (const void\*)。<br /><br /> int _loadbe_i32 (const void\*)。[3]|
|_load_be_u64<br /><br /> [_loadbe_i64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_loadbe_i64&expand=3073)|MOVBE|immintrin.h|unsigned _ _int64 _load_be_u64 (const void\*)。<br /><br /> \__ _int64 _loadbe_i64 (const void\*)。[3]|
|__lwpins32|LWP [1]|ammintrin.h|unsigned char __lwpins32(unsigned int,unsigned int,unsigned int)|
|__lwpins64|LWP [1]|ammintrin.h|unsigned char __lwpins64 (unsigned \__ _int64、unsigned int、unsigned int)|
|__lwpval32|LWP [1]|ammintrin.h|void __lwpval32(unsigned int,unsigned int,unsigned int)|
|__lwpval64|LWP [1]|ammintrin.h|void __lwpval64(unsigned \__int64,unsigned int,unsigned int)|
|[__lzcnt](../intrinsics/lzcnt16-lzcnt-lzcnt64.md)|LZCNT|intrin.h|unsigned int __lzcnt(unsigned int)|
|[_lzcnt_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_lzcnt_u32)|BMI|ammintrin.h, immintrin.h|unsigned int _lzcnt_u32(unsigned int)|
|[_lzcnt_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_lzcnt_u64)|BMI|ammintrin.h, immintrin.h|unsigned __int64 _lzcnt_u64(unsigned \__int64)|
|[__lzcnt16](../intrinsics/lzcnt16-lzcnt-lzcnt64.md)|LZCNT|intrin.h|unsigned short __lzcnt16(unsigned short)|
|[__lzcnt64](../intrinsics/lzcnt16-lzcnt-lzcnt64.md)|LZCNT|intrin.h|unsigned __int64 \__lzcnt64(unsigned \__int64)|
|_m_prefetch|3DNOW|intrin.h|void _m_prefetch (void\*)|
|_m_prefetchw|3DNOW|intrin.h|void _m_prefetchw (void\*)|
|[_mm_abs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_abs_epi16)|SSSE3|intrin.h|__m128i _mm_abs_epi16(\__m128i)|
|[_mm_abs_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_abs_epi32)|SSSE3|intrin.h|_ _m128i _mm_abs_epi32 (\__m128i)|
|[_mm_abs_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_abs_epi8)|SSSE3|intrin.h|_ _m128i _mm_abs_epi8 (\__m128i)|
|[_mm_add_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_epi16)|SSE2|intrin.h|_ _m128i _mm_add_epi16 (\__m128i、\__m128i)|
|[_mm_add_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_epi32)|SSE2|intrin.h|_ _m128i _mm_add_epi32 (\__m128i、\__m128i)|
|[_mm_add_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_epi64)|SSE2|intrin.h|_ _m128i _mm_add_epi64 (\__m128i、\__m128i)|
|[_mm_add_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_epi8)|SSE2|intrin.h|_ _m128i _mm_add_epi8 (\__m128i、\__m128i)|
|[_mm_add_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_pd)|SSE2|intrin.h|__m128d _mm_add_pd(\__m128d,\__m128d)|
|[_mm_add_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_ps)|SSE|intrin.h|__m128 _mm_add_ps(\__m128,\__m128)|
|[_mm_add_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_sd)|SSE2|intrin.h|__m128d _mm_add_sd(\__m128d,\__m128d)|
|[_mm_add_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_ss)|SSE|intrin.h|_ _m128 _mm_add_ss (\__m128、\__m128)|
|[_mm_adds_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_epi16)|SSE2|intrin.h|_ _m128i _mm_adds_epi16 (\__m128i、\__m128i)|
|[_mm_adds_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_epi8)|SSE2|intrin.h|_ _m128i _mm_adds_epi8 (\__m128i、\__m128i)|
|[_mm_adds_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_epu16)|SSE2|intrin.h|_ _m128i _mm_adds_epu16 (\__m128i、\__m128i)|
|[_mm_adds_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_epu8)|SSE2|intrin.h|_ _m128i _mm_adds_epu8 (\__m128i、\__m128i)|
|[_mm_addsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_addsub_pd)|SSE3|intrin.h|__m128d _mm_addsub_pd(\__m128d,\__m128d)|
|[_mm_addsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_addsub_ps)|SSE3|intrin.h|_ _m128 _mm_addsub_ps (\__m128、\__m128)|
|[_mm_aesdec_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesdec_si128)|AESNI [2]|immintrin.h|_ _m128i _mm_aesdec_si128 ( \__m128i、\__m128i)|
|[_mm_aesdeclast_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesdeclast_si128)|AESNI [2]|immintrin.h|_ _m128i _mm_aesdeclast_si128 ( \__m128i、\__m128i)|
|[_mm_aesenc_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesenc_si128)|AESNI [2]|immintrin.h|_ _m128i _mm_aesenc_si128 ( \__m128i、\__m128i)|
|[_mm_aesenclast_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesenclast_si128)|AESNI [2]|immintrin.h|_ _m128i _mm_aesenclast_si128 ( \__m128i、\__m128i)|
|[_mm_aesimc_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesimc_si128)|AESNI [2]|immintrin.h|_ _m128i _mm_aesimc_si128 (\__m128i)|
|[_mm_aeskeygenassist_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aeskeygenassist_si128)|AESNI [2]|immintrin.h|_ _m128i _mm_aeskeygenassist_si128 (\__m128i、const int)|
|[_mm_alignr_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_alignr_epi8)|SSSE3|intrin.h|_ _m128i _mm_alignr_epi8 (\__m128i、\__m128i、int)|
|[_mm_and_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_and_pd)|SSE2|intrin.h|__m128d _mm_and_pd(\__m128d,\__m128d)|
|[_mm_and_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_and_ps)|SSE|intrin.h|__m128 _mm_and_ps(\__m128,\__m128)|
|[_mm_and_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_and_si128)|SSE2|intrin.h|_ _m128i _mm_and_si128 (\__m128i、\__m128i)|
|[_mm_andnot_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_andnot_pd)|SSE2|intrin.h|__m128d _mm_andnot_pd(\__m128d,\__m128d)|
|[_mm_andnot_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_andnot_ps)|SSE|intrin.h|_ _m128 _mm_andnot_ps (\__m128、\__m128)|
|[_mm_andnot_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_andnot_si128)|SSE2|intrin.h|_ _m128i _mm_andnot_si128 (\__m128i、\__m128i)|
|[_mm_avg_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_avg_epu16)|SSE2|intrin.h|_ _m128i _mm_avg_epu16 (\__m128i、\__m128i)|
|[_mm_avg_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_avg_epu8)|SSE2|intrin.h|_ _m128i _mm_avg_epu8 (\__m128i、\__m128i)|
|[_mm_blend_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blend_epi16)|SSE41|intrin.h|_ _m128i _mm_blend_epi16 (\__m128i、\__m128i、const int)|
|[_mm_blend_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blend_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_blend_epi32 (\__m128i、\__m128i、const int)|
|[_mm_blend_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blend_pd)|SSE41|intrin.h|_ _m128d _mm_blend_pd (\__m128d、\__m128d、const int)|
|[_mm_blend_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blend_ps)|SSE41|intrin.h|_ _m128 _mm_blend_ps (\__m128、\__m128、const int)|
|[_mm_blendv_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blendv_epi8)|SSE41|intrin.h|_ _m128i _mm_blendv_epi8 (\__m128i、\__m128i、\__m128i)|
|[_mm_blendv_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blendv_pd)|SSE41|intrin.h|__m128d _mm_blendv_pd(\__m128d,\__m128d,\__m128d)|
|[_mm_blendv_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blendv_ps)|SSE41|intrin.h|_ _m128 _mm_blendv_ps (\__m128、\__m128、\__m128)|
|[_mm_broadcast_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcast_ss)|AVX [2]|immintrin.h|_ _m128 _mm_broadcast_ss (float、const \*)|
|[_mm_broadcastb_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastb_epi8)|AVX2 [2]|immintrin.h|_ _m128i _mm_broadcastb_epi8 (\__m128i)|
|[_mm_broadcastd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastd_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_broadcastd_epi32 (\__m128i)|
|[_mm_broadcastq_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastq_epi64)|AVX2 [2]|immintrin.h|_ _m128i _mm_broadcastq_epi64 (\__m128i)|
|[_mm_broadcastsd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastsd_pd)|AVX2 [2]|immintrin.h|__m128d _mm_broadcastsd_pd(\__m128d)|
|[_mm_broadcastss_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastss_ps)|AVX2 [2]|immintrin.h|_ _m128 _mm_broadcastss_ps (\__m128)|
|[_mm_broadcastw_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastw_epi16)|AVX2 [2]|immintrin.h|_ _m128i _mm_broadcastw_epi16 (\__m128i)|
|[_mm_castpd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castpd_ps)|SSSE3|intrin.h|__m128  _mm_castpd_ps(\__m128d)|
|[_mm_castpd_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castpd_si128)|SSSE3|intrin.h|__m128i _mm_castpd_si128(\__m128d)|
|[_mm_castps_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castps_pd)|SSSE3|intrin.h|__m128d _mm_castps_pd(\__m128)|
|[_mm_castps_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castps_si128)|SSSE3|intrin.h|__m128i _mm_castps_si128(\__m128)|
|[_mm_castsi128_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castsi128_pd)|SSSE3|intrin.h|__m128d _mm_castsi128_pd(\__m128i)|
|[_mm_castsi128_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castsi128_ps)|SSSE3|intrin.h|__m128  _mm_castsi128_ps(\__m128i)|
|[_mm_clflush](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_clflush)|SSE2|intrin.h|void _mm_clflush (const void \*)|
|[_mm_clmulepi64_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_clmulepi64_si128)|PCLMULQDQ [2]|immintrin.h|_ _m128i _mm_clmulepi64_si128 (\__m128i、\__m128i、const int)|
|_mm_cmov_si128|XOP [1]|ammintrin.h|_ _m128i _mm_cmov_si128 (\__m128i、\__m128i、\__m128i)|
|[_mm_cmp_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmp_pd)|AVX [2]|immintrin.h|__m128d  _mm_cmp_pd(\__m128d,\__m128d,const int)|
|[_mm_cmp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmp_ps)|AVX [2]|immintrin.h|_ _m128 _mm_cmp_ps (\__m128、\__m128、const int)|
|[_mm_cmp_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmp_sd)|AVX [2]|immintrin.h|__m128d  _mm_cmp_sd(\__m128d,\__m128d,const int)|
|[_mm_cmp_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmp_ss)|AVX [2]|immintrin.h|_ _m128 _mm_cmp_ss (\__m128、\__m128、const int)|
|[_mm_cmpeq_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_epi16)|SSE2|intrin.h|_ _m128i _mm_cmpeq_epi16 (\__m128i、\__m128i)|
|[_mm_cmpeq_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_epi32)|SSE2|intrin.h|_ _m128i _mm_cmpeq_epi32 (\__m128i、\__m128i)|
|[_mm_cmpeq_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_epi64)|SSE41|intrin.h|_ _m128i _mm_cmpeq_epi64 (\__m128i、\__m128i)|
|[_mm_cmpeq_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_epi8)|SSE2|intrin.h|_ _m128i _mm_cmpeq_epi8 (\__m128i、\__m128i)|
|[_mm_cmpeq_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_pd)|SSE2|intrin.h|__m128d _mm_cmpeq_pd(\__m128d,\__m128d)|
|[_mm_cmpeq_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_ps)|SSE|intrin.h|__m128 _mm_cmpeq_ps(\__m128,\__m128)|
|[_mm_cmpeq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_sd)|SSE2|intrin.h|__m128d _mm_cmpeq_sd(\__m128d,\__m128d)|
|[_mm_cmpeq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_ss)|SSE|intrin.h|_ _m128 _mm_cmpeq_ss (\__m128、\__m128)|
|[_mm_cmpestra](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestra)|SSE42|intrin.h|int _mm_cmpestra (\__m128i、int、\__m128i、int、const int)|
|[_mm_cmpestrc](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestrc)|SSE42|intrin.h|int _mm_cmpestrc (\__m128i、int、\__m128i、int、const int)|
|[_mm_cmpestri](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestri)|SSE42|intrin.h|int _mm_cmpestri (\__m128i、int、\__m128i、int、const int)|
|[_mm_cmpestrm](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestrm)|SSE42|intrin.h|_ _m128i _mm_cmpestrm (\__m128i、int、\__m128i、int、const int)|
|[_mm_cmpestro](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestro)|SSE42|intrin.h|int _mm_cmpestro (\__m128i、int、\__m128i、int、const int)|
|[_mm_cmpestrs](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestrs)|SSE42|intrin.h|int _mm_cmpestrs (\__m128i、int、\__m128i、int、const int)|
|[_mm_cmpestrz](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestrz)|SSE42|intrin.h|int _mm_cmpestrz (\__m128i、int、\__m128i、int、const int)|
|[_mm_cmpge_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpge_pd)|SSE2|intrin.h|__m128d _mm_cmpge_pd(\__m128d,\__m128d)|
|[_mm_cmpge_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpge_ps)|SSE|intrin.h|_ _m128 _mm_cmpge_ps (\__m128、\__m128)|
|[_mm_cmpge_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpge_sd)|SSE2|intrin.h|__m128d _mm_cmpge_sd(\__m128d,\__m128d)|
|[_mm_cmpge_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpge_ss)|SSE|intrin.h|_ _m128 _mm_cmpge_ss (\__m128、\__m128)|
|[_mm_cmpgt_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_epi16)|SSE2|intrin.h|_ _m128i _mm_cmpgt_epi16 (\__m128i、\__m128i)|
|[_mm_cmpgt_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_epi32)|SSE2|intrin.h|_ _m128i _mm_cmpgt_epi32 (\__m128i、\__m128i)|
|[_mm_cmpgt_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_epi64)|SSE42|intrin.h|_ _m128i _mm_cmpgt_epi64 (\__m128i、\__m128i)|
|[_mm_cmpgt_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_epi8)|SSE2|intrin.h|_ _m128i _mm_cmpgt_epi8 (\__m128i、\__m128i)|
|[_mm_cmpgt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_pd)|SSE2|intrin.h|__m128d _mm_cmpgt_pd(\__m128d,\__m128d)|
|[_mm_cmpgt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_ps)|SSE|intrin.h|_ _m128 _mm_cmpgt_ps (\__m128、\__m128)|
|[_mm_cmpgt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_sd)|SSE2|intrin.h|__m128d _mm_cmpgt_sd(\__m128d,\__m128d)|
|[_mm_cmpgt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_ss)|SSE|intrin.h|_ _m128 _mm_cmpgt_ss (\__m128、\__m128)|
|[_mm_cmpistra](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistra)|SSE42|intrin.h|int _mm_cmpistra (\__m128i、\__m128i、const int)|
|[_mm_cmpistrc](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistrc)|SSE42|intrin.h|int _mm_cmpistrc (\__m128i、\__m128i、const int)|
|[_mm_cmpistri](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistri)|SSE42|intrin.h|int _mm_cmpistri (\__m128i、\__m128i、const int)|
|[_mm_cmpistrm](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistrm)|SSE42|intrin.h|_ _m128i _mm_cmpistrm (\__m128i、\__m128i、const int)|
|[_mm_cmpistro](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistro)|SSE42|intrin.h|int _mm_cmpistro (\__m128i、\__m128i、const int)|
|[_mm_cmpistrs](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistrs)|SSE42|intrin.h|int _mm_cmpistrs (\__m128i、\__m128i、const int)|
|[_mm_cmpistrz](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistrz)|SSE42|intrin.h|int _mm_cmpistrz (\__m128i、\__m128i、const int)|
|[_mm_cmple_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmple_pd)|SSE2|intrin.h|__m128d _mm_cmple_pd(\__m128d,\__m128d)|
|[_mm_cmple_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmple_ps)|SSE|intrin.h|_ _m128 _mm_cmple_ps (\__m128、\__m128)|
|[_mm_cmple_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmple_sd)|SSE2|intrin.h|__m128d _mm_cmple_sd(\__m128d,\__m128d)|
|[_mm_cmple_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmple_ss)|SSE|intrin.h|_ _m128 _mm_cmple_ss (\__m128、\__m128)|
|[_mm_cmplt_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_epi16)|SSE2|intrin.h|_ _m128i _mm_cmplt_epi16 (\__m128i、\__m128i)|
|[_mm_cmplt_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_epi32)|SSE2|intrin.h|_ _m128i _mm_cmplt_epi32 (\__m128i、\__m128i)|
|[_mm_cmplt_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_epi8)|SSE2|intrin.h|_ _m128i _mm_cmplt_epi8 (\__m128i、\__m128i)|
|[_mm_cmplt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_pd)|SSE2|intrin.h|__m128d _mm_cmplt_pd(\__m128d,\__m128d)|
|[_mm_cmplt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_ps)|SSE|intrin.h|_ _m128 _mm_cmplt_ps (\__m128、\__m128)|
|[_mm_cmplt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_sd)|SSE2|intrin.h|__m128d _mm_cmplt_sd(\__m128d,\__m128d)|
|[_mm_cmplt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_ss)|SSE|intrin.h|_ _m128 _mm_cmplt_ss (\__m128、\__m128)|
|[_mm_cmpneq_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpneq_pd)|SSE2|intrin.h|__m128d _mm_cmpneq_pd(\__m128d,\__m128d)|
|[_mm_cmpneq_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpneq_ps)|SSE|intrin.h|_ _m128 _mm_cmpneq_ps (\__m128、\__m128)|
|[_mm_cmpneq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpneq_sd)|SSE2|intrin.h|__m128d _mm_cmpneq_sd(\__m128d,\__m128d)|
|[_mm_cmpneq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpneq_ss)|SSE|intrin.h|_ _m128 _mm_cmpneq_ss (\__m128、\__m128)|
|[_mm_cmpnge_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnge_pd)|SSE2|intrin.h|__m128d _mm_cmpnge_pd(\__m128d,\__m128d)|
|[_mm_cmpnge_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnge_ps)|SSE|intrin.h|_ _m128 _mm_cmpnge_ps (\__m128、\__m128)|
|[_mm_cmpnge_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnge_sd)|SSE2|intrin.h|__m128d _mm_cmpnge_sd(\__m128d,\__m128d)|
|[_mm_cmpnge_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnge_ss)|SSE|intrin.h|_ _m128 _mm_cmpnge_ss (\__m128、\__m128)|
|[_mm_cmpngt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpngt_pd)|SSE2|intrin.h|__m128d _mm_cmpngt_pd(\__m128d,\__m128d)|
|[_mm_cmpngt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpngt_ps)|SSE|intrin.h|_ _m128 _mm_cmpngt_ps (\__m128、\__m128)|
|[_mm_cmpngt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpngt_sd)|SSE2|intrin.h|__m128d _mm_cmpngt_sd(\__m128d,\__m128d)|
|[_mm_cmpngt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpngt_ss)|SSE|intrin.h|_ _m128 _mm_cmpngt_ss (\__m128、\__m128)|
|[_mm_cmpnle_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnle_pd)|SSE2|intrin.h|__m128d _mm_cmpnle_pd(\__m128d,\__m128d)|
|[_mm_cmpnle_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnle_ps)|SSE|intrin.h|_ _m128 _mm_cmpnle_ps (\__m128、\__m128)|
|[_mm_cmpnle_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnle_sd)|SSE2|intrin.h|__m128d _mm_cmpnle_sd(\__m128d,\__m128d)|
|[_mm_cmpnle_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnle_ss)|SSE|intrin.h|_ _m128 _mm_cmpnle_ss (\__m128、\__m128)|
|[_mm_cmpnlt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnlt_pd)|SSE2|intrin.h|__m128d _mm_cmpnlt_pd(\__m128d,\__m128d)|
|[_mm_cmpnlt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnlt_ps)|SSE|intrin.h|_ _m128 _mm_cmpnlt_ps (\__m128、\__m128)|
|[_mm_cmpnlt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnlt_sd)|SSE2|intrin.h|__m128d _mm_cmpnlt_sd(\__m128d,\__m128d)|
|[_mm_cmpnlt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnlt_ss)|SSE|intrin.h|_ _m128 _mm_cmpnlt_ss (\__m128、\__m128)|
|[_mm_cmpord_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpord_pd)|SSE2|intrin.h|__m128d _mm_cmpord_pd(\__m128d,\__m128d)|
|[_mm_cmpord_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpord_ps)|SSE|intrin.h|__m128 _mm_cmpord_ps(\__m128,\__m128)|
|[_mm_cmpord_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpord_sd)|SSE2|intrin.h|__m128d _mm_cmpord_sd(\__m128d,\__m128d)|
|[_mm_cmpord_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpord_ss)|SSE|intrin.h|_ _m128 _mm_cmpord_ss (\__m128、\__m128)|
|[_mm_cmpunord_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpunord_pd)|SSE2|intrin.h|__m128d _mm_cmpunord_pd(\__m128d,\__m128d)|
|[_mm_cmpunord_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpunord_ps)|SSE|intrin.h|_ _m128 _mm_cmpunord_ps (\__m128、\__m128)|
|[_mm_cmpunord_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpunord_sd)|SSE2|intrin.h|__m128d _mm_cmpunord_sd(\__m128d,\__m128d)|
|[_mm_cmpunord_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpunord_ss)|SSE|intrin.h|_ _m128 _mm_cmpunord_ss (\__m128、\__m128)|
|_mm_com_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_com_epi16 (\__m128i、\__m128i、int)|
|_mm_com_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_com_epi32 (\__m128i、\__m128i、int)|
|_mm_com_epi64|XOP [1]|ammintrin.h|_ _m128i _mm_com_epi32 (\__m128i、\__m128i、int)|
|_mm_com_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_com_epi8 (\__m128i、\__m128i、int)|
|_mm_com_epu16|XOP [1]|ammintrin.h|_ _m128i _mm_com_epu16 (\__m128i、\__m128i、int)|
|_mm_com_epu32|XOP [1]|ammintrin.h|_ _m128i _mm_com_epu32 (\__m128i、\__m128i、int)|
|_mm_com_epu64|XOP [1]|ammintrin.h|_ _m128i _mm_com_epu32 (\__m128i、\__m128i、int)|
|_mm_com_epu8|XOP [1]|ammintrin.h|_ _m128i _mm_com_epu8 (\__m128i、\__m128i、int)|
|[_mm_comieq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comieq_sd)|SSE2|intrin.h|int _mm_comieq_sd(\__m128d,\__m128d)|
|[_mm_comieq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comieq_ss)|SSE|intrin.h|int _mm_comieq_ss (\__m128、\__m128)|
|[_mm_comige_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comige_sd)|SSE2|intrin.h|int _mm_comige_sd(\__m128d,\__m128d)|
|[_mm_comige_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comige_ss)|SSE|intrin.h|int _mm_comige_ss (\__m128、\__m128)|
|[_mm_comigt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comigt_sd)|SSE2|intrin.h|int _mm_comigt_sd(\__m128d,\__m128d)|
|[_mm_comigt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comigt_ss)|SSE|intrin.h|int _mm_comigt_ss (\__m128、\__m128)|
|[_mm_comile_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comile_sd)|SSE2|intrin.h|int _mm_comile_sd(\__m128d,\__m128d)|
|[_mm_comile_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comile_ss)|SSE|intrin.h|int _mm_comile_ss (\__m128、\__m128)|
|[_mm_comilt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comilt_sd)|SSE2|intrin.h|int _mm_comilt_sd(\__m128d,\__m128d)|
|[_mm_comilt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comilt_ss)|SSE|intrin.h|int _mm_comilt_ss (\__m128、\__m128)|
|[_mm_comineq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comineq_sd)|SSE2|intrin.h|int _mm_comineq_sd(\__m128d,\__m128d)|
|[_mm_comineq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comineq_ss)|SSE|intrin.h|int _mm_comineq_ss (\__m128、\__m128)|
|[_mm_crc32_u16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_crc32_u16)|SSE42|intrin.h|unsigned int _mm_crc32_u16(unsigned int,unsigned short)|
|[_mm_crc32_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_crc32_u32)|SSE42|intrin.h|unsigned int _mm_crc32_u32(unsigned int,unsigned int)|
|[_mm_crc32_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_crc32_u64)|SSE42|intrin.h|unsigned __int64 _mm_crc32_u64(unsigned \__int64,unsigned \__int64)|
|[_mm_crc32_u8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_crc32_u8)|SSE42|intrin.h|unsigned int _mm_crc32_u8(unsigned int,unsigned char)|
|[_mm_cvt_si2ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvt_si2ss)|SSE|intrin.h|__m128 _mm_cvt_si2ss(\__m128,int)|
|[_mm_cvt_ss2si](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvt_ss2si)|SSE|intrin.h|int _mm_cvt_ss2si (\__m128)|
|[_mm_cvtepi16_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi16_epi32)|SSE41|intrin.h|_ _m128i _mm_cvtepi16_epi32 (\__m128i)|
|[_mm_cvtepi16_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi16_epi64)|SSE41|intrin.h|_ _m128i _mm_cvtepi16_epi64 (\__m128i)|
|[_mm_cvtepi32_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi32_epi64)|SSE41|intrin.h|_ _m128i _mm_cvtepi32_epi64 (\__m128i)|
|[_mm_cvtepi32_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi32_pd)|SSE2|intrin.h|__m128d _mm_cvtepi32_pd(\__m128i)|
|[_mm_cvtepi32_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi32_ps)|SSE2|intrin.h|_ _m128 _mm_cvtepi32_ps (\__m128i)|
|[_mm_cvtepi8_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi8_epi16)|SSE41|intrin.h|_ _m128i _mm_cvtepi8_epi16 (\__m128i)|
|[_mm_cvtepi8_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi8_epi32)|SSE41|intrin.h|_ _m128i _mm_cvtepi8_epi32 (\__m128i)|
|[_mm_cvtepi8_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi8_epi64)|SSE41|intrin.h|_ _m128i _mm_cvtepi8_epi64 (\__m128i)|
|[_mm_cvtepu16_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu16_epi32)|SSE41|intrin.h|_ _m128i _mm_cvtepu16_epi32 (\__m128i)|
|[_mm_cvtepu16_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu16_epi64)|SSE41|intrin.h|_ _m128i _mm_cvtepu16_epi64 (\__m128i)|
|[_mm_cvtepu32_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu32_epi64)|SSE41|intrin.h|_ _m128i _mm_cvtepu32_epi64 (\__m128i)|
|[_mm_cvtepu8_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu8_epi16)|SSE41|intrin.h|_ _m128i _mm_cvtepu8_epi16 (\__m128i)|
|[_mm_cvtepu8_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu8_epi32)|SSE41|intrin.h|_ _m128i _mm_cvtepu8_epi32 (\__m128i)|
|[_mm_cvtepu8_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu8_epi64)|SSE41|intrin.h|_ _m128i _mm_cvtepu8_epi64 (\__m128i)|
|[_mm_cvtpd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtpd_epi32)|SSE2|intrin.h|__m128i _mm_cvtpd_epi32(\__m128d)|
|[_mm_cvtpd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtpd_ps)|SSE2|intrin.h|__m128 _mm_cvtpd_ps(\__m128d)|
|[_mm_cvtph_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtph_ps)|F16C [2]|immintrin.h|__m128 _mm_cvtph_ps(\__m128i)|
|[_mm_cvtps_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtps_epi32)|SSE2|intrin.h|__m128i _mm_cvtps_epi32(\__m128)|
|[_mm_cvtps_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtps_pd)|SSE2|intrin.h|__m128d _mm_cvtps_pd(\__m128)|
|[_mm_cvtps_ph](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtps_ph)|F16C [2]|immintrin.h|_ _m128i _mm_cvtps_ph (\__m128、const int)|
|[_mm_cvtsd_f64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsd_f64)|SSSE3|intrin.h|double _mm_cvtsd_f64(\__m128d)|
|[_mm_cvtsd_si32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsd_si32)|SSE2|intrin.h|int _mm_cvtsd_si32 (\__m128d)|
|[_mm_cvtsd_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsd_si64)|SSE2|intrin.h|__int64 _mm_cvtsd_si64(\__m128d)|
|[_mm_cvtsd_si64x](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsd_si64x)|SSE2|intrin.h|__int64 _mm_cvtsd_si64x(\__m128d a)|
|[_mm_cvtsd_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsd_ss)|SSE2|intrin.h|_ _m128 _mm_cvtsd_ss (\__m128、\__m128d)|
|[_mm_cvtsi128_si32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi128_si32)|SSE2|intrin.h|int _mm_cvtsi128_si32(\__m128i)|
|[_mm_cvtsi128_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi128_si64)|SSE2|intrin.h|__int64 _mm_cvtsi128_si64(\__m128i)|
|[_mm_cvtsi128_si64x](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi128_si64x)|SSE2|intrin.h|__int64 _mm_cvtsi128_si64x(\__m128i a)|
|[_mm_cvtsi32_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi32_sd)|SSE2|intrin.h|__m128d _mm_cvtsi32_sd(\__m128d,int)|
|[_mm_cvtsi32_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi32_si128)|SSE2|intrin.h|__m128i _mm_cvtsi32_si128(int)|
|[_mm_cvtsi64_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi64_sd)|SSE2|intrin.h|__m128d _mm_cvtsi64_sd(\__m128d,\__int64)|
|[_mm_cvtsi64_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi64_si128)|SSE2|intrin.h|__m128i _mm_cvtsi64_si128(\__int64)|
|[_mm_cvtsi64_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi64_ss)|SSE|intrin.h|_ _m128 _mm_cvtsi64_ss (\__m128、\__ _int64)|
|[_mm_cvtsi64x_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi64x_sd)|SSE2|intrin.h|_ _m128d _mm_cvtsi64x_sd (\__m128d、\__ _int64 b)。|
|[_mm_cvtsi64x_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi64x_si128)|SSE2|intrin.h|_ _m128i _mm_cvtsi64x_si128 (\__ _int64 を)|
|[_mm_cvtsi64x_ss](../intrinsics/mm-cvtsi64x-ss.md)|SSE2|intrin.h|_ _m128 _mm_cvtsi64x_ss (\__m128、\__ _int64 b)。|
|[_mm_cvtss_f32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtss_f32)|SSSE3|intrin.h|float _mm_cvtss_f32 (\__m128)|
|[_mm_cvtss_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtss_sd)|SSE2|intrin.h|__m128d _mm_cvtss_sd(\__m128d,\__m128)|
|[_mm_cvtss_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtss_si64)|SSE|intrin.h|__int64 _mm_cvtss_si64(\__m128)|
|[_mm_cvtss_si64x](../intrinsics/mm-cvtss-si64x.md)|SSE2|intrin.h|__int64 _mm_cvtss_si64x(\__m128 a)|
|[_mm_cvtt_ss2si](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtt_ss2si)|SSE|intrin.h|int _mm_cvtt_ss2si (\__m128)|
|[_mm_cvttpd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttpd_epi32)|SSE2|intrin.h|_ _m128i _mm_cvttpd_epi32 (\__m128d)|
|[_mm_cvttps_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttps_epi32)|SSE2|intrin.h|_ _m128i _mm_cvttps_epi32 (\__m128)|
|[_mm_cvttsd_si32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttsd_si32)|SSE2|intrin.h|int _mm_cvttsd_si32 (\__m128d)|
|[_mm_cvttsd_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttsd_si64)|SSE2|intrin.h|__int64 _mm_cvttsd_si64(\__m128d)|
|[_mm_cvttsd_si64x](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttsd_si64x)|SSE2|intrin.h|__int64 _mm_cvttsd_si64x(\__m128d a)|
|[_mm_cvttss_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttss_si64)|SSE2|intrin.h|__int64 _mm_cvttss_si64(\__m128)|
|[_mm_cvttss_si64x](../intrinsics/mm-cvttss-si64x.md)|SSE2|intrin.h|__int64 _mm_cvttss_si64x(\__m128 a)|
|[_mm_div_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_div_pd)|SSE2|intrin.h|__m128d _mm_div_pd(\__m128d,\__m128d)|
|[_mm_div_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_div_ps)|SSE|intrin.h|__m128 _mm_div_ps(\__m128,\__m128)|
|[_mm_div_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_div_sd)|SSE2|intrin.h|__m128d _mm_div_sd(\__m128d,\__m128d)|
|[_mm_div_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_div_ss)|SSE|intrin.h|__m128 _mm_div_ss(\__m128,\__m128)|
|[_mm_dp_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_dp_pd)|SSE41|intrin.h|_ _m128d _mm_dp_pd (\__m128d、\__m128d、const int)|
|[_mm_dp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_dp_ps)|SSE41|intrin.h|_ _m128 _mm_dp_ps (\__m128、\__m128、const int)|
|[_mm_extract_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_extract_epi16)|SSE2|intrin.h|int _mm_extract_epi16(\__m128i,int)|
|[_mm_extract_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_extract_epi32)|SSE41|intrin.h|int   _mm_extract_epi32(\__m128i,const int )|
|[_mm_extract_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_extract_epi64)|SSE41|intrin.h|_ _int64 _mm_extract_epi64 (\__m128i、const int)|
|[_mm_extract_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_extract_epi8)|SSE41|intrin.h|int _mm_extract_epi8 (\__m128i、const int)|
|[_mm_extract_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_extract_ps)|SSE41|intrin.h|int _mm_extract_ps (\__m128、const int)|
|[_mm_extract_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)|SSE4a|intrin.h|_ _m128i _mm_extract_si64 (\__m128i、\__m128i)|
|[_mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)|SSE4a|intrin.h|_ _m128i _mm_extracti_si64 (\__m128i、int, int)|
|[_mm_fmadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmadd_pd)|FMA [2]|immintrin.h|_ _m128d _mm_fmadd_pd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fmadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmadd_ps)|FMA [2]|immintrin.h|_ _m128 _mm_fmadd_ps (\__m128、\__m128 b、\__m128 c).|
|[_mm_fmadd_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmadd_sd)|FMA [2]|immintrin.h|_ _m128d _mm_fmadd_sd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fmadd_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmadd_ss)|FMA [2]|immintrin.h|_ _m128 _mm_fmadd_ss (\__m128、\__m128 b、\__m128 c).|
|[_mm_fmaddsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmaddsub_pd)|FMA [2]|immintrin.h|_ _m128d _mm_fmaddsub_pd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fmaddsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmaddsub_ps)|FMA [2]|immintrin.h|_ _m128 _mm_fmaddsub_ps (\__m128、\__m128 b、\__m128 c).|
|[_mm_fmsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsub_pd)|FMA [2]|immintrin.h|_ _m128d _mm_fmsub_pd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fmsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsub_ps)|FMA [2]|immintrin.h|_ _m128 _mm_fmsub_ps (\__m128、\__m128 b、\__m128 c).|
|[_mm_fmsub_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsub_sd)|FMA [2]|immintrin.h|_ _m128d _mm_fmsub_sd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fmsub_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsub_ss)|FMA [2]|immintrin.h|_ _m128 _mm_fmsub_ss (\__m128、\__m128 b、\__m128 c).|
|[_mm_fmsubadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsubadd_pd)|FMA [2]|immintrin.h|_ _m128d _mm_fmsubadd_pd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fmsubadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsubadd_ps)|FMA [2]|immintrin.h|_ _m128 _mm_fmsubadd_ps (\__m128、\__m128 b、\__m128 c).|
|[_mm_fnmadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmadd_pd)|FMA [2]|immintrin.h|_ _m128d _mm_fnmadd_pd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fnmadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmadd_ps)|FMA [2]|immintrin.h|_ _m128 _mm_fnmadd_ps (\__m128、\__m128 b、\__m128 c).|
|[_mm_fnmadd_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmadd_sd)|FMA [2]|immintrin.h|_ _m128d _mm_fnmadd_sd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fnmadd_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmadd_ss)|FMA [2]|immintrin.h|_ _m128 _mm_fnmadd_ss (\__m128、\__m128 b、\__m128 c).|
|[_mm_fnmsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmsub_pd)|FMA [2]|immintrin.h|_ _m128d _mm_fnmsub_pd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fnmsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmsub_ps)|FMA [2]|immintrin.h|_ _m128 _mm_fnmsub_ps (\__m128、\__m128 b、\__m128 c).|
|[_mm_fnmsub_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmsub_sd)|FMA [2]|immintrin.h|_ _m128d _mm_fnmsub_sd (\__m128d、\__m128d b、\__m128d c).|
|[_mm_fnmsub_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmsub_ss)|FMA [2]|immintrin.h|_ _m128 _mm_fnmsub_ss (\__m128、\__m128 b、\__m128 c).|
|_mm_frcz_pd|XOP [1]|ammintrin.h|__m128d _mm_frcz_pd(\__m128d)|
|_mm_frcz_ps|XOP [1]|ammintrin.h|_ _m128 _mm_frcz_ps (\__m128)|
|_mm_frcz_sd|XOP [1]|ammintrin.h|__m128d _mm_frcz_sd(\__m128d,\__m128d)|
|_mm_frcz_ss|XOP [1]|ammintrin.h|_ _m128 _mm_frcz_ss (\__m128、\__m128)|
|[_mm_getcsr](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_getcsr)|SSE|intrin.h|unsigned int _mm_getcsr(void)|
|[_mm_hadd_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_epi16)|SSSE3|intrin.h|_ _m128i _mm_hadd_epi16 (\__m128i、\__m128i)|
|[_mm_hadd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_epi32)|SSSE3|intrin.h|_ _m128i _mm_hadd_epi32 (\__m128i、\__m128i)|
|[_mm_hadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_pd)|SSE3|intrin.h|__m128d _mm_hadd_pd(\__m128d,\__m128d)|
|[_mm_hadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_ps)|SSE3|intrin.h|_ _m128 _mm_hadd_ps (\__m128、\__m128)|
|_mm_haddd_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_haddd_epi16 (\__m128i)|
|_mm_haddd_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_haddd_epi8 (\__m128i)|
|_mm_haddd_epu16|XOP [1]|ammintrin.h|_ _m128i _mm_haddd_epu16 (\__m128i)|
|_mm_haddd_epu8|XOP [1]|ammintrin.h|_ _m128i _mm_haddd_epu8 (\__m128i)|
|_mm_haddq_epi16|XOP [1]|ammintrin.h|__m128i _mm_haddq_epi16(\__m128i)|
|_mm_haddq_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_haddq_epi32 (\__m128i)|
|_mm_haddq_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_haddq_epi8 (\__m128i)|
|_mm_haddq_epu16|XOP [1]|ammintrin.h|_ _m128i _mm_haddq_epu16 (\__m128i)|
|_mm_haddq_epu32|XOP [1]|ammintrin.h|_ _m128i _mm_haddq_epu32 (\__m128i)|
|_mm_haddq_epu8|XOP [1]|ammintrin.h|_ _m128i _mm_haddq_epu8 (\__m128i)|
|[_mm_hadds_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadds_epi16)|SSSE3|intrin.h|_ _m128i _mm_hadds_epi16 (\__m128i、\__m128i)|
|_mm_haddw_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_haddw_epi8 (\__m128i)|
|_mm_haddw_epu8|XOP [1]|ammintrin.h|_ _m128i _mm_haddw_epu8 (\__m128i)|
|[_mm_hsub_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_epi16)|SSSE3|intrin.h|_ _m128i _mm_hsub_epi16 (\__m128i、\__m128i)|
|[_mm_hsub_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_epi32)|SSSE3|intrin.h|_ _m128i _mm_hsub_epi32 (\__m128i、\__m128i)|
|[_mm_hsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_pd)|SSE3|intrin.h|__m128d _mm_hsub_pd(\__m128d,\__m128d)|
|[_mm_hsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_ps)|SSE3|intrin.h|_ _m128 _mm_hsub_ps (\__m128、\__m128)|
|_mm_hsubd_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_hsubd_epi16 (\__m128i)|
|_mm_hsubq_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_hsubq_epi32 (\__m128i)|
|[_mm_hsubs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsubs_epi16)|SSSE3|intrin.h|_ _m128i _mm_hsubs_epi16 (\__m128i、\__m128i)|
|_mm_hsubw_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_hsubw_epi8 (\__m128i)|
|[_mm_i32gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i32gather_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_i32gather_epi32 (const int\*ベース、\__m128i キーワード、const int スケール)|
|[_mm_i32gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i32gather_epi64)|AVX2 [2]|immintrin.h|_ _m128i _mm_i32gather_epi64 (\__ _int64 const\*ベース\__m128i キーワード、const int スケール)|
|[_mm_i32gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i32gather_pd)|AVX2 [2]|immintrin.h|_ _m128d _mm_i32gather_pd (二重 const\*ベース、\__m128i キーワード、const int スケール)|
|[_mm_i32gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i32gather_ps)|AVX2 [2]|immintrin.h|_ _m128 _mm_i32gather_ps (float、const\*ベース、\__m128i キーワード、const int スケール)|
|[_mm_i64gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i64gather_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_i64gather_epi32 (const int\*ベース、\__m128i キーワード、const int スケール)|
|[_mm_i64gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i64gather_epi64)|AVX2 [2]|immintrin.h|_ _m128i _mm_i64gather_epi64 (\__ _int64 const\*ベース\__m128i キーワード、const int スケール)|
|[_mm_i64gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i64gather_pd)|AVX2 [2]|immintrin.h|_ _m128d _mm_i64gather_pd (二重 const\*ベース、\__m128i キーワード、const int スケール)|
|[_mm_i64gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i64gather_ps)|AVX2 [2]|immintrin.h|_ _m128 _mm_i64gather_ps (float、const\*ベース、\__m128i キーワード、const int スケール)|
|[_mm_insert_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_insert_epi16)|SSE2|intrin.h|_ _m128i _mm_insert_epi16 (\__m128i、int, int)|
|[_mm_insert_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_insert_epi32)|SSE41|intrin.h|_ _m128i _mm_insert_epi32 (\__m128i、int、const int)|
|[_mm_insert_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_insert_epi64)|SSE41|intrin.h|_ _m128i _mm_insert_epi64 (\__m128i、\_const int、_ _int64)|
|[_mm_insert_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_insert_epi8)|SSE41|intrin.h|_ _m128i _mm_insert_epi8 (\__m128i、int、const int)|
|[_mm_insert_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_insert_ps)|SSE41|intrin.h|_ _m128 _mm_insert_ps (\__m128、\__m128、const int)|
|[_mm_insert_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)|SSE4a|intrin.h|_ _m128i _mm_insert_si64 (\__m128i、\__m128i)|
|[_mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)|SSE4a|intrin.h|_ _m128i _mm_inserti_si64 (\__m128i、\__m128i、int, int)|
|[_mm_lddqu_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_lddqu_si128)|SSE3|intrin.h|_ _m128i _mm_lddqu_si128 (\__m128i const\*)|
|[_mm_lfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_lfence)|SSE2|intrin.h|void _mm_lfence(void)|
|[_mm_load_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_pd)|SSE2|intrin.h|_ _m128d _mm_load_pd (double\*)|
|[_mm_load_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_ps)|SSE|intrin.h|_ _m128 _mm_load_ps (float\*)|
|[_mm_load_ps1](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_ps1)|SSE|intrin.h|_ _m128 _mm_load_ps1 (float\*)|
|[_mm_load_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_sd)|SSE2|intrin.h|_ _m128d _mm_load_sd (double\*)|
|[_mm_load_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_si128)|SSE2|intrin.h|_ _m128i _mm_load_si128 (\__m128i\*)|
|[_mm_load_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_ss)|SSE|intrin.h|_ _m128 _mm_load_ss (float\*)|
|[_mm_load1_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load1_pd)|SSE2|intrin.h|_ _m128d _mm_load1_pd (double\*)|
|[_mm_loaddup_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loaddup_pd)|SSE3|intrin.h|_ _m128d _mm_loaddup_pd (二重 const\*)|
|[_mm_loadh_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadh_pd)|SSE2|intrin.h|_ _m128d _mm_loadh_pd (\__m128d、二重\*)|
|[_mm_loadh_pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadh_pi)|SSE|intrin.h|_ _m128 _mm_loadh_pi (\__m128、\__m64\*)|
|[_mm_loadl_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadl_epi64)|SSE2|intrin.h|_ _m128i _mm_loadl_epi64 (\__m128i\*)|
|[_mm_loadl_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadl_pd)|SSE2|intrin.h|_ _m128d _mm_loadl_pd (\__m128d、二重\*)|
|[_mm_loadl_pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadl_pi)|SSE|intrin.h|_ _m128 _mm_loadl_pi (\__m128、\__m64\*)|
|[_mm_loadr_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadr_pd)|SSE2|intrin.h|_ _m128d _mm_loadr_pd (double\*)|
|[_mm_loadr_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadr_ps)|SSE|intrin.h|_ _m128 _mm_loadr_ps (float\*)|
|[_mm_loadu_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadu_pd)|SSE2|intrin.h|_ _m128d _mm_loadu_pd (double\*)|
|[_mm_loadu_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadu_ps)|SSE|intrin.h|_ _m128 _mm_loadu_ps (float\*)|
|[_mm_loadu_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadu_si128)|SSE2|intrin.h|_ _m128i _mm_loadu_si128 (\__m128i\*)|
|_mm_macc_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_macc_epi16 (\__m128i、\__m128i、\__m128i)|
|_mm_macc_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_macc_epi32 (\__m128i、\__m128i、\__m128i)|
|_mm_macc_pd|FMA4 [1]|ammintrin.h|__m128d _mm_macc_pd(\__m128d,\__m128d,\__m128d)|
|_mm_macc_ps|FMA4 [1]|ammintrin.h|_ _m128 _mm_macc_ps (\__m128、\__m128、\__m128)|
|_mm_macc_sd|FMA4 [1]|ammintrin.h|__m128d _mm_macc_sd(\__m128d,\__m128d,\__m128d)|
|_mm_macc_ss|FMA4 [1]|ammintrin.h|_ _m128 _mm_macc_ss (\__m128、\__m128、\__m128)|
|_mm_maccd_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_maccd_epi16 (\__m128i、\__m128i、\__m128i)|
|_mm_macchi_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_macchi_epi32 (\__m128i、\__m128i、\__m128i)|
|_mm_macclo_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_macclo_epi32 (\__m128i、\__m128i、\__m128i)|
|_mm_maccs_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_maccs_epi16 (\__m128i、\__m128i、\__m128i)|
|_mm_maccs_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_maccs_epi32 (\__m128i、\__m128i、\__m128i)|
|_mm_maccsd_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_maccsd_epi16 (\__m128i、\__m128i、\__m128i)|
|_mm_maccshi_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_maccshi_epi32 (\__m128i、\__m128i、\__m128i)|
|_mm_maccslo_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_maccslo_epi32 (\__m128i、\__m128i、\__m128i)|
|[_mm_madd_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_madd_epi16)|SSE2|intrin.h|_ _m128i _mm_madd_epi16 (\__m128i、\__m128i)|
|_mm_maddd_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_maddd_epi16 (\__m128i、\__m128i、\__m128i)|
|_mm_maddsd_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_maddsd_epi16 (\__m128i、\__m128i、\__m128i)|
|_mm_maddsub_pd|FMA4 [1]|ammintrin.h|__m128d _mm_maddsub_pd(\__m128d,\__m128d,\__m128d)|
|_mm_maddsub_ps|FMA4 [1]|ammintrin.h|_ _m128 _mm_maddsub_ps (\__m128、\__m128、\__m128)|
|[_mm_maddubs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maddubs_epi16)|SSSE3|intrin.h|_ _m128i _mm_maddubs_epi16 (\__m128i、\__m128i)|
|[_mm_mask_i32gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i32gather_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_mask_i32gather_epi32 (\__m128i src、const int\*ベース\__m128i キーワード、\__m128i マスク、const int スケール)|
|[_mm_mask_i32gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i32gather_epi64)|AVX2 [2]|immintrin.h|_ _m128i _mm_mask_i32gather_epi64 (\__m128i src、\__ _int64 const\*ベース\__m128i キーワード、\__m128i マスク、const int スケール)|
|[_mm_mask_i32gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i32gather_pd)|AVX2 [2]|immintrin.h|_ _m128d _mm_mask_i32gather_pd (\__m128d src、二重 const\*ベース\__m128i キーワード、\__m128d マスク、const int スケール)|
|[_mm_mask_i32gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i32gather_ps)|AVX2 [2]|immintrin.h|_ _m128 _mm_mask_i32gather_ps (\__m128 src、float 型の const\*ベース\__m128i キーワード、\__m128 マスク、const int スケール)|
|[_mm_mask_i64gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i64gather_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_mask_i64gather_epi32 (\__m128i src、const int\*ベース\__m128i キーワード、\__m128i マスク、const int スケール)|
|[_mm_mask_i64gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i64gather_epi64)|AVX2 [2]|immintrin.h|_ _m128i _mm_mask_i64gather_epi64 (\__m128i src、\__ _int64 const\*ベース\__m128i キーワード、\__m128i マスク、const int スケール)|
|[_mm_mask_i64gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i64gather_pd)|AVX2 [2]|immintrin.h|_ _m128d _mm_mask_i64gather_pd (\__m128d src、二重 const\*ベース\__m128i キーワード、\__m128d マスク、const int スケール)|
|[_mm_mask_i64gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i64gather_ps)|AVX2 [2]|immintrin.h|_ _m128 _mm_mask_i64gather_ps (\__m128 src、float 型の const\*ベース\__m128i キーワード、\__m128 マスク、const int スケール)|
|[_mm_maskload_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskload_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_maskload_epi32 (const int \*、\__m128i)|
|[_mm_maskload_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskload_epi64)|AVX2 [2]|immintrin.h|_ _m128i _mm_maskload_epi64 ( \__ _int64 const \*、\__m128i)|
|[_mm_maskload_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskload_pd)|AVX [2]|immintrin.h|_ _m128d _mm_maskload_pd (二重 const \*、\__m128i)|
|[_mm_maskload_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskload_ps)|AVX [2]|immintrin.h|_ _m128 _mm_maskload_ps (float、const \*、\__m128i)|
|[_mm_maskmoveu_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskmoveu_si128)|SSE2|intrin.h|void _mm_maskmoveu_si128 (\__m128i、\__m128i、char\*)|
|[_mm_maskstore_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskstore_epi32)|AVX2 [2]|immintrin.h|void _mm_maskstore_epi32 (int \*、\__m128i、\__m128i)|
|[_mm_maskstore_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskstore_epi64)|AVX2 [2]|immintrin.h|void _mm_maskstore_epi64 (\__ _int64 \*、\__m128i、\__m128i)|
|[_mm_maskstore_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskstore_pd)|AVX [2]|immintrin.h|void _mm_maskstore_pd (double \*、\__m128i、\__m128d)|
|[_mm_maskstore_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskstore_ps)|AVX [2]|immintrin.h|void _mm_maskstore_ps (float \*、\__m128i、\__m128)|
|[_mm_max_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epi16)|SSE2|intrin.h|_ _m128i _mm_max_epi16 (\__m128i、\__m128i)|
|[_mm_max_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epi32)|SSE41|intrin.h|_ _m128i _mm_max_epi32 (\__m128i、\__m128i)|
|[_mm_max_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epi8)|SSE41|intrin.h|_ _m128i _mm_max_epi8 (\__m128i、\__m128i)|
|[_mm_max_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epu16)|SSE41|intrin.h|_ _m128i _mm_max_epu16 (\__m128i、\__m128i)|
|[_mm_max_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epu32)|SSE41|intrin.h|_ _m128i _mm_max_epu32 (\__m128i、\__m128i)|
|[_mm_max_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epu8)|SSE2|intrin.h|_ _m128i _mm_max_epu8 (\__m128i、\__m128i)|
|[_mm_max_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_pd)|SSE2|intrin.h|__m128d _mm_max_pd(\__m128d,\__m128d)|
|[_mm_max_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_ps)|SSE|intrin.h|_ _m128 _mm_max_ps (\__m128、\__m128)|
|[_mm_max_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_sd)|SSE2|intrin.h|__m128d _mm_max_sd(\__m128d,\__m128d)|
|[_mm_max_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_ss)|SSE|intrin.h|_ _m128 _mm_max_ss (\__m128、\__m128)|
|[_mm_mfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mfence)|SSE2|intrin.h|void _mm_mfence(void)|
|[_mm_min_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epi16)|SSE2|intrin.h|_ _m128i _mm_min_epi16 (\__m128i、\__m128i)|
|[_mm_min_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epi32)|SSE41|intrin.h|_ _m128i _mm_min_epi32 (\__m128i、\__m128i)|
|[_mm_min_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epi8)|SSE41|intrin.h|_ _m128i _mm_min_epi8 (\__m128i、\__m128i)|
|[_mm_min_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epu16)|SSE41|intrin.h|_ _m128i _mm_min_epu16 (\__m128i、\__m128i)|
|[_mm_min_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epu32)|SSE41|intrin.h|_ _m128i _mm_min_epu32 (\__m128i、\__m128i)|
|[_mm_min_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epu8)|SSE2|intrin.h|_ _m128i _mm_min_epu8 (\__m128i、\__m128i)|
|[_mm_min_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_pd)|SSE2|intrin.h|__m128d _mm_min_pd(\__m128d,\__m128d)|
|[_mm_min_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_ps)|SSE|intrin.h|_ _m128 _mm_min_ps (\__m128、\__m128)|
|[_mm_min_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_sd)|SSE2|intrin.h|__m128d _mm_min_sd(\__m128d,\__m128d)|
|[_mm_min_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_ss)|SSE|intrin.h|_ _m128 _mm_min_ss (\__m128、\__m128)|
|[_mm_minpos_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_minpos_epu16)|SSE41|intrin.h|_ _m128i _mm_minpos_epu16 (\__m128i)|
|[_mm_monitor](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_monitor)|SSE3|intrin.h|void _mm_monitor (const void\*、符号なしの int、unsigned int)|
|[_mm_move_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_move_epi64)|SSE2|intrin.h|_ _m128i _mm_move_epi64 (\__m128i)|
|[_mm_move_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_move_sd)|SSE2|intrin.h|__m128d _mm_move_sd(\__m128d,\__m128d)|
|[_mm_move_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_move_ss)|SSE|intrin.h|_ _m128 _mm_move_ss (\__m128、\__m128)|
|[_mm_movedup_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movedup_pd)|SSE3|intrin.h|__m128d _mm_movedup_pd(\__m128d)|
|[_mm_movehdup_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movehdup_ps)|SSE3|intrin.h|_ _m128 _mm_movehdup_ps (\__m128)|
|[_mm_movehl_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movehl_ps)|SSE|intrin.h|_ _m128 _mm_movehl_ps (\__m128、\__m128)|
|[_mm_moveldup_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_moveldup_ps)|SSE3|intrin.h|_ _m128 _mm_moveldup_ps (\__m128)|
|[_mm_movelh_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movelh_ps)|SSE|intrin.h|_ _m128 _mm_movelh_ps (\__m128、\__m128)|
|[_mm_movemask_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movemask_epi8)|SSE2|intrin.h|int _mm_movemask_epi8 (\__m128i)|
|[_mm_movemask_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movemask_pd)|SSE2|intrin.h|int _mm_movemask_pd(\__m128d)|
|[_mm_movemask_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movemask_ps)|SSE|intrin.h|int _mm_movemask_ps(\__m128)|
|[_mm_mpsadbw_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mpsadbw_epu8)|SSE41|intrin.h|_ _m128i _mm_mpsadbw_epu8 (\__m128i s1、\__m128i、const int)|
|_mm_msub_pd|FMA4 [1]|ammintrin.h|__m128d _mm_msub_pd(\__m128d,\__m128d,\__m128d)|
|_mm_msub_ps|FMA4 [1]|ammintrin.h|_ _m128 _mm_msub_ps (\__m128、\__m128、\__m128)|
|_mm_msub_sd|FMA4 [1]|ammintrin.h|__m128d _mm_msub_sd(\__m128d,\__m128d,\__m128d)|
|_mm_msub_ss|FMA4 [1]|ammintrin.h|_ _m128 _mm_msub_ss (\__m128、\__m128、\__m128)|
|_mm_msubadd_pd|FMA4 [1]|ammintrin.h|__m128d _mm_msubadd_pd(\__m128d,\__m128d,\__m128d)|
|_mm_msubadd_ps|FMA4 [1]|ammintrin.h|_ _m128 _mm_msubadd_ps (\__m128、\__m128、\__m128)|
|[_mm_mul_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_epi32)|SSE41|intrin.h|_ _m128i _mm_mul_epi32 (\__m128i、\__m128i)|
|[_mm_mul_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_epu32)|SSE2|intrin.h|_ _m128i _mm_mul_epu32 (\__m128i、\__m128i)|
|[_mm_mul_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_pd)|SSE2|intrin.h|__m128d _mm_mul_pd(\__m128d,\__m128d)|
|[_mm_mul_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_ps)|SSE|intrin.h|_ _m128 _mm_mul_ps (\__m128、\__m128)|
|[_mm_mul_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_sd)|SSE2|intrin.h|__m128d _mm_mul_sd(\__m128d,\__m128d)|
|[_mm_mul_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_ss)|SSE|intrin.h|_ _m128 _mm_mul_ss (\__m128、\__m128)|
|[_mm_mulhi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mulhi_epi16)|SSE2|intrin.h|_ _m128i _mm_mulhi_epi16 (\__m128i、\__m128i)|
|[_mm_mulhi_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mulhi_epu16)|SSE2|intrin.h|_ _m128i _mm_mulhi_epu16 (\__m128i、\__m128i)|
|[_mm_mulhrs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mulhrs_epi16)|SSSE3|intrin.h|_ _m128i _mm_mulhrs_epi16 (\__m128i、\__m128i)|
|[_mm_mullo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mullo_epi16)|SSE2|intrin.h|_ _m128i _mm_mullo_epi16 (\__m128i、\__m128i)|
|[_mm_mullo_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mullo_epi32)|SSE41|intrin.h|_ _m128i _mm_mullo_epi32 (\__m128i、\__m128i)|
|[_mm_mwait](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mwait)|SSE3|intrin.h|void _mm_mwait(unsigned int,unsigned int)|
|_mm_nmacc_pd|FMA4 [1]|ammintrin.h|__m128d _mm_nmacc_pd(\__m128d,\__m128d,\__m128d)|
|_mm_nmacc_ps|FMA4 [1]|ammintrin.h|_ _m128 _mm_nmacc_ps (\__m128、\__m128、\__m128)|
|_mm_nmacc_sd|FMA4 [1]|ammintrin.h|__m128d _mm_nmacc_sd(\__m128d,\__m128d,\__m128d)|
|_mm_nmacc_ss|FMA4 [1]|ammintrin.h|_ _m128 _mm_nmacc_ss (\__m128、\__m128、\__m128)|
|_mm_nmsub_pd|FMA4 [1]|ammintrin.h|__m128d _mm_nmsub_pd(\__m128d,\__m128d,\__m128d)|
|_mm_nmsub_ps|FMA4 [1]|ammintrin.h|_ _m128 _mm_nmsub_ps (\__m128、\__m128、\__m128)|
|_mm_nmsub_sd|FMA4 [1]|ammintrin.h|__m128d _mm_nmsub_sd(\__m128d,\__m128d,\__m128d)|
|_mm_nmsub_ss|FMA4 [1]|ammintrin.h|_ _m128 _mm_nmsub_ss (\__m128、\__m128、\__m128)|
|[_mm_or_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_or_pd)|SSE2|intrin.h|__m128d _mm_or_pd(\__m128d,\__m128d)|
|[_mm_or_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_or_ps)|SSE|intrin.h|_ _m128 _mm_or_ps (\__m128、\__m128)|
|[_mm_or_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_or_si128)|SSE2|intrin.h|_ _m128i _mm_or_si128 (\__m128i、\__m128i)|
|[_mm_packs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packs_epi16)|SSE2|intrin.h|_ _m128i _mm_packs_epi16 (\__m128i、\__m128i)|
|[_mm_packs_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packs_epi32)|SSE2|intrin.h|_ _m128i _mm_packs_epi32 (\__m128i、\__m128i)|
|[_mm_packus_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packus_epi16)|SSE2|intrin.h|_ _m128i _mm_packus_epi16 (\__m128i、\__m128i)|
|[_mm_packus_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packus_epi32)|SSE41|intrin.h|_ _m128i _mm_packus_epi32 (\__m128i、\__m128i)|
|[_mm_pause](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_pause)|SSE2|intrin.h|void _mm_pause(void)|
|_mm_perm_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_perm_epi8 (\__m128i、\__m128i、\__m128i)|
|[_mm_permute_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_permute_pd)|AVX [2]|immintrin.h|__m128d _mm_permute_pd(\__m128d,int)|
|[_mm_permute_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_permute_ps)|AVX [2]|immintrin.h|_ _m128 _mm_permute_ps (\__m128、int)|
|_mm_permute2_pd|XOP [1]|ammintrin.h|__m128d _mm_permute2_pd(\__m128d,\__m128d,\__m128i,int)|
|_mm_permute2_ps|XOP [1]|ammintrin.h|_ _m128 _mm_permute2_ps (\__m128、\__m128、\__m128i、int)|
|[_mm_permutevar_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_permutevar_pd)|AVX [2]|immintrin.h|__m128d _mm_permutevar_pd(\__m128d,\__m128i)|
|[_mm_permutevar_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_permutevar_ps)|AVX [2]|immintrin.h|_ _m128 _mm_permutevar_ps (\__m128、\__m128i)|
|[_mm_popcnt_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_popcnt_u32)|POPCNT|intrin.h|int _mm_popcnt_u32(unsigned int)|
|[_mm_popcnt_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_popcnt_u64)|POPCNT|intrin.h|__int64 _mm_popcnt_u64(unsigned \__int64)|
|[_mm_prefetch](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_prefetch)|SSE|intrin.h|void _mm_prefetch (char\*int)|
|[_mm_rcp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_rcp_ps)|SSE|intrin.h|_ _m128 _mm_rcp_ps (\__m128)|
|[_mm_rcp_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_rcp_ss)|SSE|intrin.h|_ _m128 _mm_rcp_ss (\__m128)|
|_mm_rot_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_rot_epi16 (\__m128i、\__m128i)|
|_mm_rot_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_rot_epi32 (\__m128i、\__m128i)|
|_mm_rot_epi64|XOP [1]|ammintrin.h|_ _m128i _mm_rot_epi64 (\__m128i、\__m128i)|
|_mm_rot_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_rot_epi8 (\__m128i、\__m128i)|
|_mm_roti_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_rot_epi16 (\__m128i、int)|
|_mm_roti_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_rot_epi32 (\__m128i、int)|
|_mm_roti_epi64|XOP [1]|ammintrin.h|_ _m128i _mm_rot_epi64 (\__m128i、int)|
|_mm_roti_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_rot_epi8 (\__m128i、int)|
|[_mm_round_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_round_pd)|SSE41|intrin.h|__m128d _mm_round_pd(\__m128d,const int )|
|[_mm_round_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_round_ps)|SSE41|intrin.h|_ _m128 _mm_round_ps (\__m128、const int)|
|[_mm_round_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_round_sd)|SSE41|intrin.h|__m128d _mm_round_sd(\__m128d,\__m128d,const int )|
|[_mm_round_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_round_ss)|SSE41|intrin.h|_ _m128 _mm_round_ss (\__m128、\__m128、const int)|
|[_mm_rsqrt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_rsqrt_ps)|SSE|intrin.h|_ _m128 _mm_rsqrt_ps (\__m128)|
|[_mm_rsqrt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_rsqrt_ss)|SSE|intrin.h|_ _m128 _mm_rsqrt_ss (\__m128)|
|[_mm_sad_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sad_epu8)|SSE2|intrin.h|_ _m128i _mm_sad_epu8 (\__m128i、\__m128i)|
|[_mm_set_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_epi16)|SSE2|intrin.h|__m128i _mm_set_epi16(short,short,short,short,short,short,short,short)|
|[_mm_set_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_epi32)|SSE2|intrin.h|__m128i _mm_set_epi32(int,int,int,int)|
|[_mm_set_epi64x](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_epi64x)|SSE2|intrin.h|__m128i _mm_set_epi64x(\__int64 i1,\__int64 i0)|
|[_mm_set_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_epi8)|SSE2|intrin.h|__m128i _mm_set_epi8(char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char)|
|[_mm_set_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_pd)|SSE2|intrin.h|__m128d _mm_set_pd(double,double)|
|[_mm_set_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_ps)|SSE|intrin.h|__m128 _mm_set_ps(float,float,float,float)|
|[_mm_set_ps1](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_ps1)|SSE|intrin.h|__m128 _mm_set_ps1(float)|
|[_mm_set_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_sd)|SSE2|intrin.h|__m128d _mm_set_sd(double)|
|[_mm_set_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_ss)|SSE|intrin.h|__m128 _mm_set_ss(float)|
|[_mm_set1_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_epi16)|SSE2|intrin.h|__m128i _mm_set1_epi16(short)|
|[_mm_set1_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_epi32)|SSE2|intrin.h|__m128i _mm_set1_epi32(int)|
|[_mm_set1_epi64x](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_epi64x)|SSE2|intrin.h|__m128i _mm_set1_epi64x(\__int64 i)|
|[_mm_set1_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_epi8)|SSE2|intrin.h|__m128i _mm_set1_epi8(char)|
|[_mm_set1_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_pd)|SSE2|intrin.h|__m128d _mm_set1_pd(double)|
|[_mm_setcsr](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setcsr)|SSE|intrin.h|void _mm_setcsr(unsigned int)|
|_mm_setl_epi64|SSE2|intrin.h|_ _m128i _mm_setl_epi64 (\__m128i)|
|[_mm_setr_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_epi16)|SSE2|intrin.h|__m128i _mm_setr_epi16(short,short,short,short,short,short,short,short)|
|[_mm_setr_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_epi32)|SSE2|intrin.h|__m128i _mm_setr_epi32(int,int,int,int)|
|[_mm_setr_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_epi8)|SSE2|intrin.h|__m128i _mm_setr_epi8(char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char)|
|[_mm_setr_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_pd)|SSE2|intrin.h|__m128d _mm_setr_pd(double,double)|
|[_mm_setr_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_ps)|SSE|intrin.h|__m128 _mm_setr_ps(float,float,float,float)|
|[_mm_setzero_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setzero_pd)|SSE2|intrin.h|__m128d _mm_setzero_pd(void)|
|[_mm_setzero_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setzero_ps)|SSE|intrin.h|__m128 _mm_setzero_ps(void)|
|[_mm_setzero_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setzero_si128)|SSE2|intrin.h|__m128i _mm_setzero_si128(void)|
|[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)|SSE|intrin.h|void _mm_sfence(void)|
|_mm_sha_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_sha_epi16 (\__m128i、\__m128i)|
|_mm_sha_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_sha_epi32 (\__m128i、\__m128i)|
|_mm_sha_epi64|XOP [1]|ammintrin.h|_ _m128i _mm_sha_epi64 (\__m128i、\__m128i)|
|_mm_sha_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_sha_epi8 (\__m128i、\__m128i)|
|_mm_shl_epi16|XOP [1]|ammintrin.h|_ _m128i _mm_shl_epi16 (\__m128i、\__m128i)|
|_mm_shl_epi32|XOP [1]|ammintrin.h|_ _m128i _mm_shl_epi32 (\__m128i、\__m128i)|
|_mm_shl_epi64|XOP [1]|ammintrin.h|_ _m128i _mm_shl_epi64 (\__m128i、\__m128i)|
|_mm_shl_epi8|XOP [1]|ammintrin.h|_ _m128i _mm_shl_epi8 (\__m128i、\__m128i)|
|[_mm_shuffle_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shuffle_epi32)|SSE2|intrin.h|_ _m128i _mm_shuffle_epi32 (\__m128i、int)|
|[_mm_shuffle_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shuffle_epi8)|SSSE3|intrin.h|_ _m128i _mm_shuffle_epi8 (\__m128i、\__m128i)|
|[_mm_shuffle_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shuffle_pd)|SSE2|intrin.h|_ _m128d _mm_shuffle_pd (\__m128d、\__m128d、int)|
|[_mm_shuffle_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shuffle_ps)|SSE|intrin.h|_ _m128 _mm_shuffle_ps (\__m128、\__m128、符号なし int)|
|[_mm_shufflehi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shufflehi_epi16)|SSE2|intrin.h|_ _m128i _mm_shufflehi_epi16 (\__m128i、int)|
|[_mm_shufflelo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shufflelo_epi16)|SSE2|intrin.h|_ _m128i _mm_shufflelo_epi16 (\__m128i、int)|
|[_mm_sign_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sign_epi16)|SSSE3|intrin.h|_ _m128i _mm_sign_epi16 (\__m128i、\__m128i)|
|[_mm_sign_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sign_epi32)|SSSE3|intrin.h|_ _m128i _mm_sign_epi32 (\__m128i、\__m128i)|
|[_mm_sign_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sign_epi8)|SSSE3|intrin.h|_ _m128i _mm_sign_epi8 (\__m128i、\__m128i)|
|[_mm_sll_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sll_epi16)|SSE2|intrin.h|_ _m128i _mm_sll_epi16 (\__m128i、\__m128i)|
|[_mm_sll_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sll_epi32)|SSE2|intrin.h|_ _m128i _mm_sll_epi32 (\__m128i、\__m128i)|
|[_mm_sll_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sll_epi64)|SSE2|intrin.h|_ _m128i _mm_sll_epi64 (\__m128i、\__m128i)|
|[_mm_slli_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_epi16)|SSE2|intrin.h|_ _m128i _mm_slli_epi16 (\__m128i、int)|
|[_mm_slli_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_epi32)|SSE2|intrin.h|_ _m128i _mm_slli_epi32 (\__m128i、int)|
|[_mm_slli_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_epi64)|SSE2|intrin.h|_ _m128i _mm_slli_epi64 (\__m128i、int)|
|[_mm_slli_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_si128)|SSE2|intrin.h|_ _m128i _mm_slli_si128 (\__m128i、int)|
|[_mm_sllv_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sllv_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_sllv_epi32 (\__m128i、\__m128i)|
|[_mm_sllv_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sllv_epi64)|AVX2 [2]|immintrin.h|_ _m128i _mm_sllv_epi64 (\__m128i、\__m128i)|
|[_mm_sqrt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sqrt_pd)|SSE2|intrin.h|__m128d _mm_sqrt_pd(\__m128d)|
|[_mm_sqrt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sqrt_ps)|SSE|intrin.h|_ _m128 _mm_sqrt_ps (\__m128)|
|[_mm_sqrt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sqrt_sd)|SSE2|intrin.h|_ _m128d _mm_sqrt_sd (\__m128d、\__m128d)|
|[_mm_sqrt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sqrt_ss)|SSE|intrin.h|_ _m128 _mm_sqrt_ss (\__m128)|
|[_mm_sra_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sra_epi16)|SSE2|intrin.h|_ _m128i _mm_sra_epi16 (\__m128i、\__m128i)|
|[_mm_sra_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sra_epi32)|SSE2|intrin.h|_ _m128i _mm_sra_epi32 (\__m128i、\__m128i)|
|[_mm_srai_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srai_epi16)|SSE2|intrin.h|_ _m128i _mm_srai_epi16 (\__m128i、int)|
|[_mm_srai_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srai_epi32)|SSE2|intrin.h|_ _m128i _mm_srai_epi32 (\__m128i、int)|
|[_mm_srav_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srav_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_srav_epi32 (\__m128i、\__m128i)|
|[_mm_srl_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srl_epi16)|SSE2|intrin.h|_ _m128i _mm_srl_epi16 (\__m128i、\__m128i)|
|[_mm_srl_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srl_epi32)|SSE2|intrin.h|_ _m128i _mm_srl_epi32 (\__m128i、\__m128i)|
|[_mm_srl_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srl_epi64)|SSE2|intrin.h|_ _m128i _mm_srl_epi64 (\__m128i、\__m128i)|
|[_mm_srli_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_epi16)|SSE2|intrin.h|_ _m128i _mm_srli_epi16 (\__m128i、int)|
|[_mm_srli_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_epi32)|SSE2|intrin.h|_ _m128i _mm_srli_epi32 (\__m128i、int)|
|[_mm_srli_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_epi64)|SSE2|intrin.h|_ _m128i _mm_srli_epi64 (\__m128i、int)|
|[_mm_srli_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_si128)|SSE2|intrin.h|_ _m128i _mm_srli_si128 (\__m128i、int)|
|[_mm_srlv_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srlv_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm_srlv_epi32 (\__m128i、\__m128i)|
|[_mm_srlv_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srlv_epi64)|AVX2 [2]|immintrin.h|_ _m128i _mm_srlv_epi64 (\__m128i、\__m128i)|
|[_mm_store_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_pd)|SSE2|intrin.h|void _mm_store_pd (double\*、\__m128d)|
|[_mm_store_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ps)|SSE|intrin.h|void _mm_store_ps (float\*、\__m128)|
|[_mm_store_ps1](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ps1)|SSE|intrin.h|void _mm_store_ps1 (float\*、\__m128)|
|[_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)|SSE2|intrin.h|void _mm_store_sd (double\*、\__m128d)|
|[_mm_store_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_si128)|SSE2|intrin.h|void _mm_store_si128 (\__m128i\*、\__m128i)|
|[_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)|SSE|intrin.h|void _mm_store_ss (float\*、\__m128)|
|[_mm_store1_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store1_pd)|SSE2|intrin.h|void _mm_store1_pd (double\*、\__m128d)|
|[_mm_storeh_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeh_pd)|SSE2|intrin.h|void _mm_storeh_pd (double\*、\__m128d)|
|[_mm_storeh_pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeh_pi)|SSE|intrin.h|void _mm_storeh_pi (\__m64\*、\__m128)|
|[_mm_storel_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storel_epi64)|SSE2|intrin.h|void _mm_storel_epi64 (\__m128i\*、\__m128i)|
|[_mm_storel_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storel_pd)|SSE2|intrin.h|void _mm_storel_pd (double\*、\__m128d)|
|[_mm_storel_pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storel_pi)|SSE|intrin.h|void _mm_storel_pi (\__m64\*、\__m128)|
|[_mm_storer_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storer_pd)|SSE2|intrin.h|void _mm_storer_pd (double\*、\__m128d)|
|[_mm_storer_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storer_ps)|SSE|intrin.h|void _mm_storer_ps (float\*、\__m128)|
|[_mm_storeu_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeu_pd)|SSE2|intrin.h|void _mm_storeu_pd (double\*、\__m128d)|
|[_mm_storeu_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeu_ps)|SSE|intrin.h|void _mm_storeu_ps (float\*、\__m128)|
|[_mm_storeu_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeu_si128)|SSE2|intrin.h|void _mm_storeu_si128 (\__m128i\*、\__m128i)|
|[_mm_stream_load_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_load_si128)|SSE41|intrin.h|_ _m128i _mm_stream_load_si128 (\__m128i\* )|
|[_mm_stream_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_pd)|SSE2|intrin.h|void _mm_stream_pd (double\*、\__m128d)|
|[_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)|SSE|intrin.h|void _mm_stream_ps (float\*、\__m128)|
|[_mm_stream_sd](../intrinsics/mm-stream-sd.md)|SSE4a|intrin.h|void _mm_stream_sd (double\*、\__m128d)|
|[_mm_stream_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_si128)|SSE2|intrin.h|void _mm_stream_si128 (\__m128i\*、\__m128i)|
|[_mm_stream_si32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_si32)|SSE2|intrin.h|void _mm_stream_si32 (int\*int)|
|[_mm_stream_si64x](../intrinsics/mm-stream-si64x.md)|SSE2|intrin.h|void _mm_stream_si64x (\__ _int64 \*、\__ _int64)|
|[_mm_stream_ss](../intrinsics/mm-stream-ss.md)|SSE4a|intrin.h|_mm_stream_ss を無効にする (float\*、\__m128)|
|[_mm_sub_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_epi16)|SSE2|intrin.h|_ _m128i _mm_sub_epi16 (\__m128i、\__m128i)|
|[_mm_sub_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_epi32)|SSE2|intrin.h|_ _m128i _mm_sub_epi32 (\__m128i、\__m128i)|
|[_mm_sub_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_epi64)|SSE2|intrin.h|_ _m128i _mm_sub_epi64 (\__m128i、\__m128i)|
|[_mm_sub_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_epi8)|SSE2|intrin.h|_ _m128i _mm_sub_epi8 (\__m128i、\__m128i)|
|[_mm_sub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_pd)|SSE2|intrin.h|__m128d _mm_sub_pd(\__m128d,\__m128d)|
|[_mm_sub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_ps)|SSE|intrin.h|_ _m128 _mm_sub_ps (\__m128、\__m128)|
|[_mm_sub_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_sd)|SSE2|intrin.h|__m128d _mm_sub_sd(\__m128d,\__m128d)|
|[_mm_sub_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_ss)|SSE|intrin.h|_ _m128 _mm_sub_ss (\__m128、\__m128)|
|[_mm_subs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_epi16)|SSE2|intrin.h|_ _m128i _mm_subs_epi16 (\__m128i、\__m128i)|
|[_mm_subs_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_epi8)|SSE2|intrin.h|_ _m128i _mm_subs_epi8 (\__m128i、\__m128i)|
|[_mm_subs_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_epu16)|SSE2|intrin.h|_ _m128i _mm_subs_epu16 (\__m128i、\__m128i)|
|[_mm_subs_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_epu8)|SSE2|intrin.h|_ _m128i _mm_subs_epu8 (\__m128i、\__m128i)|
|[_mm_testc_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testc_pd)|AVX [2]|immintrin.h|int _mm_testc_pd(\__m128d,\__m128d)|
|[_mm_testc_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testc_ps)|AVX [2]|immintrin.h|int _mm_testc_ps (\__m128、\__m128)|
|[_mm_testc_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testc_si128)|SSE41|intrin.h|int _mm_testc_si128 (\__m128i、\__m128i)|
|[_mm_testnzc_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testnzc_pd)|AVX [2]|immintrin.h|int _mm_testnzc_pd(\__m128d,\__m128d)|
|[_mm_testnzc_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testnzc_ps)|AVX [2]|immintrin.h|int _mm_testnzc_ps (\__m128、\__m128)|
|[_mm_testnzc_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testnzc_si128)|SSE41|intrin.h|int _mm_testnzc_si128 (\__m128i、\__m128i)|
|[_mm_testz_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testz_pd)|AVX [2]|immintrin.h|int _mm_testz_pd(\__m128d,\__m128d)|
|[_mm_testz_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testz_ps)|AVX [2]|immintrin.h|int _mm_testz_ps (\__m128、\__m128)|
|[_mm_testz_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testz_si128)|SSE41|intrin.h|int _mm_testz_si128 (\__m128i、\__m128i)|
|[_mm_ucomieq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomieq_sd)|SSE2|intrin.h|int _mm_ucomieq_sd(\__m128d,\__m128d)|
|[_mm_ucomieq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomieq_ss)|SSE|intrin.h|int _mm_ucomieq_ss (\__m128、\__m128)|
|[_mm_ucomige_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomige_sd)|SSE2|intrin.h|int _mm_ucomige_sd(\__m128d,\__m128d)|
|[_mm_ucomige_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomige_ss)|SSE|intrin.h|int _mm_ucomige_ss (\__m128、\__m128)|
|[_mm_ucomigt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomigt_sd)|SSE2|intrin.h|int _mm_ucomigt_sd(\__m128d,\__m128d)|
|[_mm_ucomigt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomigt_ss)|SSE|intrin.h|int _mm_ucomigt_ss (\__m128、\__m128)|
|[_mm_ucomile_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomile_sd)|SSE2|intrin.h|int _mm_ucomile_sd(\__m128d,\__m128d)|
|[_mm_ucomile_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomile_ss)|SSE|intrin.h|int _mm_ucomile_ss (\__m128、\__m128)|
|[_mm_ucomilt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomilt_sd)|SSE2|intrin.h|int _mm_ucomilt_sd(\__m128d,\__m128d)|
|[_mm_ucomilt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomilt_ss)|SSE|intrin.h|int _mm_ucomilt_ss (\__m128、\__m128)|
|[_mm_ucomineq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomineq_sd)|SSE2|intrin.h|int _mm_ucomineq_sd(\__m128d,\__m128d)|
|[_mm_ucomineq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomineq_ss)|SSE|intrin.h|int _mm_ucomineq_ss (\__m128、\__m128)|
|[_mm_unpackhi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_epi16)|SSE2|intrin.h|_ _m128i _mm_unpackhi_epi16 (\__m128i、\__m128i)|
|[_mm_unpackhi_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_epi32)|SSE2|intrin.h|_ _m128i _mm_unpackhi_epi32 (\__m128i、\__m128i)|
|[_mm_unpackhi_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_epi64)|SSE2|intrin.h|_ _m128i _mm_unpackhi_epi64 (\__m128i、\__m128i)|
|[_mm_unpackhi_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_epi8)|SSE2|intrin.h|_ _m128i _mm_unpackhi_epi8 (\__m128i、\__m128i)|
|[_mm_unpackhi_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_pd)|SSE2|intrin.h|__m128d _mm_unpackhi_pd(\__m128d,\__m128d)|
|[_mm_unpackhi_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_ps)|SSE|intrin.h|_ _m128 _mm_unpackhi_ps (\__m128、\__m128)|
|[_mm_unpacklo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_epi16)|SSE2|intrin.h|_ _m128i _mm_unpacklo_epi16 (\__m128i、\__m128i)|
|[_mm_unpacklo_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_epi32)|SSE2|intrin.h|_ _m128i _mm_unpacklo_epi32 (\__m128i、\__m128i)|
|[_mm_unpacklo_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_epi64)|SSE2|intrin.h|_ _m128i _mm_unpacklo_epi64 (\__m128i、\__m128i)|
|[_mm_unpacklo_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_epi8)|SSE2|intrin.h|_ _m128i _mm_unpacklo_epi8 (\__m128i、\__m128i)|
|[_mm_unpacklo_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_pd)|SSE2|intrin.h|__m128d _mm_unpacklo_pd(\__m128d,\__m128d)|
|[_mm_unpacklo_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_ps)|SSE|intrin.h|_ _m128 _mm_unpacklo_ps (\__m128、\__m128)|
|[_mm_xor_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_xor_pd)|SSE2|intrin.h|__m128d _mm_xor_pd(\__m128d,\__m128d)|
|[_mm_xor_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_xor_ps)|SSE|intrin.h|__m128 _mm_xor_ps(\__m128,\__m128)|
|[_mm_xor_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_xor_si128)|SSE2|intrin.h|__m128i _mm_xor_si128(\__m128i,\__m128i)|
|[_mm256_abs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_abs_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_abs_epi16 (\__m256i)|
|[_mm256_abs_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_abs_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_abs_epi32 (\__m256i)|
|[_mm256_abs_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_abs_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_abs_epi8 (\__m256i)|
|[_mm256_add_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_add_epi16 (\__m256i、\__m256i)|
|[_mm256_add_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_add_epi32 (\__m256i、\__m256i)|
|[_mm256_add_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_add_epi64 (\__m256i、\__m256i)|
|[_mm256_add_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_add_epi8 (\__m256i、\__m256i)|
|[_mm256_add_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_pd)|AVX [2]|immintrin.h|__m256d _mm256_add_pd(\__m256d,\__m256d)|
|[_mm256_add_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_ps)|AVX [2]|immintrin.h|__m256 _mm256_add_ps(\__m256,\__m256)|
|[_mm256_adds_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_adds_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_adds_epi16 (\__m256i、\__m256i)|
|[_mm256_adds_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_adds_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_adds_epi8 (\__m256i、\__m256i)|
|[_mm256_adds_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_adds_epu16)|AVX2 [2]|immintrin.h|__m256i _mm256_adds_epu16 (\__m256i、\__m256i)|
|[_mm256_adds_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_adds_epu8)|AVX2 [2]|immintrin.h|__m256i _mm256_adds_epu8 (\__m256i、\__m256i)|
|[_mm256_addsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_addsub_pd)|AVX [2]|immintrin.h|__m256d _mm256_addsub_pd(\__m256d,\__m256d)|
|[_mm256_addsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_addsub_ps)|AVX [2]|immintrin.h|__m256 _mm256_addsub_ps (\__m256、\__m256)|
|[_mm256_alignr_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_alignr_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_alignr_epi8 (\__m256i、\__m256i、const int)|
|[_mm256_and_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_and_pd)|AVX [2]|immintrin.h|__m256d _mm256_and_pd(\__m256d,\__m256d)|
|[_mm256_and_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_and_ps)|AVX [2]|immintrin.h|__m256 _mm256_and_ps(\__m256,\__m256)|
|[_mm256_and_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_and_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_and_si256 (\__m256i、\__m256i)|
|[_mm256_andnot_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_andnot_pd)|AVX [2]|immintrin.h|__m256d _mm256_andnot_pd (\__m256d、\__m256d)|
|[_mm256_andnot_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_andnot_ps)|AVX [2]|immintrin.h|__m256 _mm256_andnot_ps (\__m256、\__m256)|
|[_mm256_andnot_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_andnot_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_andnot_si256 (\__m256i、\__m256i)|
|[_mm256_avg_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_avg_epu16)|AVX2 [2]|immintrin.h|__m256i _mm256_avg_epu16 (\__m256i、\__m256i)|
|[_mm256_avg_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_avg_epu8)|AVX2 [2]|immintrin.h|__m256i _mm256_avg_epu8 (\__m256i、\__m256i)|
|[_mm256_blend_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blend_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_blend_epi16 (\__m256i、\__m256i、const int)|
|[_mm256_blend_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blend_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_blend_epi32 (\__m256i、\__m256i、const int)|
|[_mm256_blend_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blend_pd)|AVX [2]|immintrin.h|__m256d _mm256_blend_pd(\__m256d,\__m256d,const int)|
|[_mm256_blend_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blend_ps)|AVX [2]|immintrin.h|__m256 _mm256_blend_ps(\__m256,\__m256,const int)|
|[_mm256_blendv_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blendv_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_blendv_epi8 (\__m256i、\__m256i、\__m256i)|
|[_mm256_blendv_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blendv_pd)|AVX [2]|immintrin.h|__m256d _mm256_blendv_pd(\__m256d,\__m256d,\__m256d)|
|[_mm256_blendv_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blendv_ps)|AVX [2]|immintrin.h|__m256 _mm256_blendv_ps (\__m256、\__m256、\__m256)|
|[_mm256_broadcast_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcast_pd)|AVX [2]|immintrin.h|__m256d _mm256_broadcast_pd (\__m128d const \*)|
|[_mm256_broadcast_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcast_ps)|AVX [2]|immintrin.h|__m256 _mm256_broadcast_ps (\__m128 const \*)|
|[_mm256_broadcast_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcast_sd)|AVX [2]|immintrin.h|__m256d _mm256_broadcast_sd (二重 const \*)|
|[_mm256_broadcast_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcast_ss)|AVX [2]|immintrin.h|__m256 _mm256_broadcast_ss (float、const \*)|
|[_mm256_broadcastb_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastb_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_broadcastb_epi8 (\__m128i)|
|[_mm256_broadcastd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastd_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_broadcastd_epi32 (\__m128i)|
|[_mm256_broadcastq_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastq_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_broadcastq_epi64 (\__m128i)|
|[_mm256_broadcastsd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastsd_pd)|AVX2 [2]|immintrin.h|__m256d _mm256_broadcastsd_pd(\__m128d)|
|[_mm256_broadcastsi128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastsi128_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_broadcastsi128_si256 (\__m128i)|
|[_mm256_broadcastss_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastss_ps)|AVX2 [2]|immintrin.h|__m256 _mm256_broadcastss_ps (\__m128)|
|[_mm256_broadcastw_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastw_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_broadcastw_epi16 (\__m128i)|
|[_mm256_castpd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castpd_ps)|AVX [2]|immintrin.h|__m256 _mm256_castpd_ps(\__m256d)|
|[_mm256_castpd_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castpd_si256)|AVX [2]|immintrin.h|__m256i _mm256_castpd_si256(\__m256d)|
|[_mm256_castpd128_pd256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castpd128_pd256)|AVX [2]|immintrin.h|__m256d _mm256_castpd128_pd256(\__m128d)|
|[_mm256_castpd256_pd128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castpd256_pd128)|AVX [2]|immintrin.h|__m128d _mm256_castpd256_pd128(\__m256d)|
|[_mm256_castps_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castps_pd)|AVX [2]|immintrin.h|__m256d _mm256_castps_pd(\__m256)|
|[_mm256_castps_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castps_si256)|AVX [2]|immintrin.h|__m256i _mm256_castps_si256(\__m256)|
|[_mm256_castps128_ps256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castps128_ps256)|AVX [2]|immintrin.h|__m256 _mm256_castps128_ps256(\__m128)|
|[_mm256_castps256_ps128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castps256_ps128)|AVX [2]|immintrin.h|_ _m128 _mm256_castps256_ps128 (\__m256)|
|[_mm256_castsi128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castsi128_si256)|AVX [2]|immintrin.h|__m256i _mm256_castsi128_si256 (\__m128i)|
|[_mm256_castsi256_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castsi256_pd)|AVX [2]|immintrin.h|__m256d _mm256_castsi256_pd(\__m256i)|
|[_mm256_castsi256_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castsi256_ps)|AVX [2]|immintrin.h|__m256 _mm256_castsi256_ps(\__m256i)|
|[_mm256_castsi256_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castsi256_si128)|AVX [2]|immintrin.h|_ _m128i _mm256_castsi256_si128 (\__m256i)|
|_mm256_cmov_si256|XOP [1]|ammintrin.h|__m256i _mm256_cmov_si256 (\__m256i、\__m256i、\__m256i)|
|[_mm256_cmp_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmp_pd)|AVX [2]|immintrin.h|__m256d  _mm256_cmp_pd(\__m256d,\__m256d,const int)|
|[_mm256_cmp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmp_ps)|AVX [2]|immintrin.h|__m256 _mm256_cmp_ps (\__m256、\__m256、const int)|
|[_mm256_cmpeq_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpeq_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_cmpeq_epi16 (\__m256i、\__m256i)|
|[_mm256_cmpeq_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpeq_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_cmpeq_epi32 (\__m256i、\__m256i)|
|[_mm256_cmpeq_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpeq_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_cmpeq_epi64 (\__m256i、\__m256i)|
|[_mm256_cmpeq_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpeq_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_cmpeq_epi8 (\__m256i、\__m256i)|
|[_mm256_cmpgt_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpgt_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_cmpgt_epi16 (\__m256i、\__m256i)|
|[_mm256_cmpgt_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpgt_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_cmpgt_epi32 (\__m256i、\__m256i)|
|[_mm256_cmpgt_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpgt_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_cmpgt_epi64 (\__m256i、\__m256i)|
|[_mm256_cmpgt_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpgt_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_cmpgt_epi8 (\__m256i、\__m256i)|
|[_mm256_cvtepi16_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi16_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepi16_epi32 (\__m128i)|
|[_mm256_cvtepi16_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi16_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepi16_epi64 (\__m128i)|
|[_mm256_cvtepi32_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi32_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepi32_epi64 (\__m128i)|
|[_mm256_cvtepi32_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi32_pd)|AVX [2]|immintrin.h|__m256d _mm256_cvtepi32_pd(\__m128i)|
|[_mm256_cvtepi32_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi32_ps)|AVX [2]|immintrin.h|__m256 _mm256_cvtepi32_ps(\__m256i)|
|[_mm256_cvtepi8_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi8_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepi8_epi16 (\__m128i)|
|[_mm256_cvtepi8_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi8_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepi8_epi32 (\__m128i)|
|[_mm256_cvtepi8_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi8_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepi8_epi64 (\__m128i)|
|[_mm256_cvtepu16_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu16_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepu16_epi32 (\__m128i)|
|[_mm256_cvtepu16_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu16_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepu16_epi64 (\__m128i)|
|[_mm256_cvtepu32_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu32_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepu32_epi64 (\__m128i)|
|[_mm256_cvtepu8_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu8_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepu8_epi16 (\__m128i)|
|[_mm256_cvtepu8_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu8_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepu8_epi32 (\__m128i)|
|[_mm256_cvtepu8_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu8_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_cvtepu8_epi64 (\__m128i)|
|[_mm256_cvtpd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtpd_epi32)|AVX [2]|immintrin.h|__m128i _mm256_cvtpd_epi32(\__m256d)|
|[_mm256_cvtpd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtpd_ps)|AVX [2]|immintrin.h|__m128 _mm256_cvtpd_ps(\__m256d)|
|[_mm256_cvtph_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtph_ps)|F16C [2]|immintrin.h|__m256 _mm256_cvtph_ps(\__m128i)|
|[_mm256_cvtps_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtps_epi32)|AVX [2]|immintrin.h|__m256i _mm256_cvtps_epi32(\__m256)|
|[_mm256_cvtps_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtps_pd)|AVX [2]|immintrin.h|__m256d _mm256_cvtps_pd(\__m128)|
|[_mm256_cvtps_ph](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtps_ph)|F16C [2]|immintrin.h|_ _m128i _mm256_cvtps_ph (\__m256、const int)|
|[_mm256_cvttpd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvttpd_epi32)|AVX [2]|immintrin.h|_ _m128i _mm256_cvttpd_epi32 (\__m256d)|
|[_mm256_cvttps_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvttps_epi32)|AVX [2]|immintrin.h|__m256i _mm256_cvttps_epi32 (\__m256)|
|[_mm256_div_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_div_pd)|AVX [2]|immintrin.h|__m256d _mm256_div_pd(\__m256d,\__m256d)|
|[_mm256_div_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_div_ps)|AVX [2]|immintrin.h|__m256 _mm256_div_ps(\__m256,\__m256)|
|[_mm256_dp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_dp_ps)|AVX [2]|immintrin.h|__m256 _mm256_dp_ps (\__m256、\__m256、const int)|
|[_mm256_extractf128_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_extractf128_pd)|AVX [2]|immintrin.h|_ _m128d _mm256_extractf128_pd (\__m256d、const int)|
|[_mm256_extractf128_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_extractf128_ps)|AVX [2]|immintrin.h|_ _m128 _mm256_extractf128_ps (\__m256、const int)|
|[_mm256_extractf128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_extractf128_si256)|AVX [2]|immintrin.h|_ _m128i _mm256_extractf128_si256 (\__m256i、const int)|
|[_mm256_extracti128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_extracti128_si256)|AVX2 [2]|immintrin.h|_ _m128i _mm256_extracti128_si256 (\__m256i a, int offset)|
|[_mm256_fmadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmadd_pd)|FMA [2]|immintrin.h|__m256d _mm256_fmadd_pd (\__m256d、\__m256d b、\__m256d c).|
|[_mm256_fmadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmadd_ps)|FMA [2]|immintrin.h|__m256 _mm256_fmadd_ps (\__m256、\__m256 b、\__m256 c).|
|[_mm256_fmaddsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmaddsub_pd)|FMA [2]|immintrin.h|__m256d _mm256_fmaddsub_pd (\__m256d、\__m256d b、\__m256d c).|
|[_mm256_fmaddsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmaddsub_ps)|FMA [2]|immintrin.h|__m256 _mm256_fmaddsub_ps (\__m256、\__m256 b、\__m256 c).|
|[_mm256_fmsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmsub_pd)|FMA [2]|immintrin.h|__m256d _mm256_fmsub_pd (\__m256d、\__m256d b、\__m256d c).|
|[_mm256_fmsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmsub_ps)|FMA [2]|immintrin.h|__m256 _mm256_fmsub_ps (\__m256、\__m256 b、\__m256 c).|
|[_mm256_fmsubadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmsubadd_pd)|FMA [2]|immintrin.h|__m256d _mm256_fmsubadd_pd (\__m256d、\__m256d b、\__m256d c).|
|[_mm256_fmsubadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmsubadd_ps)|FMA [2]|immintrin.h|__m256 _mm256_fmsubadd_ps (\__m256、\__m256 b、\__m256 c).|
|[_mm256_fnmadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fnmadd_pd)|FMA [2]|immintrin.h|__m256d _mm256_fnmadd_pd (\__m256d、\__m256d b、\__m256d c).|
|[_mm256_fnmadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fnmadd_ps)|FMA [2]|immintrin.h|__m256 _mm256_fnmadd_ps (\__m256、\__m256 b、\__m256 c).|
|[_mm256_fnmsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fnmsub_pd)|FMA [2]|immintrin.h|__m256d _mm256_fnmsub_pd (\__m256d、\__m256d b、\__m256d c).|
|[_mm256_fnmsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fnmsub_ps)|FMA [2]|immintrin.h|__m256 _mm256_fnmsub_ps (\__m256、\__m256 b、\__m256 c).|
|_mm256_frcz_pd|XOP [1]|ammintrin.h|__m256d _mm256_frcz_pd(\__m256d)|
|_mm256_frcz_ps|XOP [1]|ammintrin.h|__m256 _mm256_frcz_ps (\__m256)|
|[_mm256_hadd_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadd_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_hadd_epi16 (\__m256i、\__m256i)|
|[_mm256_hadd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadd_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_hadd_epi32 (\__m256i、\__m256i)|
|[_mm256_hadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadd_pd)|AVX [2]|immintrin.h|__m256d _mm256_hadd_pd(\__m256d,\__m256d)|
|[_mm256_hadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadd_ps)|AVX [2]|immintrin.h|__m256 _mm256_hadd_ps (\__m256、\__m256)|
|[_mm256_hadds_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadds_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_hadds_epi16 (\__m256i、\__m256i)|
|[_mm256_hsub_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsub_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_hsub_epi16 (\__m256i、\__m256i)|
|[_mm256_hsub_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsub_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_hsub_epi32 (\__m256i、\__m256i)|
|[_mm256_hsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsub_pd)|AVX [2]|immintrin.h|__m256d _mm256_hsub_pd(\__m256d,\__m256d)|
|[_mm256_hsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsub_ps)|AVX [2]|immintrin.h|__m256 _mm256_hsub_ps (\__m256、\__m256)|
|[_mm256_hsubs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsubs_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_hsubs_epi16 (\__m256i、\__m256i)|
|[_mm256_i32gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i32gather_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_i32gather_epi32 (const int\*ベース、\__m256i インデックス、const int スケール)|
|[_mm256_i32gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i32gather_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_i32gather_epi64 (\__ _int64 const\*ベース\__m128i キーワード、const int スケール)|
|[_mm256_i32gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i32gather_pd)|AVX2 [2]|immintrin.h|__m256d _mm256_i32gather_pd (二重 const\*ベース、\__m128i キーワード、const int スケール)|
|[_mm256_i32gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i32gather_ps)|AVX2 [2]|immintrin.h|__m256 _mm256_i32gather_ps (float、const\*ベース、\__m256i インデックス、const int スケール)|
|[_mm256_i64gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i64gather_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_i64gather_epi32 (const int\*ベース、\__m256i インデックス、const int スケール)|
|[_mm256_i64gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i64gather_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_i64gather_epi64 (\__ _int64 const\*ベース\__m256i インデックス、const int スケール)|
|[_mm256_i64gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i64gather_pd)|AVX2 [2]|immintrin.h|__m256d _mm256_i64gather_pd (二重 const\*ベース、\__m256i インデックス、const int スケール)|
|[_mm256_i64gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i64gather_ps)|AVX2 [2]|immintrin.h|_ _m128 _mm256_i64gather_ps (float、const\*ベース、\__m256i インデックス、const int スケール)|
|[_mm256_insertf128_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_insertf128_pd)|AVX [2]|immintrin.h|__m256d _mm256_insertf128_pd(\__m256d,\__m128d,int )|
|[_mm256_insertf128_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_insertf128_ps)|AVX [2]|immintrin.h|__m256 _mm256_insertf128_ps (\__m256、\__m128、int)|
|[_mm256_insertf128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_insertf128_si256)|AVX [2]|immintrin.h|__m256i _mm256_insertf128_si256 (\__m256i、\__m128i、int)|
|[_mm256_inserti128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_inserti128_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_inserti128_si256 (\__m256i、\__m128i、int)|
|[_mm256_lddqu_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_lddqu_si256)|AVX [2]|immintrin.h|__m256i _mm256_lddqu_si256 (\__m256i \*)|
|[_mm256_load_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_load_pd)|AVX [2]|immintrin.h|__m256d _mm256_load_pd (二重 const \*)|
|[_mm256_load_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_load_ps)|AVX [2]|immintrin.h|__m256 _mm256_load_ps (float、const \*)|
|[_mm256_load_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_load_si256)|AVX [2]|immintrin.h|__m256i _mm256_load_si256 (\__m256i \*)|
|[_mm256_loadu_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_loadu_pd)|AVX [2]|immintrin.h|__m256d _mm256_loadu_pd (二重 const \*)|
|[_mm256_loadu_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_loadu_ps)|AVX [2]|immintrin.h|__m256 _mm256_loadu_ps (float、const \*)|
|[_mm256_loadu_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_loadu_si256)|AVX [2]|immintrin.h|__m256i _mm256_loadu_si256 (\__m256i \*)|
|_mm256_macc_pd|FMA4 [1]|ammintrin.h|__m256d _mm_macc_pd(\__m256d,\__m256d,\__m256d)|
|_mm256_macc_ps|FMA4 [1]|ammintrin.h|__m256 _mm_macc_ps (\__m256、\__m256、\__m256)|
|[_mm256_madd_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_madd_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_madd_epi16 (\__m256i、\__m256i)|
|_mm256_maddsub_pd|FMA4 [1]|ammintrin.h|__m256d _mm_maddsub_pd (\__m256d、\__m256d、\__m256d)|
|_mm256_maddsub_ps|FMA4 [1]|ammintrin.h|__m256 _mm_maddsub_ps (\__m256、\__m256、\__m256)|
|[_mm256_maddubs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maddubs_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_maddubs_epi16 (\__m256i、\__m256i)|
|[_mm256_mask_i32gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i32gather_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_mask_i32gather_epi32 (\__m256i src、const int\*ベース\__m256i インデックス、\__m256i マスク、const int スケール)|
|[_mm256_mask_i32gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i32gather_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_mask_i32gather_epi64 (\__m256i src、\__ _int64 const \\* 基本、\__m128i キーワード、\__m256i マスク、const int スケール)|
|[_mm256_mask_i32gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i32gather_pd)|AVX2 [2]|immintrin.h|__m256d _mm256_mask_i32gather_pd (\__m256d src、二重 const\*ベース\__m128i キーワード、\__m256d マスク、const int スケール)|
|[_mm256_mask_i32gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i32gather_ps)|AVX2 [2]|immintrin.h|__m256 _mm256_mask_i32gather_ps (\__m256 src、float 型の const\*ベース\__m256i インデックス、\__m256 マスク、const int スケール)|
|[_mm256_mask_i64gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i64gather_epi32)|AVX2 [2]|immintrin.h|_ _m128i _mm256_mask_i64gather_epi32 (\__m128i src、const int\*ベース\__m256i インデックス、\__m128i マスク、const int スケール)|
|[_mm256_mask_i64gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i64gather_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_mask_i64gather_epi64 (\__m256i src、\__ _int64 const\*ベース\__m256i インデックス、\__m256i マスク、const int スケール)|
|[_mm256_mask_i64gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i64gather_pd)|AVX2 [2]|immintrin.h|__m256d _mm256_mask_i64gather_pd (\__m256d src、二重 const\*ベース\__m256i インデックス、\__m256d マスク、const int スケール)|
|[_mm256_mask_i64gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i64gather_ps)|AVX2 [2]|immintrin.h|_ _m128 _mm256_mask_i64gather_ps (\__m128 src、float 型の const\*ベース\__m256i インデックス、\__m128 マスク、const int スケール)|
|[_mm256_maskload_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskload_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_maskload_epi32 (const int \*、\__m256i)|
|[_mm256_maskload_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskload_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_maskload_epi64 ( \__ _int64 const \*、\__m256i)|
|[_mm256_maskload_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskload_pd)|AVX [2]|immintrin.h|__m256d _mm256_maskload_pd (二重 const \*、\__m256i)|
|[_mm256_maskload_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskload_ps)|AVX [2]|immintrin.h|__m256 _mm256_maskload_ps (float、const \*、\__m256i)|
|[_mm256_maskstore_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskstore_epi32)|AVX2 [2]|immintrin.h|void _mm256_maskstore_epi32 (int \*、\__m256i、\__m256i)|
|[_mm256_maskstore_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskstore_epi64)|AVX2 [2]|immintrin.h|void _mm256_maskstore_epi64 (\__ _int64 \*、\__m256i、\__m256i)|
|[_mm256_maskstore_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskstore_pd)|AVX [2]|immintrin.h|void _mm256_maskstore_pd (double \*、\__m256i、\__m256d)|
|[_mm256_maskstore_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskstore_ps)|AVX [2]|immintrin.h|void _mm256_maskstore_ps (float \*、\__m256i、\__m256)|
|[_mm256_max_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_max_epi16 (\__m256i、\__m256i)|
|[_mm256_max_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_max_epi32 (\__m256i、\__m256i)|
|[_mm256_max_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_max_epi8 (\__m256i、\__m256i)|
|[_mm256_max_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epu16)|AVX2 [2]|immintrin.h|__m256i _mm256_max_epu16 (\__m256i、\__m256i)|
|[_mm256_max_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epu32)|AVX2 [2]|immintrin.h|__m256i _mm256_max_epu32 (\__m256i、\__m256i)|
|[_mm256_max_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epu8)|AVX2 [2]|immintrin.h|__m256i _mm256_max_epu8 (\__m256i、\__m256i)|
|[_mm256_max_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_pd)|AVX [2]|immintrin.h|__m256d _mm256_max_pd(\__m256d,\__m256d)|
|[_mm256_max_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_ps)|AVX [2]|immintrin.h|__m256 _mm256_max_ps (\__m256、\__m256)|
|[_mm256_min_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_min_epi16 (\__m256i、\__m256i)|
|[_mm256_min_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_min_epi32 (\__m256i、\__m256i)|
|[_mm256_min_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_min_epi8 (\__m256i、\__m256i)|
|[_mm256_min_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epu16)|AVX2 [2]|immintrin.h|__m256i _mm256_min_epu16 (\__m256i、\__m256i)|
|[_mm256_min_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epu32)|AVX2 [2]|immintrin.h|__m256i _mm256_min_epu32 (\__m256i、\__m256i)|
|[_mm256_min_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epu8)|AVX2 [2]|immintrin.h|__m256i _mm256_min_epu8 (\__m256i、\__m256i)|
|[_mm256_min_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_pd)|AVX [2]|immintrin.h|__m256d _mm256_min_pd (\__m256d、\__m256d)|
|[_mm256_min_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_ps)|AVX [2]|immintrin.h|__m256 _mm256_min_ps (\__m256、\__m256)|
|[_mm256_movedup_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movedup_pd)|AVX [2]|immintrin.h|__m256d _mm256_movedup_pd(\__m256d)|
|[_mm256_movehdup_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movehdup_ps)|AVX [2]|immintrin.h|__m256 _mm256_movehdup_ps(\__m256)|
|[_mm256_moveldup_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_moveldup_ps)|AVX [2]|immintrin.h|__m256 _mm256_moveldup_ps (\__m256)|
|[_mm256_movemask_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movemask_epi8)|AVX2 [2]|immintrin.h|int _mm256_movemask_epi8 (\__m256i)|
|[_mm256_movemask_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movemask_pd)|AVX [2]|immintrin.h|int _mm256_movemask_pd(\__m256d)|
|[_mm256_movemask_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movemask_ps)|AVX [2]|immintrin.h|int _mm256_movemask_ps(\__m256)|
|[_mm256_mpsadbw_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mpsadbw_epu8)|AVX2 [2]|immintrin.h|__m256i _mm256_mpsadbw_epu8 (\__m256i、\__m256i、const int)|
|_mm256_msub_pd|FMA4 [1]|ammintrin.h|__m256d _mm_msub_pd (\__m256d、\__m256d、\__m256d)|
|_mm256_msub_ps|FMA4 [1]|ammintrin.h|__m256 _mm_msub_ps (\__m256、\__m256、\__m256)|
|_mm256_msubadd_pd|FMA4 [1]|ammintrin.h|__m256d _mm_msubadd_pd(\__m256d,\__m256d,\__m256d)|
|_mm256_msubadd_ps|FMA4 [1]|ammintrin.h|__m256 _mm_msubadd_ps (\__m256、\__m256、\__m256)|
|[_mm256_mul_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mul_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_mul_epi32 (\__m256i、\__m256i)|
|[_mm256_mul_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mul_epu32)|AVX2 [2]|immintrin.h|__m256i _mm256_mul_epu32 (\__m256i、\__m256i)|
|[_mm256_mul_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mul_pd)|AVX [2]|immintrin.h|__m256d _mm256_mul_pd (\__m256d、\__m256d)|
|[_mm256_mul_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mul_ps)|AVX [2]|immintrin.h|__m256 _mm256_mul_ps (\__m256、\__m256)|
|[_mm256_mulhi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mulhi_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_mulhi_epi16 (\__m256i、\__m256i)|
|[_mm256_mulhi_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mulhi_epu16)|AVX2 [2]|immintrin.h|__m256i _mm256_mulhi_epu16 (\__m256i、\__m256i)|
|[_mm256_mulhrs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mulhrs_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_mulhrs_epi16 (\__m256i、\__m256i)|
|[_mm256_mullo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mullo_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_mullo_epi16 (\__m256i、\__m256i)|
|[_mm256_mullo_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mullo_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_mullo_epi32 (\__m256i、\__m256i)|
|_mm256_nmacc_pd|FMA4 [1]|ammintrin.h|__m256d _mm_nmacc_pd (\__m256d、\__m256d、\__m256d)|
|_mm256_nmacc_ps|FMA4 [1]|ammintrin.h|__m256 _mm_nmacc_ps (\__m256、\__m256、\__m256)|
|_mm256_nmsub_pd|FMA4 [1]|ammintrin.h|__m256d _mm_nmsub_pd(\__m256d,\__m256d,\__m256d)|
|_mm256_nmsub_ps|FMA4 [1]|ammintrin.h|__m256 _mm_nmsub_ps (\__m256、\__m256、\__m256)|
|[_mm256_or_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_or_pd)|AVX [2]|immintrin.h|__m256d _mm256_or_pd (\__m256d、\__m256d)|
|[_mm256_or_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_or_ps)|AVX [2]|immintrin.h|__m256 _mm256_or_ps (\__m256、\__m256)|
|[_mm256_or_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_or_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_or_si256 (\__m256i、\__m256i)|
|[_mm256_packs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_packs_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_packs_epi16 (\__m256i、\__m256i)|
|[_mm256_packs_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_packs_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_packs_epi32 (\__m256i、\__m256i)|
|[_mm256_packus_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_packus_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_packus_epi16 (\__m256i、\__m256i)|
|[_mm256_packus_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_packus_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_packus_epi32 (\__m256i、\__m256i)|
|[_mm256_permute_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute_pd)|AVX [2]|immintrin.h|__m256d _mm256_permute_pd(\__m256d,int)|
|[_mm256_permute_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute_ps)|AVX [2]|immintrin.h|__m256 _mm256_permute_ps (\__m256、int)|
|_mm256_permute2_pd|XOP [1]|ammintrin.h|__m256d _mm256_permute2_pd(\__m256d,\__m256d,\__m256i,int)|
|_mm256_permute2_ps|XOP [1]|ammintrin.h|__m256 _mm256_permute2_ps (\__m256、\__m256、\__m256i、int)|
|[_mm256_permute2f128_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute2f128_pd)|AVX [2]|immintrin.h|__m256d _mm256_permute2f128_pd(\__m256d,\__m256d,int)|
|[_mm256_permute2f128_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute2f128_ps)|AVX [2]|immintrin.h|__m256 _mm256_permute2f128_ps (\__m256、\__m256、int)|
|[_mm256_permute2f128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute2f128_si256)|AVX [2]|immintrin.h|__m256i _mm256_permute2f128_si256 (\__m256i、\__m256i、int)|
|[_mm256_permute2x128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute2x128_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_permute2x128_si256 (\__m256i、\__m256i、const int)|
|[_mm256_permute4x64_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute4x64_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_permute4x64_epi64 (\__m256i、const int)|
|[_mm256_permute4x64_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute4x64_pd)|AVX2 [2]|immintrin.h|__m256d _mm256_permute4x64_pd (\__m256d、const int)|
|[_mm256_permutevar_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permutevar_pd)|AVX [2]|immintrin.h|__m256d _mm256_permutevar_pd(\__m256d,\__m256i)|
|[_mm256_permutevar_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permutevar_ps)|AVX [2]|immintrin.h|__m256 _mm256_permutevar_ps (\__m256、\__m256i)|
|[_mm256_permutevar8x32_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permutevar8x32_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_permutevar8x32_epi32 (\__m256i、\__m256i)|
|[_mm256_permutevar8x32_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permutevar8x32_ps)|AVX2 [2]|immintrin.h|__m256 _mm256_permutevar8x32_ps (\__m256、\__m256i)|
|[_mm256_rcp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_rcp_ps)|AVX [2]|immintrin.h|__m256 _mm256_rcp_ps(\__m256)|
|[_mm256_round_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_round_pd)|AVX [2]|immintrin.h|__m256d _mm256_round_pd(\__m256d,int)|
|[_mm256_round_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_round_ps)|AVX [2]|immintrin.h|__m256 _mm256_round_ps (\__m256、int)|
|[_mm256_rsqrt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_rsqrt_ps)|AVX [2]|immintrin.h|__m256 _mm256_rsqrt_ps (\__m256)|
|[_mm256_sad_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sad_epu8)|AVX2 [2]|immintrin.h|__m256i _mm256_sad_epu8 (\__m256i、\__m256i)|
|[_mm256_set_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_epi16)|AVX [2]|immintrin.h|(__m256i _mm256_set_epi16(short|
|[_mm256_set_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_epi32)|AVX [2]|immintrin.h|__m256i _mm256_set_epi32(int,int,int,int,int,int,int,int)|
|[_mm256_set_epi64x](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_epi64x)|AVX [2]|immintrin.h|__m256i _mm256_set_epi64x(long long,long long,long long,long long)|
|[_mm256_set_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_epi8)|AVX [2]|immintrin.h|__m256i _mm256_set_epi8(char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char,char)|
|[_mm256_set_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_pd)|AVX [2]|immintrin.h|__m256d _mm256_set_pd(double,double,double,double)|
|[_mm256_set_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_ps)|AVX [2]|immintrin.h|__m256 _mm256_set_ps(float,float,float,float,float,float,float,float)|
|[_mm256_set1_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_epi16)|AVX [2]|immintrin.h|__m256i _mm256_set1_epi16(short)|
|[_mm256_set1_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_epi32)|AVX [2]|immintrin.h|__m256i _mm256_set1_epi32(int)|
|[_mm256_set1_epi64x](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_epi64x)|AVX [2]|immintrin.h|__m256i _mm256_set1_epi64x(long long)|
|[_mm256_set1_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_epi8)|AVX [2]|immintrin.h|__m256i _mm256_set1_epi8(char)|
|[_mm256_set1_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_pd)|AVX [2]|immintrin.h|__m256d _mm256_set1_pd(double)|
|[_mm256_set1_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_ps)|AVX [2]|immintrin.h|__m256 _mm256_set1_ps(float)|
|[_mm256_setr_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_epi16)|AVX [2]|immintrin.h|(__m256i _mm256_setr_epi16(short|
|[_mm256_setr_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_epi32)|AVX [2]|immintrin.h|__m256i _mm256_setr_epi32(int,int,int,int,int,int,int,int)|
|[_mm256_setr_epi64x](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_epi64x)|AVX [2]|immintrin.h|__m256i _mm256_setr_epi64x(long long,long long,long long,long long)|
|[_mm256_setr_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_epi8)|AVX [2]|immintrin.h|(__m256i _mm256_setr_epi8(char|
|[_mm256_setr_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_pd)|AVX [2]|immintrin.h|__m256d _mm256_setr_pd(double,double,double,double)|
|[_mm256_setr_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_ps)|AVX [2]|immintrin.h|__m256 _mm256_setr_ps(float,float,float,float,float,float,float,float)|
|[_mm256_setzero_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setzero_pd)|AVX [2]|immintrin.h|__m256d _mm256_setzero_pd(void)|
|[_mm256_setzero_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setzero_ps)|AVX [2]|immintrin.h|__m256 _mm256_setzero_ps(void)|
|[_mm256_setzero_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setzero_si256)|AVX [2]|immintrin.h|__m256i _mm256_setzero_si256(void)|
|[_mm256_shuffle_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shuffle_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_shuffle_epi32 (\__m256i、const int)|
|[_mm256_shuffle_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shuffle_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_shuffle_epi8 (\__m256i、\__m256i)|
|[_mm256_shuffle_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shuffle_pd)|AVX [2]|immintrin.h|__m256d _mm256_shuffle_pd (\__m256d、\__m256d、const int)|
|[_mm256_shuffle_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shuffle_ps)|AVX [2]|immintrin.h|__m256 _mm256_shuffle_ps (\__m256、\__m256、const int)|
|[_mm256_shufflehi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shufflehi_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_shufflehi_epi16 (\__m256i、const int)|
|[_mm256_shufflelo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shufflelo_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_shufflelo_epi16 (\__m256i、const int)|
|[_mm256_sign_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sign_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_sign_epi16 (\__m256i、\__m256i)|
|[_mm256_sign_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sign_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_sign_epi32 (\__m256i、\__m256i)|
|[_mm256_sign_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sign_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_sign_epi8 (\__m256i、\__m256i)|
|[_mm256_sll_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sll_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_sll_epi16 (\__m256i、\__m128i)|
|[_mm256_sll_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sll_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_sll_epi32 (\__m256i、\__m128i)|
|[_mm256_sll_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sll_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_sll_epi64 (\__m256i、\__m128i)|
|[_mm256_slli_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_slli_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_slli_epi16 (\__m256i、int)|
|[_mm256_slli_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_slli_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_slli_epi32 (\__m256i、int)|
|[_mm256_slli_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_slli_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_slli_epi64 (\__m256i、int)|
|[_mm256_slli_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_slli_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_slli_si256 (\__m256i、int)|
|[_mm256_sllv_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sllv_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_sllv_epi32 (\__m256i、\__m256i)|
|[_mm256_sllv_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sllv_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_sllv_epi64 (\__m256i、\__m256i)|
|[_mm256_sqrt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sqrt_pd)|AVX [2]|immintrin.h|__m256d _mm256_sqrt_pd(\__m256d)|
|[_mm256_sqrt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sqrt_ps)|AVX [2]|immintrin.h|__m256 _mm256_sqrt_ps(\__m256)|
|[_mm256_sra_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sra_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_sra_epi16 (\__m256i、\__m128i)|
|[_mm256_sra_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sra_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_sra_epi32 (\__m256i、\__m128i)|
|[_mm256_srai_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srai_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_srai_epi16 (\__m256i、int)|
|[_mm256_srai_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srai_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_srai_epi32 (\__m256i、int)|
|[_mm256_srav_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srav_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_srav_epi32 (\__m256i、\__m256i)|
|[_mm256_srl_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srl_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_srl_epi16 (\__m256i、\__m128i)|
|[_mm256_srl_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srl_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_srl_epi32 (\__m256i、\__m128i)|
|[_mm256_srl_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srl_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_srl_epi64 (\__m256i、\__m128i)|
|[_mm256_srli_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srli_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_srli_epi16 (\__m256i、int)|
|[_mm256_srli_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srli_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_srli_epi32 (\__m256i、int)|
|[_mm256_srli_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srli_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_srli_epi64 (\__m256i、int)|
|[_mm256_srli_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srli_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_srli_si256 (\__m256i、int)|
|[_mm256_srlv_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srlv_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_srlv_epi32 (\__m256i、\__m256i)|
|[_mm256_srlv_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srlv_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_srlv_epi64 (\__m256i、\__m256i)|
|[_mm256_store_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_store_pd)|AVX [2]|immintrin.h|void _mm256_store_pd (double \*、\__m256d)|
|[_mm256_store_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_store_ps)|AVX [2]|immintrin.h|void _mm256_store_ps (float \*、\__m256)|
|[_mm256_store_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_store_si256)|AVX [2]|immintrin.h|void _mm256_store_si256 (\__m256i \*、\__m256i)|
|[_mm256_storeu_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_storeu_pd)|AVX [2]|immintrin.h|void _mm256_storeu_pd (double \*、\__m256d)|
|[_mm256_storeu_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_storeu_ps)|AVX [2]|immintrin.h|void _mm256_storeu_ps (float \*、\__m256)|
|[_mm256_storeu_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_storeu_si256)|AVX [2]|immintrin.h|void _mm256_storeu_si256 (\__m256i \*、\__m256i)|
|[_mm256_stream_load_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_stream_load_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_stream_load_si256 (\__m256i const \*)|
|[_mm256_stream_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_stream_pd)|AVX [2]|immintrin.h|void __mm256_stream_pd (double \*、\__m256d)|
|[_mm256_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_stream_ps)|AVX [2]|immintrin.h|void _mm256_stream_ps (float \*p、\__m256 を)|
|[_mm256_stream_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_stream_si256)|AVX [2]|immintrin.h|void __mm256_stream_si256 (\__m256i \*、\__m256i)|
|[_mm256_sub_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_sub_epi16 (\__m256i、\__m256i)|
|[_mm256_sub_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_sub_epi32 (\__m256i、\__m256i)|
|[_mm256_sub_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_sub_epi64 (\__m256i、\__m256i)|
|[_mm256_sub_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_sub_epi8 (\__m256i、\__m256i)|
|[_mm256_sub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_pd)|AVX [2]|immintrin.h|__m256d _mm256_sub_pd (\__m256d、\__m256d)|
|[_mm256_sub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_ps)|AVX [2]|immintrin.h|__m256 _mm256_sub_ps (\__m256、\__m256)|
|[_mm256_subs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_subs_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_subs_epi16 (\__m256i、\__m256i)|
|[_mm256_subs_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_subs_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_subs_epi8 (\__m256i、\__m256i)|
|[_mm256_subs_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_subs_epu16)|AVX2 [2]|immintrin.h|__m256i _mm256_subs_epu16 (\__m256i、\__m256i)|
|[_mm256_subs_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_subs_epu8)|AVX2 [2]|immintrin.h|__m256i _mm256_subs_epu8 (\__m256i、\__m256i)|
|[_mm256_testc_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testc_pd)|AVX [2]|immintrin.h|int _mm256_testc_pd(\__m256d,\__m256d)|
|[_mm256_testc_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testc_ps)|AVX [2]|immintrin.h|int _mm256_testc_ps(\__m256,\__m256)|
|[_mm256_testc_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testc_si256)|AVX [2]|immintrin.h|int _mm256_testc_si256 (\__m256i、\__m256i)|
|[_mm256_testnzc_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testnzc_pd)|AVX [2]|immintrin.h|int _mm256_testnzc_pd(\__m256d,\__m256d)|
|[_mm256_testnzc_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testnzc_ps)|AVX [2]|immintrin.h|int _mm256_testnzc_ps (\__m256、\__m256)|
|[_mm256_testnzc_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testnzc_si256)|AVX [2]|immintrin.h|int _mm256_testnzc_si256 (\__m256i、\__m256i)|
|[_mm256_testz_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testz_pd)|AVX [2]|immintrin.h|int _mm256_testz_pd(\__m256d,\__m256d)|
|[_mm256_testz_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testz_ps)|AVX [2]|immintrin.h|int _mm256_testz_ps(\__m256,\__m256)|
|[_mm256_testz_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testz_si256)|AVX [2]|immintrin.h|int _mm256_testz_si256 (\__m256i、\__m256i)|
|[_mm256_unpackhi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_unpackhi_epi16 (\__m256i、\__m256i)|
|[_mm256_unpackhi_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_unpackhi_epi32 (\__m256i、\__m256i)|
|[_mm256_unpackhi_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_unpackhi_epi64 (\__m256i、\__m256i)|
|[_mm256_unpackhi_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_unpackhi_epi8 (\__m256i、\__m256i)|
|[_mm256_unpackhi_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_pd)|AVX [2]|immintrin.h|__m256d _mm256_unpackhi_pd (\__m256d、\__m256d)|
|[_mm256_unpackhi_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_ps)|AVX [2]|immintrin.h|__m256 _mm256_unpackhi_ps (\__m256、\__m256)|
|[_mm256_unpacklo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_epi16)|AVX2 [2]|immintrin.h|__m256i _mm256_unpacklo_epi16 (\__m256i、\__m256i)|
|[_mm256_unpacklo_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_epi32)|AVX2 [2]|immintrin.h|__m256i _mm256_unpacklo_epi32 (\__m256i、\__m256i)|
|[_mm256_unpacklo_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_epi64)|AVX2 [2]|immintrin.h|__m256i _mm256_unpacklo_epi64 (\__m256i、\__m256i)|
|[_mm256_unpacklo_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_epi8)|AVX2 [2]|immintrin.h|__m256i _mm256_unpacklo_epi8 (\__m256i、\__m256i)|
|[_mm256_unpacklo_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_pd)|AVX [2]|immintrin.h|__m256d _mm256_unpacklo_pd (\__m256d、\__m256d)|
|[_mm256_unpacklo_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_ps)|AVX [2]|immintrin.h|__m256 _mm256_unpacklo_ps (\__m256、\__m256)|
|[_mm256_xor_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_xor_pd)|AVX [2]|immintrin.h|__m256d _mm256_xor_pd(\__m256d,\__m256d)|
|[_mm256_xor_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_xor_ps)|AVX [2]|immintrin.h|__m256 _mm256_xor_ps (\__m256、\__m256)|
|[_mm256_xor_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_xor_si256)|AVX2 [2]|immintrin.h|__m256i _mm256_xor_si256 (\__m256i、\__m256i)|
|[_mm256_zeroall](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_zeroall)|AVX [2]|immintrin.h|void _mm256_zeroall(void)|
|[_mm256_zeroupper](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_zeroupper)|AVX [2]|immintrin.h|void _mm256_zeroupper(void)|
|[__movsb](../intrinsics/movsb.md)||intrin.h|VOID _ _movsb (IN PBYTE、const IN バイト\*、IN SIZE_T)|
|[__movsd](../intrinsics/movsd.md)||intrin.h|VOID _ _movsd (IN PDWORD、const の DWORD \*、IN SIZE_T)|
|[__movsq](../intrinsics/movsq.md)||intrin.h|VOID _ _movsq (IN PDWORD64、const IN DWORD64 \*、IN SIZE_T)|
|[__movsw](../intrinsics/movsw.md)||intrin.h|VOID _ _movsw (IN PWORD、const の WORD \*、IN SIZE_T)|
|[_mul128](../intrinsics/mul128.md)||intrin.h|_ _int64 _mul128 (\__ _int64 の乗数\__ _int64 の被乗数\__ _int64 \*highproduct)|
|[__mulh](../intrinsics/mulh.md)||intrin.h|__int64 \__mulh(\__int64,\__int64)|
|_mulx_u32|BMI [2]|immintrin.h|符号なしの int _mulx_u32 (符号なしの int、unsigned int、unsigned int\*)|
|_mulx_u64|BMI [2]|immintrin.h|unsigned _ _int64 _mulx_u64 (unsigned \_、符号なし _ _int64 \_、符号なし _ _int64 \__ _int64\*)|
|[__nop](../intrinsics/nop.md)||intrin.h|void __nop(void)|
|__nvreg_restore_fence||intrin.h|void __nvreg_restore_fence(void)|
|__nvreg_save_fence||intrin.h|void __nvreg_save_fence(void)|
|[__outbyte](../intrinsics/outbyte.md)||intrin.h|void __outbyte(unsigned short Port,unsigned char Data)|
|[__outbytestring](../intrinsics/outbytestring.md)||intrin.h|void _ _outbytestring (符号なし short ポート、unsigned char\*バッファー、時間数の符号なし)|
|[__outdword](../intrinsics/outdword.md)||intrin.h|void __outdword(unsigned short Port,unsigned long Data)|
|[__outdwordstring](../intrinsics/outdwordstring.md)||intrin.h|void _ _outdwordstring (符号なしの時間の長い符号なし short のポート\*バッファー、時間数の符号なし)|
|[__outword](../intrinsics/outword.md)||intrin.h|void __outword(unsigned short Port,unsigned short Data)|
|[__outwordstring](../intrinsics/outwordstring.md)||intrin.h|void _ _outwordstring (符号なしの短い符号なし short のポート\*バッファー、時間数の符号なし)|
|[_pdep_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_pdep_u32)|BMI [2]|immintrin.h|unsigned int _pdep_u32(unsigned int,unsigned int)|
|[_pdep_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_pdep_u64)|BMI [2]|immintrin.h|unsigned __int64 _pdep_u64(unsigned \__int64,unsigned \__int64)|
|[_pext_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_pext_u32)|BMI [2]|immintrin.h|unsigned int _pext_u32(unsigned int,unsigned int)|
|[_pext_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_pext_u64)|BMI [2]|immintrin.h|unsigned __int64 _pext_u64(unsigned \__int64,unsigned \__int64)|
|[__popcnt](../intrinsics/popcnt16-popcnt-popcnt64.md)|POPCNT|intrin.h|unsigned int __popcnt(unsigned int)|
|[__popcnt16](../intrinsics/popcnt16-popcnt-popcnt64.md)|POPCNT|intrin.h|unsigned short __popcnt16(unsigned short)|
|[__popcnt64](../intrinsics/popcnt16-popcnt-popcnt64.md)|POPCNT|intrin.h|unsigned __int64 \__popcnt64(unsigned \__int64)|
|[_rdrand16_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdrand16_step)|RDRAND [2]|immintrin.h|int _rdrand16_step (unsigned short \*)|
|[_rdrand32_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdrand32_step)|RDRAND [2]|immintrin.h|int _rdrand32_step (unsigned int \*)|
|[_rdrand64_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdrand64_step)|RDRAND [2]|immintrin.h|int _rdrand64_step (unsigned \__ _int64 \*)|
|[_rdseed16_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdseed16_step)|RDSEED [2]|immintrin.h|int _rdseed16_step (unsigned short \*)|
|[_rdseed32_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdseed32_step)|RDSEED [2]|immintrin.h|int _rdseed32_step (unsigned int \*)|
|[_rdseed64_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdseed64_step)|RDSEED [2]|immintrin.h|int _rdseed64_step (unsigned \__ _int64 \*)|
|[__rdtsc](../intrinsics/rdtsc.md)||intrin.h|unsigned __int64 \__rdtsc(void)|
|[__rdtscp](../intrinsics/rdtscp.md)|RDTSCP|intrin.h|符号なし _ _int64 \__rdtscp (unsigned int\*)|
|[_ReadBarrier](../intrinsics/readbarrier.md)||intrin.h|void _ReadBarrier(void)|
|[__readcr0](../intrinsics/readcr0.md)||intrin.h|unsigned __int64 \__readcr0(void)|
|[__readcr2](../intrinsics/readcr2.md)||intrin.h|unsigned __int64 \__readcr2(void)|
|[__readcr3](../intrinsics/readcr3.md)||intrin.h|unsigned __int64 \__readcr3(void)|
|[__readcr4](../intrinsics/readcr4.md)||intrin.h|unsigned __int64 \__readcr4(void)|
|[__readcr8](../intrinsics/readcr8.md)||intrin.h|unsigned __int64 \__readcr8(void)|
|[__readdr](../intrinsics/readdr.md)||intrin.h|unsigned __int64 \__readdr(unsigned)|
|[__readeflags](../intrinsics/readeflags.md)||intrin.h|unsigned __int64 \__readeflags(void)|
|[_readfsbase_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_readfsbase_u32)|FSGSBASE [2]|immintrin.h|unsigned int _readfsbase_u32(void)|
|[_readfsbase_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_readfsbase_u64)|FSGSBASE [2]|immintrin.h|unsigned __int64 _readfsbase_u64(void)|
|[_readgsbase_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_readgsbase_u32)|FSGSBASE [2]|immintrin.h|unsigned int _readgsbase_u32(void)|
|[_readgsbase_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_readgsbase_u64)|FSGSBASE [2]|immintrin.h|unsigned __int64 _readgsbase_u64(void)|
|[__readgsbyte](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)||intrin.h|unsigned char __readgsbyte(unsigned long Offset)|
|[__readgsdword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)||intrin.h|unsigned long __readgsdword(unsigned long Offset)|
|[__readgsqword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)||intrin.h|unsigned __int64 \__readgsqword(unsigned long Offset)|
|[__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)||intrin.h|unsigned short __readgsword(unsigned long Offset)|
|[__readmsr](../intrinsics/readmsr.md)||intrin.h|unsigned __int64 \__readmsr(unsigned long)|
|[__readpmc](../intrinsics/readpmc.md)||intrin.h|unsigned __int64 \__readpmc(unsigned long a)|
|[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)||intrin.h|void _ReadWriteBarrier(void)|
|[_ReturnAddress](../intrinsics/returnaddress.md)||intrin.h|void \* _ReturnAddress(void)|
|_rorx_u32|BMI [2]|immintrin.h|unsigned int _rorx_u32(unsigned int,const unsigned int)|
|_rorx_u64|BMI [2]|immintrin.h|unsigned _ _int64 _rorx_u64 (unsigned \__ _int64、const の符号なし int)|
|[_rotl16](../intrinsics/rotl8-rotl16.md)||intrin.h|unsigned short _rotl16(unsigned short value,unsigned char shift)|
|[_rotl8](../intrinsics/rotl8-rotl16.md)||intrin.h|unsigned char _rotl8(unsigned char value,unsigned char shift)|
|[_rotr16](../intrinsics/rotr8-rotr16.md)||intrin.h|unsigned short _rotr16(unsigned short value,unsigned char shift)|
|[_rotr8](../intrinsics/rotr8-rotr16.md)||intrin.h|unsigned char _rotr8(unsigned char value,unsigned char shift)|
|_rsm||intrin.h|void _rsm(void)|
|_sarx_i32|BMI [2]|immintrin.h|int _sarx_i32(int,unsigned int)|
|_sarx_i64|BMI [2]|immintrin.h|_ _int64 _sarx_i64 (\__ _int64、符号なし int)|
|[__segmentlimit](../intrinsics/segmentlimit.md)||intrin.h|unsigned long __segmentlimit(unsigned long a)|
|_sgdt||intrin.h|void _sgdt (void\*)|
|[__shiftleft128](../intrinsics/shiftleft128.md)||intrin.h|unsigned __int64 \__shiftleft128(unsigned \__int64 LowPart,unsigned \__int64 HighPart,unsigned char Shift)|
|[__shiftright128](../intrinsics/shiftright128.md)||intrin.h|unsigned __int64 \__shiftright128(unsigned \__int64 LowPart,unsigned \__int64 HighPart,unsigned char Shift)|
|_shlx_u32|BMI [2]|immintrin.h|unsigned int _shlx_u32(unsigned int,unsigned int)|
|_shlx_u64|BMI [2]|immintrin.h|unsigned _ _int64 _shlx_u64 (unsigned \__ _int64、符号なし int)|
|_shrx_u32|BMI [2]|immintrin.h|unsigned int _shrx_u32(unsigned int,unsigned int)|
|_shrx_u64|BMI [2]|immintrin.h|unsigned _ _int64 _shrx_u64 (unsigned \__ _int64、符号なし int)|
|[__sidt](../intrinsics/sidt.md)||intrin.h|void _ _sidt (void\*)|
|__slwpcb|LWP [1]|ammintrin.h|void \*__slwpcb(void)|
|_stac|SMAP|intrin.h|void _stac(void)|
|_store_be_u16<br /><br /> [_storebe_i16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_storebe_i16&expand=5141)|MOVBE|immintrin.h|void _store_be_u16 (void \*、unsigned short) です。<br /><br /> void _storebe_i16 (void \*, short) です。[3]|
|_store_be_u32<br /><br /> [_storebe_i32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_storebe_i32&expand=5142)|MOVBE|immintrin.h|void _store_be_u32 (void \*、unsigned int);<br /><br /> void _storebe_i32 (void \*int);[3]|
|_store_be_u64<br /><br /> [_storebe_i64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_storebe_i64&expand=5143)|MOVBE|immintrin.h|void _store_be_u64 (void\*の符号なし\__ _int64)。<br /><br /> void _storebe_i64 (void \*、 \__ _int64)。[3]|
|_Store_HLERelease|HLE [2]|immintrin.h|void _Store_HLERelease (long volatile \*, long)|
|_Store64_HLERelease|HLE [2]|immintrin.h|void _Store64_HLERelease (\__ _int64 volatile \*、\__ _int64)|
|_StorePointer_HLERelease|HLE [2]|immintrin.h|void _StorePointer_HLERelease (void \* volatile \*, void \*)|
|[__stosb](../intrinsics/stosb.md)||intrin.h|void __stosb(IN PBYTE,IN BYTE,IN SIZE_T)|
|[__stosd](../intrinsics/stosd.md)||intrin.h|void __stosd(IN PDWORD,IN DWORD,IN SIZE_T)|
|[__stosq](../intrinsics/stosq.md)||intrin.h|void __stosq(IN PDWORD64,IN DWORD64,IN SIZE_T)|
|[__stosw](../intrinsics/stosw.md)||intrin.h|void __stosw(IN PWORD,IN WORD,IN SIZE_T)|
|_subborrow_u16||intrin.h|unsigned char _subborrow_u16 (unsigned char b_in、符号なし short src1、短い符号なしの符号なしの短い src2\*相違)|
|[_subborrow_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_subborrow_u32)||intrin.h|unsigned char _subborrow_u32 (unsigned char b_in、符号なし int src1、符号なし int src2、符号なし int\*相違)|
|[_subborrow_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_subborrow_u64)||intrin.h|unsigned char _subborrow_u64 (unsigned char b_in、符号なしの\_符号なしの _ _int64 src1 \__ _int64 src2、符号なし\__ _int64\*差分)|
|_subborrow_u8||intrin.h|unsigned char _subborrow_u8 (unsigned char b_in、src1 の符号なしの char、unsigned char src2、符号なしの char\*相違)|
|[__svm_clgi](../intrinsics/svm-clgi.md)||intrin.h|void __svm_clgi(void)|
|[__svm_invlpga](../intrinsics/svm-invlpga.md)||intrin.h|void _ _svm_invlpga (void\*int)|
|[__svm_skinit](../intrinsics/svm-skinit.md)||intrin.h|void __svm_skinit(int)|
|[__svm_stgi](../intrinsics/svm-stgi.md)||intrin.h|void __svm_stgi(void)|
|[__svm_vmload](../intrinsics/svm-vmload.md)||intrin.h|void __svm_vmload(size_t)|
|[__svm_vmrun](../intrinsics/svm-vmrun.md)||intrin.h|void __svm_vmrun(size_t)|
|[__svm_vmsave](../intrinsics/svm-vmsave.md)||intrin.h|void __svm_vmsave(size_t)|
|_t1mskc_u32|ABM [1]|ammintrin.h|unsigned int _t1mskc_u32(unsigned int)|
|_t1mskc_u64|ABM [1]|ammintrin.h|unsigned __int64 _t1mskc_u64(unsigned \__int64)|
|[_tzcnt_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_tzcnt_u32)|BMI|ammintrin.h, immintrin.h|unsigned int _tzcnt_u32(unsigned int)|
|[_tzcnt_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_tzcnt_u64)|BMI|ammintrin.h, immintrin.h|unsigned __int64 _tzcnt_u64(unsigned \__int64)|
|_tzmsk_u32|ABM [1]|ammintrin.h|unsigned int _tzmsk_u32(unsigned int)|
|_tzmsk_u64|ABM [1]|ammintrin.h|unsigned __int64 _tzmsk_u64(unsigned \__int64)|
|[__ud2](../intrinsics/ud2.md)||intrin.h|void __ud2(void)|
|[__ull_rshift](../intrinsics/ull-rshift.md)||intrin.h|符号なし _ _int64 [pascal/cdecl] \__ull_rshift (unsigned \_int、_ _int64)|
|[_umul128](../intrinsics/umul128.md)||intrin.h|unsigned _ _int64 _umul128 (unsigned\_符号なし _ _int64 乗数\_符号なしの _ _int64 multiplicand \__ _int64 \*highproduct)|
|[__umulh](../intrinsics/umulh.md)||intrin.h|unsigned __int64 \__umulh(unsigned \__int64,unsigned \__int64)|
|[__vmx_off](../intrinsics/vmx-off.md)||intrin.h|void __vmx_off(void)|
|[__vmx_on](../intrinsics/vmx-on.md)||intrin.h|unsigned char _ _vmx_on (unsigned \__ _int64\*)|
|[__vmx_vmclear](../intrinsics/vmx-vmclear.md)||intrin.h|unsigned char _ _vmx_vmclear (unsigned \__ _int64\*)|
|[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)||intrin.h|unsigned char __vmx_vmlaunch(void)|
|[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)||intrin.h|unsigned char _ _vmx_vmptrld (unsigned \__ _int64\*)|
|[__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)||intrin.h|void _ _vmx_vmptrst (unsigned \__ _int64 \*)|
|[__vmx_vmread](../intrinsics/vmx-vmread.md)||intrin.h|unsigned char _ _vmx_vmread (size_t、size_t\*)|
|[__vmx_vmresume](../intrinsics/vmx-vmresume.md)||intrin.h|unsigned char __vmx_vmresume(void)|
|[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)||intrin.h|unsigned char __vmx_vmwrite(size_t,size_t)|
|[__wbinvd](../intrinsics/wbinvd.md)||intrin.h|void __wbinvd(void)|
|[_WriteBarrier](../intrinsics/writebarrier.md)||intrin.h|void _WriteBarrier(void)|
|[__writecr0](../intrinsics/writecr0.md)||intrin.h|void __writecr0(unsigned \__int64)|
|[__writecr3](../intrinsics/writecr3.md)||intrin.h|void __writecr3(unsigned \__int64)|
|[__writecr4](../intrinsics/writecr4.md)||intrin.h|void __writecr4(unsigned \__int64)|
|[__writecr8](../intrinsics/writecr8.md)||intrin.h|void __writecr8(unsigned \__int64)|
|[__writedr](../intrinsics/writedr.md)||intrin.h|void __writedr(unsigned,unsigned \__int64)|
|[__writeeflags](../intrinsics/writeeflags.md)||intrin.h|_ _writeeflags を無効にする (unsigned \__ _int64)|
|[_writefsbase_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_writefsbase_u32)|FSGSBASE [2]|immintrin.h|void _writefsbase_u32(unsigned int)|
|[_writefsbase_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_writefsbase_u64)|FSGSBASE [2]|immintrin.h|void _writefsbase_u64(unsigned \__int64)|
|[_writegsbase_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_writegsbase_u32)|FSGSBASE [2]|immintrin.h|void _writegsbase_u32(unsigned int)|
|[_writegsbase_u64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_writegsbase_u64)|FSGSBASE [2]|immintrin.h|void _writegsbase_u64(unsigned \__int64)|
|[__writegsbyte](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)||intrin.h|void __writegsbyte(unsigned long Offset,unsigned char Data)|
|[__writegsdword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)||intrin.h|void __writegsdword(unsigned long Offset,unsigned long Data)|
|[__writegsqword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)||intrin.h|void __writegsqword(unsigned long Offset,unsigned \__int64 Data)|
|[__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)||intrin.h|void __writegsword(unsigned long Offset,unsigned short Data)|
|[__writemsr](../intrinsics/writemsr.md)||intrin.h|void __writemsr(unsigned long,unsigned \__int64)|
|[_xabort](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xabort)|RTM [2]|immintrin.h|void _xabort(unsigned int)|
|[_xbegin](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xbegin)|RTM [2]|immintrin.h|unsigned _xbegin(void)|
|[_xend](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xend)|RTM [2]|immintrin.h|void _xend(void)|
|[_xgetbv](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xgetbv)|XSAVE [2]|immintrin.h|unsigned __int64 _xgetbv(unsigned int)|
|[_xrstor](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xrstor)|XSAVE [2]|immintrin.h|void _xrstor (const void\*の符号なし\__ _int64)|
|[_xrstor64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xrstor64)|XSAVE [2]|immintrin.h|void _xrstor64 (const void\*の符号なし\__ _int64)|
|[_xsave](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xsave)|XSAVE [2]|immintrin.h|void _xsave (void\*の符号なし\__ _int64)|
|[_xsave64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xsave64)|XSAVE [2]|immintrin.h|void _xsave64 (void\*の符号なし\__ _int64)|
|[_xsaveopt](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xsaveopt)|XSAVEOPT [2]|immintrin.h|void _xsaveopt (void\*の符号なし\__ _int64)|
|[_xsaveopt64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xsaveopt64)|XSAVEOPT [2]|immintrin.h|void _xsaveopt64 (void\*の符号なし\__ _int64)|
|[_xsetbv](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xsetbv)|XSAVE [2]|immintrin.h|void _xsetbv(unsigned int,unsigned \__int64)|
|[_xtest](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xtest)|XTEST [2]|immintrin.h|unsigned char _xtest(void)|

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)  
[ARM 組み込み](../intrinsics/arm-intrinsics.md)  
[x86 組み込み](../intrinsics/x86-intrinsics-list.md)    