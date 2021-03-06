---
title: COleException クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs:
- C++
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a472de31695ab6038cab9ba0158580f3d305194
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212489"
---
# <a name="coleexception-class"></a>COleException クラス
OLE 操作に関する例外条件を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleException::Process](#process)|OLE のリターン コードにキャッチされた例外に変換します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|例外の原因を示すステータス コードが含まれています。|  
  
## <a name="remarks"></a>Remarks  
 `COleException`クラスには、例外の理由を示すステータス コードを保持するパブリック データ メンバーが含まれています。  
  
 一般に、作成しないようにする、`COleException`オブジェクトは、直接呼び出す必要があります[AfxThrowOleException](exception-processing.md#afxthrowoleexception)します。  
  
 例外の詳細については、記事をご覧ください。[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)と[例外: OLE 例外](../../mfc/exceptions-ole-exceptions.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="m_sc"></a>  COleException::m_sc  
 OLE の例外の理由を示すステータス コードを保持します。  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>Remarks  
 この変数の値によって設定されます[AfxThrowOleException](exception-processing.md#afxthrowoleexception)します。  
  
 SCODE の詳細については、次を参照してください。 [COM エラー コードの構造](/windows/desktop/com/structure-of-com-error-codes)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>  COleException::Process  
 呼び出す、**プロセス**OLE のステータス コードにキャッチされた例外に変換します。  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>パラメーター  
 *pAnyException*  
 キャッチされた例外へのポインター。  
  
### <a name="return-value"></a>戻り値  
 OLE のステータス コード。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  この関数は**静的**します。  
  
 SCODE の詳細については、次を参照してください。 [COM エラー コードの構造](/windows/desktop/com/structure-of-com-error-codes)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例をご覧ください[coledispatchdriver::createdispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CALCDRIV](../../visual-cpp-samples.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



