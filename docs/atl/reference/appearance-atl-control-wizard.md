---
title: 外観、ATL コントロール ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b3db7fbcf190aa2dda05cabd2d1553824fb076e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194728"
---
# <a name="appearance-atl-control-wizard"></a>外観、ATL コントロール ウィザード
「検索結果」の概要をここに挿入します。  
  
 コントロールの追加のユーザーの要素のオプションを識別するために、ウィザードのこのページを使用します。 このページとして識別されるコントロールの使用可能な**標準コントロール****コントロール型**上、[オプション、ATL コントロール ウィザード](../../atl/reference/options-atl-control-wizard.md)ページ。  
  
## <a name="uielement-list"></a>UIElement の一覧  
**状態の表示**  
コンテナー内のコントロールの外観を設定します。  
  
 -   **非透過**: VIEWSTATUS_OPAQUE のビットを設定、[な VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus)列挙体を描画するコントロール全体の四角形が渡される、 [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw)メソッド。 コントロールが完全に不透明が表示され、コントロールの境界の背後にあるコンテナーを示しています。      
      
        この設定によりより迅速にコントロールを描画するコンテナー。 このオプションが選択されていない場合、コントロールは、透明な部分を含めることができます。  
      
        単色の背景、不透明なコントロールだけことができます。  
      
 -   な VIEWSTATUS 列挙体でビット VIEWSTATUS_SOLIDBKGND を設定します。 コントロールの背景は、パターンのない純色として表示されます。  
      
  このオプションは使用可能な場合にのみ、**不透明**オプションも選択します。  
  
**コントロールを追加します。**  
コントロールを追加して、Windows のコントロール型に基づく設定、 [CContainedWindow](ccontainedwindowt-class.md)コントロールを実装するクラスのデータ メンバー。 また、メッセージ マップとコントロール用の Windows メッセージを処理するメッセージ ハンドラー関数を追加します。 存在する場合は、作成する Windows コントロールの種類を一覧から選択します。  

 -   `Button`  
      
 -   `ListBox`  
      
 -   `SysAnimate32`  
      
 -   `SysListView32`  
      
 -   `ComboBox`  
      
 -   `RichEdit`  
      
 -   `SysDateTimePick32`  
      
 -   `SysMonthCal32`  
      
 -   `ComboBoxEx32`  
      
 -   `ScrollBar`  
      
 -   `SysHeader32`  
      
 -   `SysTabControl32`  
      
 -   `Edit`  
      
 -   `Static`  
      
 -   `SysIPAddress32`  
      
 -   `SysTreeView32`  
  
**その他の状態**  
コントロールの外観と動作の追加オプションを設定します。  
  
 -   **実行時に非表示**: に実行時に表示されないコントロールを設定します。 非表示のコントロールを使用して、指定された間隔でイベントを発生させるなど、バック グラウンドで操作を実行することができます。  
      
 -   **ボタンのような動作**: OLEMISC_ACTSLIKEBUTTON のビットを設定、[入ります](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc)ボタンなどのコントロールに動作を有効にする列挙体。 コンテナーには、既定のボタンとコントロールのクライアント サイトがマークされているが、このオプションを選択すると、ボタン コントロール自体を太くフレームを描画することで、既定のボタンとして表示を有効になります。 参照してください[CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault)詳細についてはします。  
      
  -   **ラベルのように動作**: コンテナーのネイティブのラベルを置換するコントロールを有効にする OLEMISC_ACTSLIKELABEL 入ります列挙体のビットを設定します。 コンテナーは、何も場合、このフラグの処理を決定します。  
  
**その他**  
コントロールの動作を追加のオプションを設定します。  
  
 -   **DC の正規化**: 自体を描画するために呼び出された場合は、正規化されたデバイス コンテキストを作成するコントロールを設定します。 コントロールの外観を標準化します。 このアクションが、描画の効率が低下します。  
      
 -   **ウィンドウのみ**: ウィンドウなしのコントロールであることを指定します。 このオプションを選択しない場合、コントロールはウィンドウなしのオブジェクトをサポートするコンテナーで自動的にウィンドウなしとはウィンドウなしのオブジェクトをサポートしていないコンテナーに自動的にウィンドウ。 ウィンドウなしのオブジェクトをサポートするコンテナーであっても、ウィンドウに強制的にこのオプションを選択します。  
      
 -   **挿入可能な**: コントロールを表示するには、このオプションを選択、**オブジェクトの挿入**Word や Excel などのアプリケーションのダイアログ ボックス。 コントロールは、このダイアログ ボックスから埋め込みオブジェクトをサポートする任意のアプリケーションで挿入できます。  
  
## <a name="see-also"></a>関連項目  
 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)   
 [標準の Windows コントロールをスーパークラスのサンプルを SUBEDIT:](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)

