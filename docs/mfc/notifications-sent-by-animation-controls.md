---
title: アニメーション コントロールによる通知の送信 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7aff43577a4b1aa55fc0725ba4753228e334000
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43199662"
---
# <a name="notifications-sent-by-animation-controls"></a>アニメーション コントロールによる通知の送信
アニメーション コントロール ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) 2 つのさまざまな種類の通知メッセージを送信します。 形式で、通知が送信[WM_COMMAND](/windows/desktop/menurc/wm-command)メッセージ。  
  
 [ACN_START](/windows/desktop/Controls/acn-start)アニメーション コントロールのクリップの再生が開始されたときにメッセージを送信します。 [ACN_STOP](/windows/desktop/Controls/acn-stop)アニメーション コントロールが完了またはクリップの再生を停止したときにメッセージが送信されます。  
  
## <a name="see-also"></a>関連項目  
 [Canimatectrl の使い方](../mfc/using-canimatectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

