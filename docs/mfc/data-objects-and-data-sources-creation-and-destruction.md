---
title: 'データ オブジェクトとデータ ソース: 作成と破棄 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- destroying data objects [MFC]
- object creation [MFC], data source objects
- data sources [MFC], and data objects
- data source objects [MFC], creating
- destruction [MFC], data sources
- data source objects [MFC], destroying
- data objects [MFC], creating
- data objects [MFC], destroying
- data sources [MFC], role
- data sources [MFC], destroying
- destruction [MFC], data objects
- data sources [MFC], creating
ms.assetid: ac216d54-3ca5-4ce7-850d-cd1f6a90d4f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90143b919fde02a95df81d41845d8ecc671ced0d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931877"
---
# <a name="data-objects-and-data-sources-creation-and-destruction"></a>データ オブジェクトとデータ ソース : 作成と破棄
アーティクルの説明に従って[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)、データ オブジェクトとデータ ソースは、データ転送の両側を表します。 ここでは、データ転送を正しく実行するために、これらのオブジェクトとソースをいつ作成し、いつ破棄するかについて説明します。  
  
-   [データ オブジェクトの作成](#_core_creating_data_objects)  
  
-   [データ オブジェクトの破棄](#_core_destroying_data_objects)  
  
-   [データ ソースの作成](#_core_creating_data_sources)  
  
-   [データ ソースの破棄](#_core_destroying_data_sources)  
  
##  <a name="_core_creating_data_objects"></a> データ オブジェクトの作成  
 データ オブジェクトは、転送先アプリケーション (クライアントまたはサーバー) で使用されます。 転送先アプリケーションのデータ オブジェクトは、転送元アプリケーションと転送先アプリケーション間の接続の片端となります。 転送先アプリケーションのデータ オブジェクトは、データ ソース内のデータへのアクセスと対話に使用されます。  
  
 データ オブジェクトが必要な状況は、一般的に 2 つあります。 1 つ目は、ドラッグ アンド ドロップを使用してアプリケーションにデータをドロップする場合です。 2 つ目は、[編集] メニューの [貼り付け] または [形式を選択して貼り付け] を選択する場合です。  
  
 ドラッグ アンド ドロップの場合、データ オブジェクトを作成する必要はありません。 既存のデータ オブジェクトへのポインターが `OnDrop` 関数に渡されます。 このデータ オブジェクトは、ドラッグ アンド ドロップ操作の一環としてフレームワークによって作成され、さらにフレームワークによって破棄されます。 貼り付けが別の方法で行われる場合は、必ずしもこれが当てはまるとは限りません。 詳細については、次を参照してください。[データ オブジェクトの破棄](#_core_destroying_data_objects)です。  
  
 アプリケーションで [貼り付け] または [形式を選択して貼り付け] 操作を実行する場合は、`COleDataObject` オブジェクトを作成し、その `AttachClipboard` メンバー関数を呼び出す必要があります。 これにより、データ オブジェクトはクリップボード上のデータと関連付けられます。 その後、貼り付け関数でこのデータ オブジェクトを使用できます。  
  
##  <a name="_core_destroying_data_objects"></a> データ オブジェクトの破棄  
 説明した手法に従う場合[データ オブジェクトの作成](#_core_creating_data_objects)、データ転送の一環としては、データ オブジェクトを破棄します。 貼り付け関数で作成されたデータ オブジェクトは、関数から制御が戻るときに、MFC によって破棄されます。  
  
 貼り付け操作を別の方法で処理する場合は、貼り付け操作が完了した後にデータ オブジェクトが破棄されるようにしてください。 データ オブジェクトが破棄されるまで、アプリケーションではデータをクリップボードに正常にコピーすることができません。  
  
##  <a name="_core_creating_data_sources"></a> データ ソースの作成  
 データ ソースは、データ転送の送信元によって使用されます。この送信元は、データ転送のクライアント側の場合もサーバー側の場合もあります。 転送元アプリケーションのデータ ソースは、転送元アプリケーションと転送先アプリケーション間の接続の片端となります。 転送先アプリケーションのデータ オブジェクトは、データ ソース内のデータとの対話に使用されます。  
  
 データ ソースは、アプリケーションでデータをクリップボードにコピーすることが必要な場合に作成されます。 一般的なシナリオは次のようになります。  
  
1.  ユーザーがいくつかのデータを選択します。  
  
2.  ユーザーが選択した**コピー** (または**切り取り**) から、**編集**メニューか、ドラッグ アンド ドロップ操作を開始します。  
  
3.  プログラムの仕様に応じて、アプリケーションは `COleDataSource` オブジェクトを作成するか、`COleDataSource` から派生したクラスからオブジェクトを作成します。  
  
4.  選択したデータは、`COleDataSource::CacheData` グループまたは `COleDataSource::DelayRenderData` グループ内の関数のいずれかを呼び出すと、データ ソースに挿入されます。  
  
5.  アプリケーションは、手順 3. で作成したオブジェクトに属する `SetClipboard` メンバー関数 (またはドラッグ アンド ドロップ操作の場合は `DoDragDrop` メンバー関数) を呼び出します。  
  
6.  この場合、**切り取り**操作または`DoDragDrop`を返します**行った**、手順 1. で選択したデータは、ドキュメントから削除します。  
  
 このシナリオは、MFC OLE サンプルで実装されて[OCLIENT](../visual-cpp-samples.md)と[HIERSVR](../visual-cpp-samples.md)です。 `GetClipboardData` 関数と `OnGetClipboardData` 関数を除くすべてについて、各アプリケーションの `CView` から派生したクラスのソースを確認してください。 これらの 2 つの関数は、`COleClientItem` または `COleServerItem` から派生したクラスの実装に含まれています。 これらのサンプル プログラムでは、これらの概念を実装する方法の良い例を示しています。  
  
 さらに、ドラッグ アンド ドロップ操作の既定の動作を変更する場合にも、`COleDataSource` オブジェクトの作成が必要になることがあります。 詳細については、次を参照してください。、[ドラッグ アンド ドロップ: カスタマイズ](../mfc/drag-and-drop-customizing.md)資料です。  
  
##  <a name="_core_destroying_data_sources"></a> データ ソースの破棄  
 データ ソースは、現在データ ソースを管理しているアプリケーションによって破棄する必要があります。 OLE にデータ ソースを配信する場合、呼び出しなど[された](../mfc/reference/coledatasource-class.md#dodragdrop)、呼び出す必要がある`pDataSrc->InternalRelease`です。 例えば:  
  
 [!code-cpp[NVC_MFCListView#1](../atl/reference/codesnippet/cpp/data-objects-and-data-sources-creation-and-destruction_1.cpp)]  
  
 OLE にデータ ソースを渡していない場合は、通常の C++ オブジェクトの場合と同様、データ ソースを破棄します。  
  
 詳細については、次を参照してください。[ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)、[クリップボード](../mfc/clipboard.md)、および[を操作するデータ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-manipulation.md)です。  
  
## <a name="see-also"></a>関連項目  
 [データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject クラス](../mfc/reference/coledataobject-class.md)   
 [COleDataSource クラス](../mfc/reference/coledatasource-class.md)
