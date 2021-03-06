---
title: MFC COM |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MFC COM (MFC)
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e8c3af361e1ffb5928132727fa124f03a99e81e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205650"
---
# <a name="mfc-com"></a>MFC COM
Active Template Library (ATL) のほとんどは設計されています。 COM をサポートする MFC のサブセットがに設計された COM プログラミングします。 このセクションのトピックには、COM の MFC のサポートがについて説明します  
  
 Active テクノロジ (など、ActiveX コントロール、Active ドキュメント コンテインメント、OLE、およびなど) が使用する言語に関係なく、ネットワーク環境で互いと対話するのにソフトウェア コンポーネントを有効にするのにコンポーネント オブジェクト モデル (COM) を使用します。作成されます。 Active テクノロジは、デスクトップまたはインターネット上で実行されるアプリケーションの作成に使用できます。 詳細については、次を参照してください。 [COM の概要](../atl/introduction-to-com.md)または[、コンポーネント オブジェクト モデル](/windows/desktop/com/the-component-object-model)します。  
  
 アクティブな技術には、次を含む、クライアントとサーバーの両方のテクノロジがあります。  
  
-   [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)、MFC バージョン 4.2 ではサポートでき、後で、ユーザーを表示する[active ドキュメント](../mfc/active-documents.md)(Microsoft Excel または Word ファイル) などのドキュメントのネイティブ インターフェイス全体をアクティブ化アプリケーションの全体のクライアント領域で、 [active ドキュメント コンテナー](../mfc/active-document-containers.md) Microsoft Internet Explorer と Microsoft Office バインダーなど。 によって提供されるドキュメントはときに、コンテナーが、クライアントとして動作[active ドキュメント サーバー](../mfc/active-document-servers.md)します。 インターネット アプリケーションでアクティブなドキュメントの使用に関する詳細については、次を参照してください。: [、インターネット上の Active ドキュメント](../mfc/active-documents-on-the-internet.md)します。  
  
-   ActiveX コントロールは、Web サイトなどのコンテナーで使用できる対話型のオブジェクトです。 ActiveX コントロールの詳細についてを参照してください。  
  
    -   [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)  
  
    -   [インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)  
  
    -   [概要: インターネット](../mfc/mfc-internet-programming-basics.md)  
  
    -   [インターネットで使用する既存の ActiveX コントロールのアップグレードします。](../mfc/upgrading-an-existing-activex-control.md)  
  
    -   [ActiveX コントロールのデバッグ](/visualstudio/debugger/how-to-debug-an-activex-control)  
  
-   アクティブ スクリプトからブラウザーまたはサーバーの 1 つ以上の ActiveX コントロールの統合の動作を制御します。 アクティブ スクリプトの詳細については、次を参照してください。 [、インターネット上の Active テクノロジ](../mfc/active-technology-on-the-internet.md)します。  
  
-   [Automation](../mfc/automation.md) (以前の OLE オートメーション) 1 つのアプリケーションを別のアプリケーションで実装されているオブジェクトを操作する"オブジェクトを公開したり"操作できるようにすることになります。  
  
     オブジェクトの自動化には、ローカルまたはリモート (上に別のコンピューターをネットワーク経由でアクセスできる) があります。 OLE オブジェクトと COM オブジェクトは、どちらもオートメーションを利用できます。  
  
-   このセクションの例については、MFC を使用する COM コンポーネントを作成する方法に関する情報も提供します[コネクション ポイント](../mfc/connection-points.md)します。  
  
 まだと呼ばれる OLE active テクノロジを今すぐと呼ばれるものと比較の詳細については、トピックを参照してください。 [OLE](../mfc/ole-in-mfc.md)します。  
  
 また、サポート技術情報記事 Q248019 を参照してください: HOWTO: ようにサーバー ビジー状態 ダイアログ ボックスから表示中に、時間のかかる COM 操作。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)  
  
 [オートメーション](../mfc/automation.md)  
  
 [接続ポイント](../mfc/connection-points.md)  
  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)

