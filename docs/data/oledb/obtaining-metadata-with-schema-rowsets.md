---
title: スキーマ行セットのメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets, getting OLE DB provider metadata
- OLE DB consumer templates, getting provider metadata
- metadata, getting (OLE DB Templates)
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7b131119f5f6207feccec3c683a470a8b099de12
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207843"
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>スキーマ行セットを使用したメタデータの取得
プロバイダー、行セット、テーブル、列、またはその他のデータベース情報に関する情報を行セットを開かずに取得することが必要な場合があります。 データベース構造に関するデータはメタデータと呼ばれます。メタデータはさまざまな方法で取得できます。 1 つは、スキーマ行セットを使用する方法です。  
  
 OLE DB テンプレートは、一連のスキーマ情報を取得するためのクラスを提供します。これらのクラスは、定義済みのスキーマ行セットを作成し、記載されて[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)します。  
  
> [!NOTE]
>  OLAP を使用していて、行セットの一部がスキーマ行セット クラスでサポートされていない場合 (列数が変数の場合など) は、`CManualAccessor` または `CDynamicAccessor` の使用を検討する必要があります。 列をスクロールし、case ステートメントを使用して、各列で可能なデータ型を処理できます。  
  
## <a name="catalogschema-model"></a>カタログ/スキーマ モデル  
 ANSI SQL はデータ ストアのカタログ/スキーマ モデルを定義しています。OLE DB はこのモデルを使用します。 このモデルでは、カタログ (データベース) にスキーマが含まれ、スキーマにテーブルが含まれます。  
  
-   **カタログ**カタログは、データベースに別の名前。 これは、関連するスキーマのコレクションです。 指定したデータ ソースに属するカタログ (データベース) を一覧表示する[CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md)します。 多くのデータベースにはカタログが 1 つしかないため、メタデータは、単純にスキーマ情報と呼ばれることがあります。  
  
-   **スキーマ**スキーマが所有しているまたは特定のユーザーによって作成されたデータベース オブジェクトのコレクション。 特定のユーザーが所有するスキーマを一覧表示する[CSchemata](../../data/oledb/cschemata-cschematainfo.md)します。  
  
     Microsoft SQL Server と ODBC 2.x の用語では、スキーマは所有者です (たとえば、dbo は一般的なスキーマ名)。 また、SQL Server は一連のテーブルでメタデータを格納します。 1 つのテーブルには、すべてのテーブルの一覧が含まれていますし、別のテーブルには、すべての列の一覧が含まれています。 Microsoft Access データベースにはスキーマに相当するものはありません。  
  
-   **テーブル**テーブルは、特定の順序で分類された列のコレクション。 指定したカタログ (データベース) とそれらのテーブルに関する情報で定義されているテーブルを一覧表示する[CTables](../../data/oledb/ctables-ctableinfo.md))。  
  
## <a name="restrictions"></a>制約  
 スキーマ情報を照会するときに、制約を使用して、目的の情報の種類を指定できます。 制約は、クエリのフィルターまたは修飾子として考えることができます。 たとえば、次のクエリについて考えます。  
  
```sql  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
 このクエリでは、`l_name` が制約です。 これは制約が 1 つしかない単純な例です。スキーマ行セット クラスは複数の制約をサポートします。  
  
 [スキーマ行セット typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)他の行セットと同じようにスキーマ行セットをインスタンス化して開くことによってアクセスできるように、すべての OLE DB スキーマ行セットをカプセル化します。 たとえば、typedef クラス[CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)として定義されます。  
  
```cpp  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md)クラスは制約がサポートを提供します。 スキーマ行セットのインスタンスを作成した後で呼び出す[crestrictions::open](../../data/oledb/crestrictions-open.md)します。 このメソッドは、指定された制約に基づいて結果セットを返します。  
  
 制限を指定するを参照してください[付録 B スキーマ行セット](/previous-versions/windows/desktop/ms712921\(v=vs.85\))し使用している行セットを検索します。 たとえば、`CColumns`に対応する、 [COLUMNS 行セット](/previous-versions/windows/desktop/ms723052\(v%3dvs.85\)); そのトピックでは、COLUMNS 行セットの制限列: TABLE_CATALOG、table_schema、TABLE_NAME、COLUMN_NAME します。 制約を指定するときは、この順序に従う必要があります。  
  
 そのため、たとえば、テーブル名で制限する場合は、TABLE_NAME が 3 つ目の制限列を呼び出して`Open`、次の例に示すように、3 番目の制限パラメーターとして目的のテーブル名を指定します。  
  
#### <a name="to-use-schema-rowsets"></a>スキーマ行セットを使用するには  
  
1.  Atldbsch.h ヘッダー ファイルをインクルードする必要があります (コンシューマー サポートでも Atldbcli.h が必要です)。  
  
2.  コンシューマーまたはドキュメントのヘッダー ファイル内のスキーマ行セット オブジェクトをインスタンス化します。 テーブルの情報を実行する場合に、宣言、`CTables`オブジェクト。 列情報を実行する場合に、宣言、`CColumns`オブジェクト。 authors テーブルの列を取得する方法の例を次に示します。  
  
    ```cpp  
    CDataSource ds;  
    ds.Open();  
    CSession ss;  
    ss.Open();  
    CColumns ColumnSchemaRowset;  
    // TABLE_NAME is the third restriction column, so  
    // specify "authors" as the third restriction parameter:  
    hr = ColumnSchemaRowset.Open(ss, NULL, NULL, "authors");  
    hr = ColumnSchemaRowset.MoveFirst();  
    while (hr == S_OK)  
    {  
       hr = ColumnSchemaRowset.MoveNext();  
    }  
    ```  
  
3.  情報をフェッチするには、スキーマ行セット オブジェクトの適切なデータ メンバーにアクセスします。たとえば、`ColumnSchemaRowset.m_szColumnName` にアクセスします。 これは COLUMN_NAME に対応します。 各データ メンバーに対応する OLE DB 列を表示するには、次を参照してください。 [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)します。  
  
 OLE DB テンプレートのスキーマ行セットの参照の typedef クラスが提供されている (を参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md))。  
  
 制限列を含め、OLE DB スキーマ行セットの詳細については、次を参照してください。[付録 b スキーマ行セット](/previous-versions/windows/desktop/ms712921\(v=vs.85\))OLE DB プログラマーズ リファレンス。  
  
 スキーマ行セット クラスを使用する方法のより複雑な例については、次を参照してください。、 [CatDB](https://github.com/Microsoft/VCSamples)と[DBViewer](https://github.com/Microsoft/VCSamples)サンプル。  
  
 スキーマ行セット プロバイダーのサポートについては、次を参照してください。[スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)します。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)