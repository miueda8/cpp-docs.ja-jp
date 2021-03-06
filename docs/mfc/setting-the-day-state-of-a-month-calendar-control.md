---
title: 予定表コントロールの月の日付状態の設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MCN_GETDAYSTATE
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d4254448e3f8f5a23acd9a303788fd13afb2f84
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950796"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>月間予定表コントロールの日付状態の設定
月間予定表コントロールの属性の 1 つは、月の日付ごとに、コントロールの日付状態と呼ばれます情報を格納する機能です。 この情報は、現在表示されている月の特定の日付を強調する使用されます。  
  
> [!NOTE]
>  `CMonthCalCtrl`オブジェクトは、1 日の状態情報を表示する MCS_DAYSTATE スタイルをいる必要があります。  
  
 1 日の状態情報は、32 ビットのデータ型として表される**月数**です。 各ビットを**月数**ビット フィールド (1 ~ 31) が 1 日に 1 か月の状態を表します。 対応する日付が表示されます、ビットがオンの場合で太字で表示します。それ以外の場合太字で表示されます。  
  
 月間予定表コントロールの日付状態を設定するための 2 つの方法: への呼び出しで明示的に[CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate)または MCN_GETDAYSTATE 通知メッセージを処理します。  
  
## <a name="handling-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE 通知メッセージの処理  
 MCN_GETDAYSTATE メッセージから送信される、コントロール以内に表示される日数を表示する方法を決定します。  
  
> [!NOTE]
>  コントロールが前月と翌月の表示の月に関してはキャッシュされるため、新しい月が選択されるたびにこの通知を受け取ります。  
  
 このメッセージを正しく処理するには、数か月 1 日状態される情報の数に対して要求されたの配列を初期化を決定する必要があります**月数**適切な値は、および関連する構造体のメンバーの初期化を含む構造体新しい情報。 詳細な手順では、次の手順では、あると想定する`CMonthCalCtrl`と呼ばれるオブジェクト*示します*と配列の**月数**オブジェクト、 *mdState*.  
  
#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE 通知メッセージを処理するには  
  
1.  MCN_GETDAYSTATE メッセージの通知ハンドラーを追加、プロパティ ウィンドウを使用して、*示します*オブジェクト (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。  
  
2.  ハンドラーの本体では、次のコードを追加します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]  
  
     例では、変換、 *pNMHDR* 、適切な型へのポインターが要求されている情報の月の数を決定し (`pDayState->cDayState`)。 毎月、現在のビット フィールドの (`pDayState->prgDayState[i]`)、し、必要とゼロに初期化されます (ここでは、各月の 15 日) の日付が設定されます。  
  
## <a name="see-also"></a>関連項目  
 [CMonthCalCtrl の使い方](../mfc/using-cmonthcalctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

