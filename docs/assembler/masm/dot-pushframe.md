---
title: .PUSHFRAME |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .PUSHFRAME
dev_langs:
- C++
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c86ba043eb185e9cc5697f236b907ae8177d6824
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689490"
---
# <a name="pushframe"></a>.PUSHFRAME

生成、`UWOP_PUSH_MACHFRAME`アンワインド コードのエントリ。 場合、省略可能な`code`を指定すると、アンワインド コードのエントリが 1 の修飾子を指定します。 それ以外の場合、修飾子には 0 です。

## <a name="syntax"></a>構文

> .PUSHFRAME [コード]

## <a name="remarks"></a>Remarks

.PUSHFRAME が ml64.exe ユーザーは、フレームの関数をアンワインドする方法を指定することしから拡張すると、プロローグ内でのみ使用できますが、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[します。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブは、コードを生成しませんのみを生成する`.xdata`と`.pdata`します。 .PUSHFRAME は、実際にアンワインド操作を実装する手順によって先行されなければなりません。 アンワインド ディレクティブと契約を確認します。 マクロでのアンワインドに本来はコードの両方をラップすることをお勧めします。

詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)します。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>