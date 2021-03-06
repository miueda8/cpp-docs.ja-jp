---
title: C ランタイム エラー R6002 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6002
dev_langs:
- C++
helpviewer_keywords:
- R6002
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50a970ecea4fdd7d397c09672b0548be947cab1e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298565"
---
# <a name="c-runtime-error-r6002"></a>C ランタイム エラー R6002
浮動小数点のサポートを読み込めませんでした。  
  
 必要な浮動小数点ライブラリはリンクされませんでした。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーは、いくつかの理由が考えられますが、多くの場合、それがまたはが原因で、アプリのコードの欠陥特定のコンピューターのプロセッサの作成されませんでしたするアプリを実行しようとしています。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [** を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 このエラーは、浮動小数点のライブラリがリンクされていないアプリに発生することができます。 これらの原因のいずれかを確認します。  
  
-   書式指定文字列、`printf_s`または`scanf_s`関数には、浮動小数点の書式指定が含まれているし、プログラムを含まないは任意の浮動小数点値または変数です。 この問題を解決するには、浮動小数点形式仕様に対応する浮動小数点引数を使用またはプログラムで別の場所、浮動小数点の割り当てを実行します。 これにより、読み込まれる浮動小数点サポートされます。  
  
-   コンパイラは、必要な場合にのみ浮動小数点のサポートを読み込むことにより、プログラムのサイズを最小化します。 コンパイラでは、必要な浮動小数点ルーチンが読み込まれないように浮動小数点演算または浮動小数点形式の仕様を書式指定文字列で検出することはできません。 この問題を解決するには、浮動小数点の書式指定を使用して、浮動小数点引数を指定またはプログラムで別の場所、浮動小数点の割り当てを実行します。 これにより、読み込まれる浮動小数点サポートされます。  
  
-   C ライブラリは、プログラムでは、混合言語、プログラムがリンクされている場合 FORTRAN ライブラリの前に指定されました。 再リンクし、最後に、C ライブラリを指定します。