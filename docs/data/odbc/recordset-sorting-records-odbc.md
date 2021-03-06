---
title: 'レコード セット: レコードの並べ替え (ODBC) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c78603e12aec7653e7c5c62d9a0282241ccda99e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337831"
---
# <a name="recordset-sorting-records-odbc"></a>レコードセット: レコードの並べ替え (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、レコード セットを並べ替える方法について説明します。 並べ替えには、基になる 1 つまたは複数の列を指定して、昇順または降順を指定することができます (**ASC**または**DESC**;**ASC**既定値は、) の各列を指定します。 たとえば、2 つの列を指定する場合はレコードの並べ替え最初という名前の最初の列とし、という名前の 2 番目の列。 SQL **ORDER BY**句は、並べ替えを定義します。 フレームワークを追加すると、 **ORDER BY**句をレコード セットの SQL クエリを選択範囲の順序付け句コントロール。  
  
 呼び出す前に、オブジェクトを構築した後は、レコード セットの並べ替え順序を確立する必要があります、`Open`メンバー関数 (または呼び出す前に、`Requery`メンバー関数の既存のレコード セット オブジェクト`Open`メンバー関数がされています。既に呼び出されて)。  
  
#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>レコード セット オブジェクトの並べ替え順序を指定するには  
  
1.  新しいレコード セット オブジェクトを作成する (またはを呼び出す準備`Requery`既存の)。  
  
2.  オブジェクトの値を設定[レコード](../../mfc/reference/crecordset-class.md#m_strsort)データ メンバー。  
  
     並べ替えは、null で終わる文字列です。 内容が含まれている、 **ORDER BY**句がキーワードではなく**ORDER BY**します。 たとえば、次のように使用します。  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  フィルターやロック モードは、パラメーターなどの必要なその他のオプションを設定します。  
  
4.  呼び出す`Open`に新しいオブジェクト (または`Requery`既存のオブジェクト)。  
  
 選択されたレコードは順序付けと指定します。 たとえば、一連の生徒レコード名、姓の順で降順に並べ替えるに、次のように行います。  
  
```cpp  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 レコード セットには、すべての降順に並べ替えられます (z から A) して、姓、し、最初の名前で、学生のレコードが含まれています。  
  
> [!NOTE]
>  場合に、独自の SQL 文字列を渡すことによって、レコード セットの既定の SQL 文字列を上書きする`Open`、カスタム文字列がある場合は、並べ替えを設定しないでください、 **ORDER BY**句。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [レコードセット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)