---
title: 使用して、インライン アセンブリでのレジスタの維持 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60506f53eb1933e5acbb03318edada82a8904386
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677019"
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>インライン アセンブリでのレジスタの使用および保持

**Microsoft 固有の仕様**

一般に、ことを想定しないでください、レジスタが指定した値にあるときに、`__asm`ブロックを開始します。 レジスタの値を個別にわたって維持されますとは限りません`__asm`ブロックします。 インライン コードのブロックを終了して、開始すると場合、は、最初のブロックから値を保持する 2 番目のブロックでのレジスタに依存することはできません。 `__asm`ブロックは、通常の制御フローからの値の結果を登録内容を継承します。

使用する場合、`__fastcall`呼び出し規約、コンパイラ引数を渡します関数の代わりにレジスタ、スタックにします。 これは、関数で問題が発生できる`__asm`関数はどのレジスタにパラメーターを確認する方法があるないためにをブロックします。 関数は、EAX でパラメーターを受け取ることが発生し、EAX に別のものをすぐに格納、元のパラメーターは失われます。 さらで宣言された任意の関数に ECX レジスタを保持する必要があります`__fastcall`します。

このような登録の競合を避けるためには、使用しないでください、`__fastcall`を含む関数の規則、`__asm`ブロックします。 指定した場合、`__fastcall`規則、/Gr コンパイラ オプションでグローバルに宣言を含むすべての関数、`__asm`ブロックと一緒に`__cdecl`または`__stdcall`します。 (、`__cdecl`属性にその関数に対して C の呼び出し規則を使用してコンパイラに指示します)。/Gr でコンパイルしない場合は、使用して、関数の宣言を回避、`__fastcall`属性。

使用する場合`__asm`EAX、EBX、ECX、EDX、ESI、または EDI レジスタを保持するために C と C++ の関数のアセンブリ言語を記述する必要はありません。 たとえば、POWER2 で。例では C[インライン アセンブリでの書き込み関数](../../assembler/inline/writing-functions-with-inline-assembly.md)、`power2`関数は、EAX レジスタに値を保持しません。 ただし、これらのレジスタを使用して、影響を与えるコードの品質レジスタ アロケーターが全体で値を格納する使用できないため`__asm`ブロックします。 さらに、インライン アセンブラー コードで EBX、ESI または EDI を使用すると、保存し、関数プロローグおよびエピローグでこれらのレジスタを復元するコンパイラを強制します。

スコープ (DS、SS、SP、BP、フラグ レジスタなど) を使用するその他のレジスタを保持する必要があります、`__asm`ブロックします。 (たとえば、スタックを切り替える) に変更するには、いくつか理由がない限り、ESP および EBP レジスタを保持する必要があります。 参照してください[インライン アセンブリの最適化](../../assembler/inline/optimizing-inline-assembly.md)します。

いくつか SSE 型には、強制的にスタック配置の動的なコードを生成するコンパイラ スタックの 8 バイトのアラインメントが必要です。 配置後にローカル変数と関数のパラメーターの両方にアクセスできるようにするには、コンパイラは、2 つのフレーム ポインターを保持します。  コンパイラは、フレーム ポインターの省略 (FPO) を実行する場合、EBP と ESP を使用します。  コンパイラが FPO を実行していない場合、EBX、EBP が使用されます。 コードの実行を正しく確実には、フレーム ポインターを変更できますが、関数は動的スタック配置が必要な場合は、asm コードで EBX を変更しないでください。 関数から 8 バイトのアラインされた型を移動するか、EBX は使用しないでください。

> [!NOTE]
>  STD または CLD 命令を使用して方向フラグが、インライン アセンブリ コードに変更された場合は、元の値にフラグを復元する必要があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>