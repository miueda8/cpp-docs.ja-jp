---
title: IRowsetInfoImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
- ATL.IRowsetInfoImpl.GetProperties
- IRowsetInfoImpl.GetProperties
- ATL::IRowsetInfoImpl::GetProperties
- IRowsetInfoImpl::GetProperties
- GetProperties
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
dev_langs:
- C++
helpviewer_keywords:
- IRowsetInfoImpl class
- GetProperties method
- GetReferencedRowset method
- GetSpecification method
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d07c0e64e969e599393a657d4c41a8dd544901c9
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572663"
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl クラス
実装を提供、 [IRowsetInfo](/previous-versions/windows/desktop/ms724541\(v=vs.85\))インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IRowsetInfoImpl`します。  
  
 *PropClass*  
 その既定値はユーザー定義プロパティ クラス*T*します。 

## <a name="requirements"></a>要件  
 **ヘッダー:** altdb.h   
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|行セットでサポートされるすべてのプロパティの現在の設定を返します。|  
|[GetReferencedRowset](#getreferencedrowset)|ブックマークを適用する行セットにインターフェイス ポインターを返します。|  
|[GetSpecification](#getspecification)|この行セットを作成するオブジェクト (コマンドまたはセッション) のインターフェイス ポインターを返します。|  
  
## <a name="remarks"></a>Remarks  
 行セットの必須インターフェイス。 このクラスを使用して行セット プロパティを実装する、[プロパティ セットのマップ](../../data/oledb/begin-propset-map.md)コマンド クラスで定義されています。 行セット クラスでは、コマンド クラスのプロパティを使用する設定が表示されますが、コマンドまたはセッション オブジェクトが作成されたとき、実行時のプロパティの独自のコピーでは、行セットが指定されました。  
  
## <a name="getproperties"></a> Irowsetinfoimpl::getproperties
プロパティの現在の設定を返します、`DBPROPSET_ROWSET`グループ。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (GetProperties )(const ULONG cPropertyIDSets,  
   const DBPROPIDSET rgPropertyIDSets[],  
   ULONG* pcPropertySets,  
   DBPROPSET** prgPropertySets);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowsetinfo::getproperties](/previous-versions/windows/desktop/ms719611\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。 

## <a name="getreferencedrowset"></a> Irowsetinfoimpl::getreferencedrowset
ブックマークを適用する行セットにインターフェイス ポインターを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (GetReferencedRowset )(DBORDINAL iOrdinal,  
   REFIID riid,  
   IUnknown** ppReferencedRowset);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IRowsetInfo::GetReferencedRowset](/previous-versions/windows/desktop/ms721145\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。 *IOrdinal*パラメーターはブックマーク列である必要があります。 

## <a name="getspecification"></a> Irowsetinfoimpl::getspecification
この行セットを作成するオブジェクト (コマンドまたはセッション) のインターフェイス ポインターを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (GetSpecification )(REFIID riid,  
   IUnknown** ppSpecification);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IRowsetInfo::GetSpecification](/previous-versions/windows/desktop/ms716746\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用[IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)データ ソース オブジェクトからプロパティを取得します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)