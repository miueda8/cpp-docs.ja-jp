---
title: プロジェクトのビルドの警告 PRJ0049 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 726294f420000ab1d1b98be72d310dfcbfcd04c0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591885"
---
# <a name="project-build-warning-prj0049"></a>プロジェクト ビルドの警告 PRJ0049
参照先の対象 '\<参照 >'.NET Framework が必要です\<ごと > とは、このプロジェクトのターゲット フレームワークで実行できません  
  
 Visual Studio 2008 を使用して作成されたアプリケーションは、ターゲットが .NET Framework のバージョンを指定できます。 アセンブリまたは .NET Framework には、対象のバージョンより後のバージョンに依存しているプロジェクトへの参照を追加する場合は、コンパイル時にこの警告が表示されます。  
  
### <a name="to-correct-this-warning"></a>この警告を解決するには  
  
1.  次のいずれかを選択します。  
  
    -   プロジェクトの対象となるフレームワークを変更**プロパティ ページ** ダイアログ ボックスのすべての参照先アセンブリとプロジェクトの最小限の framework バージョン以降できるようにします。 詳細については、次を参照してください。[参照の追加](../../ide/adding-references-in-visual-cpp-projects.md)します。  
  
    -   アセンブリまたは最小限の framework バージョンが、対象のフレームワークよりも後のプロジェクトへの参照を削除します。 これらの項目は、プロジェクトの警告アイコンでマークは**プロパティ ページ**します。  
  
## <a name="see-also"></a>関連項目  
 [プロジェクト ビルド エラーと警告 (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)