---
title: ツリー コントロール項目のラベル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e016093e2dcde68fcc01691c4877841d648321fb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207465"
---
# <a name="tree-control-item-labels"></a>ツリー コントロールの項目のラベル
ツリー コントロールに項目を追加するときに通常、項目のラベルのテキストを指定する ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))。 `InsertItem`メンバー関数に渡すことができます、 [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema)ラベルのテキストを含む文字列を含む、アイテムのプロパティを定義する構造体。 `InsertItem` パラメーターのさまざまな組み合わせで呼び出すことができるいくつかのオーバー ロードがあります。  
  
 ツリー コントロールは、各項目を格納するためにメモリを割り当てます項目のラベルのテキストは、このメモリの大部分を占有します。 アプリケーションにツリー コントロール内の文字列のコピーが保持している場合は、指定することで、コントロールのメモリ要件を減らすことができます、**保持するようにする**値、 *pszText* のメンバー`TV_ITEM`または*lpszItem*ツリー コントロールに実際の文字列を渡すのではなくパラメーター。 使用して**保持するようにする**ツリー コントロールの項目が再描画する必要があるたびに、アプリケーションから、項目のラベルのテキストを取得します。 テキストを取得するには、ツリー コントロールの送信、 [TVN_GETDISPINFO](/windows/desktop/Controls/tvn-getdispinfo)のアドレスを含む通知メッセージを[NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa)構造体。 構造体の適切なメンバーを設定して応答する必要があります。  
  
 ツリー コントロールでは、ツリーのコントロールを作成するプロセスのヒープから割り当てられたメモリを使用します。 ツリー コントロールで項目の最大数は、ヒープの使用可能なメモリの量に基づきます。 各項目は 64 バイトになります。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

