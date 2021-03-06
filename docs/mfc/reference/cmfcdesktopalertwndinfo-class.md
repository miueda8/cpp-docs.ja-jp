---
title: CMFCDesktopAlertWndInfo クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d5cf3c8804595aa3d0f3a83bc2628ea830e786a
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540913"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo クラス
`CMFCDesktopAlertWndInfo`クラスで使用されます、 [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)します。 デスクトップ通知ウィンドウがポップアップする場合に表示されるコントロールを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[アイコン](#m_hicon)|表示されるアイコンへのハンドル。|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|デスクトップ通知ウィンドウ上のリンクに関連付けられているコマンド ID。|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|デスクトップ通知ウィンドウに表示されるテキスト。|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|デスクトップ通知ウィンドウに表示されるリンク。|  
  
## <a name="remarks"></a>Remarks  
 `CMFCDesktopAlertWndInfo`クラスに渡される、 [cmfcdesktopalertwnd::create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)デスクトップ通知ウィンドウの [既定] ダイアログ ボックスに表示される要素を指定します。 既定のダイアログ ボックスは、3 つの項目を含めることができます。  
  
-   アイコンは、呼び出すことによって設定が[アイコン](#m_hicon)します。  
  
-   ラベル、または呼び出すことによって設定されたテキスト メッセージ、 [CMFCDesktopAlertWndInfo::m_strText](#m_strtext)します。  
  
-   呼び出すことによって設定されているリンク[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)します。 リンクがクリックされたときに実行されるコマンドを設定するには、呼び出す[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)します。  
  
 既定のダイアログ ボックスが十分ではない場合は、カスタム ダイアログを作成およびに渡す、 [cmfcdesktopalertwnd::create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)メソッドをこのクラスを使用する代わりにします。 詳細については、次を参照してください。 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメンバーを使用する方法、`CMFCDesktopAlertWndInfo`クラス。 この例では、デスクトップ通知ウィンドウ、デスクトップの通知ウィンドウに表示されているリンクおよびデスクトップ通知ウィンドウ上のリンクに関連付けられているコマンド ID に表示されるテキスト、アイコンが表示されたらにハンドルを設定する方法を示します。 この例は、[デスクトップ アラート デモ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxDesktopAlertDialog.h  
  
##  <a name="operator_eq"></a>  CMFCDesktopAlertWndInfo::operator =  
 詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。  
  
```  
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*src*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_hicon"></a>  アイコン  
 表示されるアイコンへのハンドル。  
  
```  
HICON m_hIcon;  
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_nurlcmdid"></a>  CMFCDesktopAlertWndInfo::m_nURLCmdID  
 デスクトップ通知ウィンドウ上のリンクに関連付けられているコマンド ID。  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>Remarks  
 ユーザーによって指定されたリンクをクリックすると、コマンド ID がポップアップ ウィンドウの所有者に送信されます[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)します。  
  
##  <a name="m_strtext"></a>  CMFCDesktopAlertWndInfo::m_strText  
 デスクトップ通知ウィンドウに表示されるテキスト。  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_strurl"></a>  CMFCDesktopAlertWndInfo::m_strURL  
 デスクトップ通知ウィンドウに表示されるリンク。  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>Remarks  
 ユーザーは、リンクをクリックすると、コマンドを持つ、 [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)コマンド ID は、ポップアップ ウィンドウの所有者に送信されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [Cmfcdesktopalertwnd::create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)
