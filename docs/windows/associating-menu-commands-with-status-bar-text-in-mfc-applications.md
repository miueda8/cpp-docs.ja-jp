---
title: MFC アプリケーションのステータス バーのテキストとメニュー コマンドの関連付け |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- status bars, associating menu items
- menus, status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d9cb5e57d6c7020e0b89104dac87fa3cd08ea023
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583702"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>メニュー コマンドと MFC アプリケーションのステータス バーのテキストとの関連付け

アプリケーションでは、ユーザーが選択する各メニュー コマンドに対して、説明のテキストを表示できます。 各メニュー コマンドを使用するテキスト文字列を割り当てることで、これを行う、**プロンプト**プロパティ、**プロパティ**ウィンドウ。 コマンドと同じ ID を持つ [ストリング テーブル](../windows/string-editor.md) に文字列がある場合、MFC アプリケーションでは、ユーザーがマウス ポインターをメニュー項目の上に置くと、実行中のアプリケーションのステータス バーにこの文字列リソースが自動的に表示されます。

### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>メニュー コマンドをステータス バーのテキスト文字列に関連付けるには

1. **メニュー** エディターで、メニュー コマンドを選択します。

2. [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で、関連付けるステータス バーのテキストを **[プロンプト]** ボックスに入力します。

## <a name="requirements"></a>要件

MFC

## <a name="see-also"></a>関連項目

[文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
[メニューへのコマンドの追加](../windows/adding-commands-to-a-menu.md)  
[メニュー エディター](../windows/menu-editor.md)