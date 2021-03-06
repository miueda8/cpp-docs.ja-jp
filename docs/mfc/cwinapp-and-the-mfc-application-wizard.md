---
title: CWinApp および MFC アプリケーション ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59fcd3f00fb8998cf90c88d574b9d22051cb4305
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687785"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp および MFC アプリケーション ウィザード
MFC アプリケーション ウィザードでは、アプリケーションのクラスから派生した宣言、スケルトン アプリケーションの作成時に[CWinApp](../mfc/reference/cwinapp-class.md)します。 MFC アプリケーション ウィザードでは、次の項目を格納する実装ファイルも生成されます。  
  
-   アプリケーションのクラスのメッセージ マップです。  
  
-   空のクラスのコンス トラクターです。  
  
-   クラスのオブジェクトのみを宣言する変数。  
  
-   標準的な実装、`InitInstance`メンバー関数。  
  
 アプリケーションのクラスは、プロジェクトのヘッダーとメイン ソース ファイルに配置されます。 クラスと作成されるファイルの名前は、MFC アプリケーション ウィザードで、指定したプロジェクトの名前に基づきます。 これらのクラスのコードを表示する最も簡単な方法は使用[クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)します。  
  
 標準的な実装とメッセージ マップの指定は多くの目的で、適切であるが、必要に応じて変更することができます。 これらの実装の中で最も興味深いは、`InitInstance`メンバー関数。 スケルトンの実装にコードを追加する通常、`InitInstance`します。  
  
## <a name="see-also"></a>関連項目  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)   
 [オーバーライド可能な CWinApp のメンバー関数します。](../mfc/overridable-cwinapp-member-functions.md)   
 [CWinApp のその他のサービス](../mfc/special-cwinapp-services.md)

