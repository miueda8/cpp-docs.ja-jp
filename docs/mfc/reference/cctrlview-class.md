---
title: CCtrlView クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
dev_langs:
- C++
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fdcec255c7d2398e1bb0efa7f86a31fc5dd938e4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210204"
---
# <a name="cctrlview-class"></a>CCtrlView クラス
Windows 98 および Windows NT Version 3.51 以降がサポートするコモン コントロールにドキュメント/ビュー アーキテクチャを適合させます。  
  
## <a name="syntax"></a>構文  
  
```  
class CCtrlView : public CView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](#cctrlview)|`CCtrlView` オブジェクトを構築します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCtrlView::OnDraw](#ondraw)|指定したデバイス コンテキストを使用して描画するためにフレームワークによって呼び出されます。|  
|[CCtrlView::PreCreateWindow](#precreatewindow)|`CCtrlView` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|ビュー クラスの既定のスタイルが含まれています。|  
|[CCtrlView::m_strClass](#m_strclass)|ビュー クラスの Windows クラス名が含まれています。|  
  
## <a name="remarks"></a>Remarks  
 クラスは、`CCtrlView`とその派生物、 [CEditView](../../mfc/reference/ceditview-class.md)、 [CListView](../../mfc/reference/clistview-class.md)、 [CTreeView](../../mfc/reference/ctreeview-class.md)、および[CRichEditView](../../mfc/reference/cricheditview-class.md)、調整、Windows 95/98 および Windows NT version 3.51 以降は新しいコモン コントロールをドキュメント/ビュー アーキテクチャ サポート。 ドキュメント/ビュー アーキテクチャの詳細については、次を参照してください。[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cctrlview"></a>  CCtrlView::CCtrlView  
 `CCtrlView` オブジェクトを構築します。  
  
```  
CCtrlView(
    LPCTSTR lpszClass,  
    DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszClass*  
 ビュー クラスの Windows クラス名。  
  
 *dwStyle*  
 ビュー クラスのスタイル。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、新しいフレーム ウィンドウが作成されるか、ウィンドウを分割時に、コンス トラクターを呼び出します。 オーバーライド[:oninitialupdate](../../mfc/reference/cview-class.md#oninitialupdate)ドキュメントがアタッチされた後に、ビューを初期化します。 呼び出す[cwnd::create](../../mfc/reference/cwnd-class.md#create)または[とき](../../mfc/reference/cwnd-class.md#createex)Windows オブジェクトを作成します。  
  
##  <a name="m_strclass"></a>  CCtrlView::m_strClass  
 ビュー クラスの Windows クラス名が含まれています。  
  
```  
CString m_strClass;  
```  
  
##  <a name="m_dwdefaultstyle"></a>  CCtrlView::m_dwDefaultStyle  
 ビュー クラスの既定のスタイルが含まれています。  
  
```  
DWORD m_dwDefaultStyle;  
```  
  
### <a name="remarks"></a>Remarks  
 ウィンドウが作成されたときに、このスタイルが適用されます。  
  
##  <a name="ondraw"></a>  CCtrlView::OnDraw  
 内容を描画するためにフレームワークによって呼び出されます、`CCtrlView`オブジェクトの指定したデバイス コンテキストを使用します。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 描画が発生したデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>Remarks  
 `OnDraw` 通常で指定した画面のデバイス コンテキストを渡して、画面表示のために呼び出されます*pDC*します。  
  
##  <a name="precreatewindow"></a>  CCtrlView::PreCreateWindow  
 `CWnd` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>パラメーター  
 *cs*  
 A [CREATESTRUCT](https://msdn.microsoft.com/library/windows/desktop/ms632603)構造体。  
  
### <a name="return-value"></a>戻り値  
 以外の場合、ウィンドウの作成を続行する必要があります。作成の失敗を示すには 0。  
  
### <a name="remarks"></a>Remarks  
 この関数を直接呼び出すことはありません。  
  
 この関数の既定の実装では、ウィンドウ クラスの名前は NULL をチェックし、適切なの既定値に置換されます。 変更するには、このメンバー関数をオーバーライド、`CREATESTRUCT`ウィンドウが作成される前に構造体します。  
  
 各クラスから派生した`CCtrlView`のオーバーライドを独自の機能を追加します。`PreCreateWindow`します。 仕様上、これらの派生の`PreCreateWindow`記載されていません。 各クラスと、スタイルの間の相互依存関係を適切なスタイルを確認するのには、アプリケーションの基本クラスの MFC ソース コードを確認できます。 オーバーライドする場合`PreCreateWindow`アプリケーションの基本クラスで使用されているスタイルが、MFC のソース コードから収集された情報を使用して必要な機能を提供するかどうかを指定できます。  
  
 ウィンドウ スタイルを変更する方法の詳細については、次を参照してください。、 [MFC で作成したウィンドウのスタイルを変更する](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)します。  
  
## <a name="see-also"></a>関連項目  
 [CView クラス](../../mfc/reference/cview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CTreeView クラス](../../mfc/reference/ctreeview-class.md)   
 [CListView クラス](../../mfc/reference/clistview-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)
