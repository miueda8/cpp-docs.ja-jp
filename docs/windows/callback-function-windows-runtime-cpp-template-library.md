---
title: コールバック関数 (Windows ランタイム C++ テンプレート ライブラリ) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Callback
dev_langs:
- C++
ms.assetid: afb15d25-3230-44f7-b321-e17c54872943
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 57d1a3adc160323726bcdd31808cf82bc8da2e7f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609255"
---
# <a name="callback-function-windows-runtime-c-template-library"></a>コールバック関数 (Windows ランタイム C++ テンプレート ライブラリ)

メンバー関数がコールバック メソッドであるオブジェクトを作成します。

## <a name="syntax"></a>構文

```cpp
template<
   typename TDelegateInterface,
   typename TCallback
>
ComPtr<TDelegateInterface> Callback(
   TCallbackcallback
);
template<
   typename TDelegateInterface,
   typename TCallbackObject
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)()  
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1)  
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2)  
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3)  
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4)  
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5)  
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6)  
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7)  
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8)  
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8,
   typename TArg9
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8,
   TArg9)  
);
```

### <a name="parameters"></a>パラメーター

*TDelegateInterface*  
イベントが発生したときに呼び出すデリゲートのインターフェイスを指定するテンプレート パラメーター。

*TCallback*  
オブジェクトとそのコールバック メンバー関数を表すオブジェクト型を指定するテンプレート パラメーター。

*TCallbackObject*  
イベントが発生したときに呼び出されるメソッドをメンバー関数に持つオブジェクトを指定するテンプレート パラメーター。

*TArg1*  
最初のコールバック メソッドの引数の型を指定するテンプレート パラメーター。

*TArg2*  
2 番目のコールバック メソッドの引数の型を指定するテンプレート パラメーター。

*TArg3*  
3 番目のコールバック メソッドの引数の型を指定するテンプレート パラメーター。

*TArg4*  
4 番目のコールバック メソッドの引数の型を指定するテンプレート パラメーター。

*TArg5*  
5 番目のコールバック メソッドの引数の型を指定するテンプレート パラメーター。

*TArg6*  
6 番目のコールバック メソッドの引数の型を指定するテンプレート パラメーター。

*TArg7*  
7 番目のコールバック メソッドの引数の型を指定するテンプレート パラメーター。

*TArg8*  
8 番目のコールバック メソッドの引数の型を指定するテンプレート パラメーター。

*TArg9*  
9 番目のコールバック メソッドの引数の型を指定するテンプレート パラメーター。

*コールバック*  
コールバック オブジェクトおよびそのメンバー関数を表すオブジェクト。

*object*  
イベントが発生したときにメンバー関数が呼び出されるオブジェクト。

*method*  
イベントが発生したときに呼び出すメンバー関数。

## <a name="return-value"></a>戻り値

指定されたコールバック メソッドをメンバー関数に持つオブジェクト。

## <a name="remarks"></a>Remarks

デリゲート オブジェクトの基本である必要があります`IUnknown`ではなく、`IInspectable`します。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)