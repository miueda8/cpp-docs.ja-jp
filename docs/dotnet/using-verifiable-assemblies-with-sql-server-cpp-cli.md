---
title: SQL Server で検証可能なアセンブリの使用 (C +/cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 65a3c4da1664e34e40e0961655c130f320efb17b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690704"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>SQL Server での確認可能なアセンブリの使用 (C++/CLI)
ダイナミック リンク ライブラリ (Dll) としてパッケージ化、拡張ストアド プロシージャは、Visual C で開発した関数を使用して SQL Server の機能を拡張する手段を提供します。 拡張ストアド プロシージャは Dll 内の関数として実装されます。 拡張ストアド プロシージャも定義するだけでなく、機能[ユーザー定義型](../cpp/classes-and-structs-cpp.md)と集計関数 (SUM、AVG など)。  
  
 クライアントは、拡張ストアド プロシージャを実行するとき、SQL Server DLL を検索は、拡張ストアド プロシージャに関連付けられているし、DLL を読み込みます。 SQL Server では、要求された拡張ストアド プロシージャを呼び出すし、指定したセキュリティ コンテキストで実行します。 拡張にストアド パスの結果が設定され、サーバーにパラメーターを返しますのプロシージャをします。  
  
 SQL Server TRANSACT-SQL (T-SQL) は、SQL Server に検証可能なアセンブリをインストールすることを許可する拡張機能を提供します。 SQL Server のアクセス許可セットでは、次のセキュリティ レベルで、セキュリティ コンテキストを指定します。  
  
-   無制限のモード: コードを各自の責任で実行コードはタイプ セーフではありません。  
  
-   セーフ モード: 検証可能なタイプ セーフなコードの実行/clr:safe と共にコンパイル。  
  
 セーフ モードでは、実行されるアセンブリにタイプセーフにする必要があります。  
  
 作成しを SQL Server に検証可能なアセンブリを読み込むようアセンブリの作成と DROP ASSEMBLY は、TRANSACT-SQL コマンドを使用します。  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 PERMISSION_SET コマンドでは、セキュリティ コンテキストを指定し、無制限、SAFE、または拡張値を持つことができます。  
  
 さらに、クラスでメソッド名にバインドする関数の作成コマンドを使用できます。  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## <a name="example"></a>例  
 次の SQL スクリプト (たとえば、名前付き"MyScript.sql") は、SQL Server にアセンブリを読み込み、クラスのメソッドを使用できるように。  
  
```  
-- Create assembly without external access  
drop assembly stockNoEA  
go  
create assembly stockNoEA  
from   
'c:\stockNoEA.dll'  
with permission_set safe  
  
-- Create function on assembly with no external access  
drop function GetQuoteNoEA  
go  
create function GetQuoteNoEA(@sym nvarchar(10))  
returns real  
external name stockNoEA:StockQuotes::GetQuote  
go  
  
-- To call the function  
select dbo.GetQuoteNoEA('MSFT')  
go  
```  
  
 SQL スクリプトは、SQL クエリ アナライザーまたは sqlcmd.exe ユーティリティを使用したコマンドラインで、対話的に実行できます。 次のコマンド ライン MyServer に接続する、既定のデータベースを使用して、信頼関係接続を使用して、MyScript.sql、入出力 MyResult.txt します。  
  
```  
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt  
```  
  
## <a name="see-also"></a>関連項目  
 [方法:/clr:safe に移行する (C +/cli CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [クラスと構造体](../cpp/classes-and-structs-cpp.md)