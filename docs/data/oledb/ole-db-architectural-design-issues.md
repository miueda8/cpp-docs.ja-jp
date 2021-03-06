---
title: OLE DB アーキテクチャのデザインの問題 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, application design considerations
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b0a5c568a774d0aed05d702454664e653989401
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676837"
---
# <a name="ole-db-architectural-design-issues"></a>OLE DB アーキテクチャのデザインの問題
OLE DB アプリケーションを開始する前に、次の問題を考慮してください。  
  
 **OLE DB アプリケーションを記述するプログラミング実装を使用するか。**  
 Microsoft には、これを実現するいくつかのライブラリが用意されています。 OLE DB テンプレート ライブラリを、OLE DB 属性、および OLE DB SDK では、生の OLE DB インターフェイス。 さらでは、ウィザード ・、プログラムを記述する際に役立つことがあります。 これらの実装については、後述[OLE DB テンプレート、属性、およびその他の実装](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md)します。  
  
 **独自のプロバイダーを記述する必要がありますか。**  
 ほとんどの開発者は、独自のプロバイダーを作成する必要はありません。 Microsoft では、いくつかのプロバイダーを提供します。 (たとえば、コンシューマーを ATL OLE DB コンシューマー ウィザードを使用してプロジェクトに追加する場合)、データ接続を作成するたびに、**データ リンク プロパティ** ダイアログ ボックスには、システムに登録されているすべての利用可能なプロバイダーが一覧表示されます。 これらのプロバイダーのいずれかが、独自のデータ ストアとデータ アクセス アプリケーションの適切な場合は、これらのいずれかは、最も簡単な操作を行います。 ただし、データ ストアがこれらのカテゴリのいずれかにも収まらない場合、独自のプロバイダーを作成する必要あります。 プロバイダーを作成する方法の詳細については、次を参照してください。 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)します。  
  
 **コンシューマーに必要なレベルのサポート**  
 一部のコンシューマーは、非常に基本的です;他のユーザーは、非常に複雑になることができます。 OLE DB オブジェクトの機能は、プロパティによって指定されます。 ATL OLE DB コンシューマー ウィザードを使用してプロバイダーを作成するには、コンシューマーまたはデータベース プロバイダーのウィザードを作成するときに、標準的な一連の機能を提供する適切なオブジェクトのプロパティを設定します。 ただし、ウィザードで生成されたコンシューマーまたはプロバイダーのクラスをサポートしていないすべての実行に必要な場合でこれらのクラス インターフェイスを参照してください、 [OLE DB テンプレート ライブラリ](../../data/oledb/ole-db-templates.md)します。 これらのインターフェイスは、使いやすくために余分な実装を提供する、生の OLE DB インターフェイスをラップします。  
  
 など、行セット内のデータを更新するウィザードを使用して、コンシューマーの作成時に指定されていない場合は、する機能、ファクトの後に設定して指定できます、`DBPROP_IRowsetChange`と`DBPROP_UPDATABILITY`コマンド オブジェクトのプロパティ。 次に、行セットが作成されたときに、`IRowsetChange`インターフェイス。  
  
 **別のデータ アクセス テクノロジ (ADO、ODBC、または DAO) を使用して以前のコードを使用していますか。**  
 (コンポーネントの OLE DB と ADO のコンポーネントを使用して、OLE DB の ODBC コードを移行する) などのテクノロジの組み合わせについて、すべての状況を説明することは、Visual C ドキュメントの範囲外です。 ただし、さまざまなシナリオをカバーする多くの記事は、次の Microsoft Web サイトで使用できます。  
  
-   [Microsoft ヘルプおよびサポート](https://support.microsoft.com/)  
  
-   [Microsoft データ アクセス技術記事の概要](https://msdn.microsoft.com/en-us/library/ms810811.aspx)  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)   
 [OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)