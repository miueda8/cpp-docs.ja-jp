---
title: リッチ エディット コントロールでの操作を Stream |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f418156fb5be4837bc0dbe9b05b3ad26d7ac02dd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196859"
---
# <a name="stream-operations-in-rich-edit-controls"></a>リッチ エディット コントロールでのストリーム操作
リッチ エディット コントロールの内外にデータを転送するストリームを使用することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 ストリームがによって定義されている、 [EDITSTREAM](/windows/desktop/api/richedit/ns-richedit-_editstream)構造体は、バッファー、およびアプリケーション定義のコールバック関数を指定します。  
  
 読み取るデータをリッチ エディット コントロール (つまり、内のデータ ストリーム) を使用して、 [StreamIn](../mfc/reference/cricheditctrl-class.md#streamin)メンバー関数。 コントロールでは、バッファーにデータの一部を転送するたびに、アプリケーション定義のコールバック関数を繰り返し呼び出します。  
  
 コントロールを編集しているの豊富な内容を保存する (つまり、送信データ ストリーム) を使用することができます、 [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout)メンバー関数。 コントロールでは、繰り返しをバッファーに書き込みます、アプリケーション定義のコールバック関数を呼び出します。 呼び出しごとには、コールバック関数は、バッファーの内容を保存します。  
  
## <a name="see-also"></a>関連項目  
 [Cricheditctrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

