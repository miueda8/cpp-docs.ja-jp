---
title: IDispEventImpl (ATL) の使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38ac64a99c3523f174c62c9788aeab867aa8758b
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848929"
---
# <a name="using-idispeventimpl"></a>IDispEventImpl の使用
使用する場合`IDispEventImpl`イベントを処理する必要があります。  
  
-   クラスを派生[IDispEventImpl](../atl/reference/idispeventimpl-class.md)します。  
  
-   クラスにイベント シンク マップを追加します。  
  
-   イベント シンク マップを使用するエントリを追加、 [SINK_ENTRY](reference/composite-control-macros.md#sink_entry)または[SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)マクロ。  
  
-   処理したいメソッドを実装します。  
  
-   イベント ソースをアドバイズことをお勧めします.  
  
## <a name="example"></a>例  
 次の例を処理する方法を示しています、`DocumentChange`によって Word のイベントが発生した**アプリケーション**オブジェクト。 このイベントは、メソッドとしてで定義されている、`ApplicationEvents`ディスパッチ インターフェイス。  
  
 例は、[コード](../visual-cpp-samples.md)します。  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 この例では`#import`Word のタイプ ライブラリから必要なヘッダー ファイルを生成します。 Word の他のバージョンでこの例を使用する場合は、正しい mso dll ファイルを指定する必要があります。 たとえば、Office 2000 mso9.dll を提供し、OfficeXP が mso.dll を提供します。 このコードは、stdafx.h から簡素化します。  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]  
  
 NotSoSimple.h に次のコードが表示されます。 関連するコードは、コメントでされています。  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]  
  
## <a name="see-also"></a>関連項目  
 [イベント処理](../atl/event-handling-and-atl.md)   
 [コード](../visual-cpp-samples.md)

