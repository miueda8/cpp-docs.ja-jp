---
title: 純粋仮想の実装 | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afce516f2718a76658846ed4f992aeabff75330b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33328027"
---
# <a name="implement-pure-virtuals"></a>純粋仮想の実装
**機能:** クラスですべての純粋仮想を実装するために必要なコードをすぐに生成できます。 

**条件:** 純粋仮想関数のクラスからの継承が望まれるとき。  

**理由:** すべての純粋仮想関数は 1 つずつ手動で実装できますが、この機能ではすべてのメソッド シグネチャが自動的に生成されます。

**方法:**

1. 基底クラスの純粋仮想関数を実装するクラスにテキストまたはマウス カーソルを置きます。

   ![強調表示されたコード](images/virtuals_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **キーボード**
     * **Ctrl + .** キーを押して、 **[クイック アクションとリファクタリング]** メニューをトリガーし、コンテキスト メニューから **[Implement all Pure Virtuals for class '*ClassName*’]\(クラス 'ClassName' のすべての純粋仮想を実装\)** を選択します。*ClassName* は、選択されたクラスの名前になります。
   * **マウス**
     * 右クリックして **[クイック アクションとリファクタリング]** メニューを選択し、コンテキスト メニューから **[Implement all Pure Virtuals for class '*ClassName*']\(クラス 'ClassName' のすべての純粋仮想を実装\)** を選択します。*ClassName* は、選択されたクラスの名前になります。

1. 純粋仮想メソッドのシグネチャが自動的に作成され、実装する準備が整います。

   ![純粋仮想の実装の結果](images/virtuals_result.png)
