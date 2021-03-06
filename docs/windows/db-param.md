---
title: db_param |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_param
dev_langs:
- C++
helpviewer_keywords:
- db_param attribute
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c3bfa286e253ef634a42fea5a5c926981174c400
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613002"
---
# <a name="dbparam"></a>db_param

入力または出力パラメーターを使用して、指定したメンバー変数を関連付けるし、変数を区切ります。

## <a name="syntax"></a>構文

```cpp
[ db_param(
   ordinal,
   paramtype="DBPARAMIO_INPUT",
   dbtype,
   precision,
   scale,
   status,
   length
) ]
```

### <a name="parameters"></a>パラメーター

*序数*  
データをバインドする行セット内のフィールドに対応する列数 (DBCOLUMNINFO 序数)。

*paramtype* (省略可能)  
パラメーターに設定する型。 プロバイダーは、基になるデータ ソースでサポートされているパラメーター I/O 型のみをサポートします。 種類は、次の 1 つまたは複数の値の組み合わせです。

- DBPARAMIO_INPUT 入力パラメーター。

- DBPARAMIO_OUTPUT 出力パラメーター。

- DBPARAMIO_NOTPARAM アクセサーにパラメーターがありません。 設定`eParamIO`行では、この値にアクセサー ユーザーに通知するパラメーターは無視されます。

*dbtype* (省略可能)  
OLE DB[型インジケーター](/previous-versions/windows/desktop/ms711251\(v=vs.85\))列エントリにします。

*有効桁数*(省略可能)  
列のエントリに使用する有効桁数です。 詳細については、説明を参照してください`bPrecision`の要素、 [DBBINDING 構造体。](/previous-versions/windows/desktop/ms716845\(v=vs.85\))

*スケール*(省略可能)  
列のエントリに使用する小数点以下桁数。 詳細については、説明を参照してください`bScale`の要素、 [DBBINDING 構造体。](/previous-versions/windows/desktop/ms716845\(v=vs.85\))

*ステータス*(省略可能)  
この列の状態を保持するために使用するメンバー変数です。 状態は、列の値がデータ値や NULL など、他のいくつかの値であるかどうかを示します。 使用可能な値は、次を参照してください。[状態](/previous-versions/windows/desktop/ms722617\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。

*長さ*(省略可能)  
メンバー変数 (バイト単位)、列のサイズを保持するために使用します。

## <a name="remarks"></a>Remarks

**db_param**パラメーターを定義することでコマンドを使用する; で使用するため`db_command`します。 たとえば、使用することができます**db_param** SQL クエリまたはストアド プロシージャのパラメーターをバインドします。 ストアド プロシージャのパラメーターは疑問符 (?) で示されています、パラメーターの順序でデータ メンバーにバインドする必要があります。

**db_param** OLE DB に参加できるメンバー データを取り出すため`ICommandWithParameters`-ベースのバインド。 パラメーターの型 (入力または出力)、OLE DB 型、有効桁数、スケール、状態、および指定されたパラメーターの長さを設定します。 この属性は、OLE DB コンシューマー マクロ BEGIN_PARAM_MAP を挿入しています.END_PARAM_MAP します。 各メンバーをマークする、 **db_param**属性は、マップ、COLUMN_ENTRY の形式に 1 つのエントリを占有します。

**db_param**いずれかと組み合わせて使用は、 [db_table](../windows/db-table.md)または[db_command](../windows/db-command.md)属性。

コンパイラにクラスの名前は、コンシューマー属性プロバイダーでは、この属性をクラスに適用されます、ときに\_ *YourClassName*、アクセサーで*YourClassName*に付けた名前を指定します、クラス、さらに、コンパイラはというクラスを作成も*YourClassName*から派生した\_ *YourClassName*アクセサー。  クラス ビューでは、両方のクラスが表示されます。

## <a name="example"></a>例

次の例では、Northwind データベースに格納されている SalesbyYear プロシージャに基づくコマンド クラスを作成します。 ストアド プロシージャの最初のパラメーターを関連付けます、`m_RETURN_VALUE`変数と出力パラメーターとして定義されます。 最後の 2 つ (入力) パラメーターを関連付けます`m_Beginning_Date`と`m_Ending_Date`します。

次の例、`nOutput`出力パラメーターを持つ変数です。

```cpp
// db_param.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_source(L"my_connection_string"),
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")  
]
struct CSalesbyYear {
   DBSTATUS m_dwShippedDateStatus;
   DBSTATUS m_dwOrderIDStatus;
   DBSTATUS m_dwSubtotalStatus;
   DBSTATUS m_dwYearStatus;

   DBLENGTH m_dwShippedDateLength;
   DBLENGTH m_dwOrderIDLength;
   DBLENGTH m_dwSubtotalLength;
   DBLENGTH m_dwYearLength;

   // Bind columns
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];

   // Bind parameters
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**member、method、local|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)  
