---
title: CMFCRibbonButtonsGroup クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 855bc48da10e8ca4dd83cf091e155746450a33f1
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848520"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup クラス
`CMFCRibbonButtonsGroup`クラスは、リボン ボタンのセットをグループにまとめることができます。 グループ内のすべてのボタンは互いに隣接して水平に並べられ、1 つの枠で囲まれます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|`CMFCRibbonButtonsGroup` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|グループには、ボタンを追加します。|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|ボタンのリストをグループに追加します。|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|指定したインデックス位置にあるボタンにポインターを返します。|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|グループ内のボタンの数を返します。|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|リボン グループ内の通常のイメージのイメージのサイズを返します (オーバーライド[cmfcribbonbaseelement::getimagesize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize))。|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|リボン要素の通常のサイズを返します (オーバーライド[cmfcribbonbaseelement::getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize))。|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|レポートするかどうか、`CMFCRibbonButtonsGroup`オブジェクトには、ツール バー イメージが含まれています。|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|ボタンは、通常、強調表示されている、または無効になっているかどうかに応じて、指定したボタンの適切なイメージを描画します。|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|すべてのボタンの削除、`CMFCRibbonButtonsGroup`オブジェクト。|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|画像をグループに割り当てます。|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|親を設定`CMFCRibbonCategory`の`CMFCRibbonButtonsGroup`オブジェクトとその中のすべてのボタン (オーバーライド[cmfcribbonbaseelement::setparentcategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory))。|  
  
## <a name="remarks"></a>Remarks  
 派生した、グループは[CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md)および単一のエンティティとして操作できます。 パネルまたはポップアップ メニューに、グループを配置することができます。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCRibbonButtonsGroup`クラス。 例では、作成する方法を示しています、`CMFCRibbonButtonsGroup`オブジェクト、イメージをリボン ボタンのグループに割り当てるし、リボン ボタンのグループにボタンを追加します。 このコード スニペットは、「 [クライアント サンプルの描画](../../visual-cpp-samples.md)」の一部です。  
  
 [!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxribbonbuttonsgroup.h  
  
##  <a name="addbutton"></a>  CMFCRibbonButtonsGroup::AddButton  
 グループには、ボタンを追加します。  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pButton*  
 追加するボタンへのポインター。  
  
##  <a name="addbuttons"></a>  CMFCRibbonButtonsGroup::AddButtons  
 ボタンのリストをグループに追加します。  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lstButtons*  
 追加するボタンへのポインターのリスト。  
  
##  <a name="cmfcribbonbuttonsgroup"></a>  CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 `CMFCRibbonButtonsGroup` オブジェクトを構築します。  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pButton*  
 新しく作成されたに追加するボタンを指定`CMFCRibbonButtonsGroup`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getbutton"></a>  CMFCRibbonButtonsGroup::GetButton  
 指定したインデックス位置にあるボタンにポインターを返します。  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*しました*  
 返すボタンの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置にあるボタンへのポインター。 指定したインデックスが範囲外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcount"></a>  CMFCRibbonButtonsGroup::GetCount  
 グループ内のボタンの数を返します。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 グループ内のボタンの数。  
  
##  <a name="getimagesize"></a>  CMFCRibbonButtonsGroup::GetImageSize  
 保護対象のソース イメージのサイズを取得`CMFCToolBarImages`メンバー`m_Images`します。  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 いずれかが存在するか、ツールバーのイメージのソース イメージのサイズを返します`CSize`の場合は 0。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getregularsize"></a>  CMFCRibbonButtonsGroup::GetRegularSize  
 リボン グループ要素の最大サイズを取得します。  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 リボン グループのデバイス コンテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="hasimages"></a>  CMFCRibbonButtonsGroup::HasImages  
 レポートするかどうか、`CMFCRibbonButtonsGroup`オブジェクトには、ツール バー イメージが含まれています。  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>戻り値  
 True の場合、保護された`CMFCToolBarImages`メンバー`m_Images`しないすべての画像、または場合は FALSE が含まれています。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondrawimage"></a>  CMFCRibbonButtonsGroup::OnDrawImage  
 ボタンは、通常、強調表示されている、または無効になっているかどうかに応じて、指定したボタンの適切なイメージを描画します。  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rectImage,  
    CMFCRibbonBaseElement* pButton,  
    int nImageIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター、`CMFCRibbonButtonsGroup`オブジェクト。  
  
 [in]*rectImage*  
 イメージを描画する四角形。  
  
 [in]*pButton*  
 イメージを描画するためのボタンをクリックします。  
  
 [in]*nImageIndex*  
 (通常、強調表示されている、または無効になっているボタンの 3 つのイメージの配列のいずれか) のボタンを描画するイメージのインデックス。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="removeall"></a>  CMFCRibbonButtonsGroup::RemoveAll  
 すべてのボタンの削除、`CMFCRibbonButtonsGroup`オブジェクト。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setimages"></a>  CMFCRibbonButtonsGroup::SetImages  
 リボン ボタンのグループには、イメージを割り当てます。  
  
```  
void SetImages(
    CMFCToolBarImages* pImages,  
    CMFCToolBarImages* pHotImages,  
    CMFCToolBarImages* pDisabledImages);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pImages*  
 通常のイメージ。  
  
 [in]*pHotImages*  
 ホット イメージ。  
  
 [in]*pDisabledImages*  
 無効なイメージ。  
  
### <a name="remarks"></a>Remarks  
 呼び出す`SetImages`ボタンをグループに追加する前にします。 イメージの数は、グループに追加するボタンの数以上である必要があります。  
  
> [!NOTE]
>  ホット イメージとは、ユーザーがボタン上に置いたときに表示されるイメージです。 無効なイメージとは、ボタンが無効になっているときに表示されるイメージです。  
  
##  <a name="setparentcategory"></a>  CMFCRibbonButtonsGroup::SetParentCategory  
 親を設定`CMFCRibbonCategory`の`CMFCRibbonButtonsGroup`オブジェクトとその中のすべてのボタン。  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pCategory*  
 設定を親カテゴリへのポインター (リボン コントロールのタブ付きグループはカテゴリで呼ばれます)。  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
