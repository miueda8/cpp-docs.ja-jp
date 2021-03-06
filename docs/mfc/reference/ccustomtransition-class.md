---
title: CCustomTransition クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
dev_langs:
- C++
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39588a6835b3484fc3961e793596c1190f85f7c4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952753"
---
# <a name="ccustomtransition-class"></a>CCustomTransition クラス
カスタム遷移を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCustomTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCustomTransition::CCustomTransition](#ccustomtransition)|カスタム遷移オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCustomTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
|[CCustomTransition::SetInitialValue](#setinitialvalue)|この遷移に関連付けられているアニメーション変数に適用される初期の値を設定します。|  
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|この遷移に関連付けられているアニメーション変数に適用される初期の速度を設定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|SetInitialValue で初期値が指定されたかどうかを指定します。|  
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|初期ベロシティが SetInitialVelocity で指定されたかどうかを指定します。|  
|[CCustomTransition::m_initialValue](#m_initialvalue)|初期値を格納します。|  
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|初期ベロシティを格納します。|  
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|カスタムのインターポレータへのポインターを格納します。|  
  
## <a name="remarks"></a>Remarks  
 CCustomTransitions クラスは、開発者がカスタム遷移を実装するを使用します。 作成されるので、標準の遷移と使用が、そのコンス トラクターがパラメーターとしてカスタム インターポレータへのポインターを受け取ります。 カスタム遷移を使用する次の手順: 1。 CCustomInterpolator からクラスを派生し、実装には、少なくとも InterpolateValue メソッドです。 2. 確認してカスタムのインターポレータ オブジェクトの有効期間必要がありますのアニメーションの期間より長くが使用されています。 3. オブジェクトのインスタンス (新しい演算子を使用して)、CCustomTransition し、コンス トラクターでカスタムのインターポレータをへのポインターを渡します。 4. これらのパラメーターは、カスタムの補間に必要な場合は、CCustomTransition::SetInitialValue と CCustomTransition::SetInitialVelocity を呼び出します。 5. カスタムのアルゴリズムでアニメーション化する値を持つアニメーション オブジェクトの AddTransition メソッドへのカスタム移行へのポインターを渡します。 6. アニメーション オブジェクトの値を変更する必要がある場合は、Windows Animation API が CCustomInterpolator でに InterpolateValue (およびその他の関連するメソッド) を呼び出します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CCustomTransition`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="ccustomtransition"></a>  CCustomTransition::CCustomTransition  
 カスタム遷移オブジェクトを構築します。  
  
```  
CCustomTransition(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>パラメーター  
 *pInterpolator*  
 カスタムのインターポレータへのポインター。  
  
##  <a name="create"></a>  CCustomTransition::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,  
    IUIAnimationTransitionFactory* pFactory);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFactory*  
 カスタム遷移の作成を担当する遷移ファクトリへのポインター。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、初期値と、この遷移に関連付けられているアニメーション変数に適用する初期ベロシティ使用設定できますも。 この目的のフレームワーク (CAnimationController::AnimateGroup を呼び出すときに行われます)、遷移をカプセル化された COM オブジェクトを作成する前に、SetInitialValue と SetInitialVelocity を呼び出す必要があります。  
  
##  <a name="m_binitialvaluespecified"></a>  CCustomTransition::m_bInitialValueSpecified  
 SetInitialValue で初期値が指定されたかどうかを指定します。  
  
```  
BOOL m_bInitialValueSpecified;  
```  
  
##  <a name="m_binitialvelocityspecified"></a>  CCustomTransition::m_bInitialVelocitySpecified  
 初期ベロシティが SetInitialVelocity で指定されたかどうかを指定します。  
  
```  
BOOL m_bInitialVelocitySpecified;  
```  
  
##  <a name="m_initialvalue"></a>  CCustomTransition::m_initialValue  
 初期値を格納します。  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="m_initialvelocity"></a>  CCustomTransition::m_initialVelocity  
 初期ベロシティを格納します。  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="m_pinterpolator"></a>  CCustomTransition::m_pInterpolator  
 カスタムのインターポレータへのポインターを格納します。  
  
```  
CCustomInterpolator* m_pInterpolator;  
```  
  
##  <a name="setinitialvalue"></a>  CCustomTransition::SetInitialValue  
 この遷移に関連付けられているアニメーション変数に適用される初期の値を設定します。  
  
```  
void SetInitialValue(DOUBLE initialValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *初期値*  
  
##  <a name="setinitialvelocity"></a>  CCustomTransition::SetInitialVelocity  
 この遷移に関連付けられているアニメーション変数に適用される初期の速度を設定します。  
  
```  
void SetInitialVelocity(DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>パラメーター  
 *initialVelocity*  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
