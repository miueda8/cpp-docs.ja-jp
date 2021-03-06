---
title: インライン アセンブリの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49660bdc6d2eb84e6e1bbaeb5ebf0d57e484e9e1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687877"
---
# <a name="optimizing-inline-assembly"></a>インライン アセンブリの最適化

**Microsoft 固有の仕様**

有無、`__asm`関数内のブロックがいくつかの方法での最適化に影響します。 コンパイラはまず、最適化するために、`__asm`自体をブロックします。 アセンブリ言語で記述するものが正確に取得します。 2 番目の存在、`__asm`ブロックに影響は、変数の記憶域を登録します。 コンパイラで変数をレジスタ格納を回避できます、`__asm`ブロックでレジスタの内容に変更する場合、`__asm`ブロック。 最後に、いくつかその他の関数全体の最適化の場合は、アセンブリ言語で関数を含めることによって影響が受けるされます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>