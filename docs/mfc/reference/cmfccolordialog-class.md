---
title: CMFCColorDialog クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a1d5c2d7bb2da2ba293ac29a59948f80c1bed59
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680611"
---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog クラス
`CMFCColorDialog`クラスは、色の選択 ダイアログ ボックスを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|`CMFCColorDialog` オブジェクトを構築します。|  
|`CMFCColorDialog::~CMFCColorDialog`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](#getcolor)|現在選択されている色を返します。|  
|[CMFCColorDialog::GetPalette](#getpalette)|色のパレットを返します。|  
|`CMFCColorDialog::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 関数。 構文と詳細については、次を参照してください。 [cwnd::pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)します。 (`CDialogEx::PreTranslateMessage` をオーバーライドします)。|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|パレットは、システム パレットから派生します。|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|現在の選択した色を設定します。|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|指定された RGB 値に最も近い色を設定します。|  
|[CMFCColorDialog::SetPageOne](#setpageone)|最初のプロパティ ページの RGB 値を選択します。|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|2 番目のプロパティ ページの RGB 値を選択します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|`m_bIsMyPalette`|色の選択 ダイアログ ボックスで、独自のカラー パレットを使用する場合は TRUE または FALSE の場合、ダイアログ ボックスで指定されているパレットを使用して、`CMFCColorDialog`コンス トラクター。|  
|`m_bPickerMode`|TRUE に、ユーザーが選択 ダイアログ ボックスから色の選択それ以外の場合、FALSE です。|  
|`m_btnColorSelect`|色のボタンをユーザーが選択されます。|  
|`m_CurrentColor`|現在選択されている色です。|  
|`m_hcurPicker`|色の選択に使用するカーソル。|  
|`m_NewColor`|これから選択色では、完全に選択されているまたは色を元に戻すことができます。|  
|`m_pColourSheetOne`|色の選択のプロパティ シートの最初のプロパティ ページへのポインター。|  
|`m_pColourSheetTwo`|色の選択のプロパティ シートの 2 番目のプロパティ ページへのポインター。|  
|`m_pPalette`|現在の論理パレット。|  
|`m_pPropSheet`|色の選択 ダイアログ ボックスのプロパティ シートへのポインター。|  
|`m_wndColors`|カラー ピッカー コントロール オブジェクト。|  
|`m_wndStaticPlaceHolder`|カラー ピッカーのプロパティ シートのプレース ホルダーである静的なコントロールします。|  
  
## <a name="remarks"></a>Remarks  
 色の選択 ダイアログ ボックスは、2 つのページでプロパティ シートとして表示されます。 最初のページで、システム パレットから標準の色を選択します。2 番目のページには、カスタムの色を選択します。  
  
 構築することができます、`CMFCColorDialog`スタック上のオブジェクトを呼び出して`DoModal`、初期の色をパラメーターとして渡す、`CMFCColorDialog`コンス トラクター。 [色の選択] ダイアログ ボックスがいくつか作成します[CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)各色パレットを処理するオブジェクト。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>例  
 次の例は、さまざまなメソッドを使用して色のダイアログを構成する方法を示します、`CMFCColorDialog`クラス。 例では、現在と、ダイアログの新しい色を設定する方法および色 ダイアログ ボックスの 2 つのプロパティ ページで選択した色の赤、緑、および青のコンポーネントを設定する方法を示します。 この例は、[新しいコントロール サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcolordialog.h  
  
##  <a name="cmfccolordialog"></a>  CMFCColorDialog::CMFCColorDialog  
 `CMFCColorDialog` オブジェクトを構築します。  
  
```  
CMFCColorDialog(
    COLORREF clrInit=0,  
    DWORD dwFlags=0,  
    CWnd* pParentWnd=NULL,  
    HPALETTE hPal=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*clrInit*  
 既定色を選択します。 値が指定されていない場合は、既定では RGB(0,0,0) (黒です)。  
  
 [in]*dwFlags*  
 (予約されています。)  
  
 [in]*pParentWnd*  
 ウィンドウ、ダイアログ ボックスの親またはオーナー ウィンドウへのポインター。  
  
 [in]*hPal*  
 色パレットへのハンドル。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcolor"></a>  CMFCColorDialog::GetColor  
 ユーザーが色 ダイアログ ボックスから選択した色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](/windows/desktop/gdi/colorref)色 ダイアログ ボックスで選択した色の RGB の情報を含む値。  
  
### <a name="remarks"></a>Remarks  
 呼び出した後、この関数を呼び出す、`DoModal`メソッド。  
  
##  <a name="getpalette"></a>  CMFCColorDialog::GetPalette  
 現在の色 ダイアログで使用できるカラー パレットを取得します。  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPalette`で指定されたオブジェクト、`CMFCColorDialog`コンス トラクター。  
  
### <a name="remarks"></a>Remarks  
 カラー パレットには、ユーザーが選択できる色を指定します。  
  
##  <a name="rebuildpalette"></a>  CMFCColorDialog::RebuildPalette  
 パレットは、システム パレットから派生します。  
  
```  
void RebuildPalette();
```  
  
##  <a name="setcurrentcolor"></a>  CMFCColorDialog::SetCurrentColor  
 ダイアログ ボックスの現在の色を設定します。  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*rgb*  
 RGB カラー値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setnewcolor"></a>  CMFCColorDialog::SetNewColor  
 現在の色を最も近い現在パレットの色に設定します。  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*rgb*  
 A [COLORREF](/windows/desktop/gdi/colorref) RGB 色を指定します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setpageone"></a>  CMFCColorDialog::SetPageOne  
 色のダイアログ ボックスの最初のプロパティ ページで選択した色の赤、緑、および青のコンポーネントを明示的に指定します。  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*R*  
 RGB 値の赤の要素を指定します。  
  
 [in]*G*  
 RGB 値の緑の成分を指定します。  
  
 [in]*B*  
 RGB 値の青のコンポーネントを指定します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setpagetwo"></a>  CMFCColorDialog::SetPageTwo  
 色のダイアログ ボックスの 2 つ目のプロパティ ページで選択した色の赤、緑、および青のコンポーネントを明示的に指定します。  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*R*  
 RGB 値の赤の要素を指定します  
  
 [in]*G*  
 RGB 値の緑の成分を指定します  
  
 [in]*B*  
 RGB 値の青のコンポーネントを指定します  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)
