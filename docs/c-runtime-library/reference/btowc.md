---
title: btowc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- btowc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- btowc
dev_langs:
- C++
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d0e56649218e6249550638af4e198cbd1284bc2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393317"
---
# <a name="btowc"></a>btowc

初回のシフト状態で整数が有効なシングルバイト文字を表すかどうかを判断します。

## <a name="syntax"></a>構文

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>パラメーター

*character*<br/>
テストする整数。

## <a name="return-value"></a>戻り値

初回のシフト状態で整数が有効なシングルバイト文字を表す場合、文字のワイド文字表現を返します。 初回のシフト状態で整数が EOF の場合、あるいは有効なシングルバイト文字ではない場合、WEOF を返します。 この関数の出力は、現在の影響を受けた**LC_TYPE**ロケール。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**btowc**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
