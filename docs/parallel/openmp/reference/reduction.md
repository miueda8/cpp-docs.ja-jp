---
title: 削減 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- reduction
dev_langs:
- C++
helpviewer_keywords:
- reduction OpenMP clause
ms.assetid: a2b051af-5a1b-4c00-9cc7-692bb43653fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2b90ef2eeca60a305cd8836e09dc81940392d2c
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "42540282"
---
# <a name="reduction"></a>reduction
各スレッドに対してプライベートである 1 つまたは複数の変数を並行領域の最後のリダクション演算の件名を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
reduction(operation:var)  
```  
  
## <a name="remarks"></a>Remarks  
 指定項目  
  
 `operation`  
 変数に対して実行する操作の演算子 (`var`)、並列領域の最後にします。  
  
 `var`  
 スカラー リダクションを実行する 1 つまたは複数の変数。 1 つ以上の変数が指定されている場合は、変数名をコンマで区切ります。  
  
## <a name="remarks"></a>Remarks  
 `reduction` 次のディレクティブに適用されます。  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.7.2.6 削減](../../../parallel/openmp/2-7-2-6-reduction.md)します。  
  
## <a name="example"></a>例  
  
```  
// omp_reduction.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define SUM_START   1  
#define SUM_END     10  
#define FUNC_RETS   {1, 1, 1, 1, 1}  
  
int bRets[5] = FUNC_RETS;  
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;  
  
int func1( ) {return bRets[0];}  
int func2( ) {return bRets[1];}  
int func3( ) {return bRets[2];}  
int func4( ) {return bRets[3];}  
int func5( ) {return bRets[4];}  
  
int main( )   
{  
    int nRet = 0,   
        nCount = 0,   
        nSum = 0,   
        i,   
        bSucceed = 1;  
  
    omp_set_num_threads(NUM_THREADS);  
  
    #pragma omp parallel reduction(+ : nCount)  
    {  
        nCount += 1;  
  
        #pragma omp for reduction(+ : nSum)  
        for (i = SUM_START ; i <= SUM_END ; ++i)  
            nSum += i;  
  
        #pragma omp sections reduction(&& : bSucceed)  
        {  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func1( );  
            }    
  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func2( );  
            }  
  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func3( );  
            }  
  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func4( );  
            }  
  
            #pragma omp section  
            {  
                bSucceed = bSucceed && func5( );  
            }  
        }  
    }  
  
    printf_s("The parallel section was executed %d times "  
             "in parallel.\n", nCount);  
    printf_s("The sum of the consecutive integers from "  
             "%d to %d, is %d\n", 1, 10, nSum);  
  
    if (bSucceed)  
        printf_s("All of the functions, func1 through "  
                 "func5 succeeded!\n");  
    else  
        printf_s("One or more of the functions, func1 "  
                 "through func5 failed!\n");  
  
    if (nCount != NUM_THREADS)   
    {  
        printf_s("ERROR: For %d threads, %d were counted!\n",   
                 NUM_THREADS, nCount);  
        nRet |= 0x1;  
   }  
  
    if (nSum != nSumCalc)   
    {  
        printf_s("ERROR: The sum of %d through %d should be %d, "  
                "but %d was reported!\n",   
                SUM_START, SUM_END, nSumCalc, nSum);  
        nRet |= 0x10;  
    }  
  
    if (bSucceed != (bRets[0] && bRets[1] &&   
                     bRets[2] && bRets[3] && bRets[4]))   
    {  
        printf_s("ERROR: The sum of %d through %d should be %d, "  
                 "but %d was reported!\n",   
                 SUM_START, SUM_END, nSumCalc, nSum);  
        nRet |= 0x100;  
    }  
}  
```  
  
```Output  
The parallel section was executed 4 times in parallel.  
The sum of the consecutive integers from 1 to 10, is 55  
All of the functions, func1 through func5 succeeded!  
```  
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)