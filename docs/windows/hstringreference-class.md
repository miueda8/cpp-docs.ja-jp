---
title: HStringReference クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
dev_langs:
- C++
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b80ae92671b2ee78cd2f48e9a35958c89232e4e5
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683042"
---
# <a name="hstringreference-class"></a>HStringReference クラス

既存の文字列から作成された HSTRING を表します。

## <a name="syntax"></a>構文

```cpp
class HStringReference;
```

## <a name="remarks"></a>Remarks

新しい HSTRING のバッキング バッファーの有効期間は、Windows ランタイムで管理されていません。 呼び出し元はソース文字列をスタック フレームに割り当てることで、ヒープ割り当てを回避し、メモリ リークのリスクを排除します。 また、呼び出し元はアタッチ済みの HSTRING の有効期間中にソース文字列が変更されないことを確認する必要があります。 詳細については、次を参照してください。 [WindowsCreateStringReference 関数](/windows/desktop/api/winstring/nf-winstring-windowscreatestringreference)します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[HStringReference::HStringReference コンストラクター](../windows/hstringreference-hstringreference-constructor.md)|新しいインスタンスを初期化、 **HStringReference**クラス。|

### <a name="members"></a>メンバー

|メンバー|説明|
|------------|-----------------|
|[HStringReference::CopyTo メソッド](../windows/hstringreference-copyto-method.md)|現在のコピー **HStringReference**オブジェクトを HSTRING オブジェクトにします。|
|[HStringReference::Get メソッド](../windows/hstringreference-get-method.md)|基になる HSTRING ハンドルの値を取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[HStringReference::Operator= 演算子](../windows/hstringreference-operator-assign-operator.md)|別の値を移動**HStringReference**現在オブジェクト**HStringReference**オブジェクト。|
|[HStringReference::Operator== 演算子](../windows/hstringreference-operator-equality-operator.md)|2 つのパラメーターが等しいかどうかを示します。|
|[HStringReference::Operator!= 演算子](../windows/hstringreference-operator-inequality-operator.md)|2 つのパラメーターが異なるかどうかを示します。|

## <a name="inheritance-hierarchy"></a>継承階層

`HStringReference`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)