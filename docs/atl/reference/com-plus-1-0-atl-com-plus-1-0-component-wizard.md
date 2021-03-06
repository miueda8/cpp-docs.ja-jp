---
title: COM + 1.0、ATL COM + 1.0 コンポーネント ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.options
dev_langs:
- C++
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 158d279106538fd059252f8e8dcd19aeb6a20f6d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198193"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0、ATL COM+ 1.0 コンポーネント ウィザード
ATL COM + 1.0 コンポーネント ウィザードのこのページを使用すると、サポートするのにには、インターフェイスの種類と追加のインターフェイスを指定できます。  
  
 ATL プロジェクトや ATL COM クラスの詳細については、次を参照してください。 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)します。  
  
 **Interface**  
 オブジェクトがサポートするインターフェイスの種類を示します。 既定では、オブジェクトは、デュアル インターフェイスをサポートします。  
  
|オプション|説明|  
|------------|-----------------|  
|**デュアル**|オブジェクトがデュアル インターフェイスをサポートしていることを指定します (その vtable がカスタム インターフェイス関数と遅延バインディング`IDispatch`メソッド)。 COM クライアントおよびオートメーション コント ローラーがオブジェクトへのアクセスを許可します。|  
|**カスタム**|オブジェクトが (その vtable がカスタム インターフェイス関数) カスタム インターフェイスをサポートするように指定します。 カスタム インターフェイスはプロセスの境界をまたいで、デュアル インターフェイスよりも高速化できます。<br /><br /> -   **互換性のある automation**カスタム インターフェイスをオートメーションのサポートを追加します。 属性付きプロジェクトは、設定、 **oleautomation**コクラスの属性。|  
  
 **Queueable**  
 クライアントが非同期的にメッセージ キューを使用して、このコンポーネントを呼び出すことを示します。 .H ファイル (属性付きプロジェクト) または .idl ファイル (プロジェクト属性なし) には、コンポーネントの属性マクロ カスタム (TLBATTR_QUEUEABLE 0) を追加します。  
  
 **サポート**  
 エラー処理とオブジェクトのコントロールの追加サポートを示します。  
  
|オプション|説明|  
|------------|-----------------|  
|**ISupportErrorInfo**|作成のサポート、 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)インターフェイスのため、オブジェクトは、クライアントにエラー情報を返すことができます。|  
|**IObjectControl**|3 つに、オブジェクトへのアクセスを提供します。 [IObjectControl](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectcontrol)メソッド:[アクティブ化](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-activate)、 [CanBePooled](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-canbepooled)、および[非アクティブ化](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-deactivate)します。|  
|**IObjectConstruct**|作成のサポート、 [IObjectConstruct](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectconstruct)他のメソッドやオブジェクトからパラメーターの受け渡しを管理するインターフェイス。|  
  
 **トランザクション**  
 オブジェクトがトランザクションをサポートすることを示します。 .Idl ファイル (プロジェクト属性なし) では、ファイル mtxattr.h が含まれています。  
  
|オプション|説明|  
|------------|-----------------|  
|**サポート状況**|オブジェクトではないことをトランザクション ストリームのルート コンポーネントの属性マクロ custom(TLBATTR_TRANS_SUPPORTED,0) .h ファイル (属性付きプロジェクト) または .idl ファイル (プロジェクト属性なし) を追加することでを指定します。|  
|**必須**|オブジェクトは可能性がありますか、コンポーネントの属性マクロ custom(TLBATTR_TRANS_REQUIRED,0) .h ファイル (属性付きプロジェクト) または .idl ファイル (プロジェクト属性なし) を追加することによってトランザクション ストリームのルートができない可能性がありますを指定します。|  
|**サポートされていません**|オブジェクトがトランザクションを除外することを指定します。 .H ファイル (属性付きプロジェクト) または .idl ファイル (プロジェクト属性なし) には、コンポーネントの属性マクロ custom(TLBATTR_TRANS_NOTSUPP,0) を追加します。|  
|**新しいが必要です。**|オブジェクトが常にトランザクション ストリームのルート コンポーネントの属性マクロ custom(TLBATTR_TRANS_REQNEW,0) .h ファイル (属性付きプロジェクト) または .idl ファイル (プロジェクト属性なし) を追加することでを指定します。|  
  
## <a name="see-also"></a>関連項目  
 [ATL COM + 1.0 コンポーネント ウィザード](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM + 1.0 コンポーネント](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

