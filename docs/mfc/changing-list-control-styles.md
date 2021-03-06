---
title: リスト コントロール スタイルの変更 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2fdb2bbb3681fab2bae42866df40d0ca363b7935
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676768"
---
# <a name="changing-list-control-styles"></a>リスト コントロール スタイルの変更
リスト コントロールのウィンドウ スタイルを変更することができます ([CListCtrl](../mfc/reference/clistctrl-class.md)) 作成した後、いつでもできます。 ウィンドウ スタイルを変更すると、コントロールを使用してビューの種類を変更します。 たとえば、エクスプ ローラーをエミュレートする可能性がありますを指定するメニュー項目またはツール バー ボタンのさまざまなビューでコントロールの切り替え: アイコン ビューやリスト ビュー。  
  
 たとえば、ユーザーは、メニュー項目を選択するときにへの呼び出しを作成できます[GetWindowLong](/windows/desktop/api/winuser/nf-winuser-getwindowlonga)コントロールの現在のスタイルを取得し、呼び出す[SetWindowLong](/windows/desktop/api/winuser/nf-winuser-setwindowlonga)スタイルをリセットします。 詳細については、次を参照してください。[を使用してリスト ビュー コントロール](/windows/desktop/Controls/using-list-view-controls)Windows SDK に含まれています。  
  
 使用可能なスタイルは、「[作成](../mfc/reference/clistctrl-class.md#create)です。 スタイル**LVS_ICON**、**だけ**、 **LVS_LIST**、および**LVS_REPORT**一覧の 4 つのコントロール ビューを指定します。  
  
## <a name="extended-styles"></a>拡張スタイル  
 リスト コントロールの標準的なスタイル、だけでなく、拡張スタイルと呼ばれる別のセットがあります。 これらのスタイルで説明した[リスト ビューのスタイルの拡張](/windows/desktop/Controls/extended-list-view-styles)Windows sdk には、さまざまなリスト コントロールの動作をカスタマイズできるさまざまな機能を提供します。 特定のスタイル (ホバー選択) などの動作を実装するへの呼び出しを行い[かざして](../mfc/reference/clistctrl-class.md#setextendedstyle)、必要なスタイルします。 次の例では、関数呼び出しを示しています。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  作業をホバー選択もが必要か**LVS_EX_ONECLICKACTIVATE**または**させる**オンにします。  
  
## <a name="see-also"></a>関連項目  
 [Clistctrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

