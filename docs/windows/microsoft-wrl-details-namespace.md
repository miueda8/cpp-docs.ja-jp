---
title: Microsoft::WRL::Details Namespace |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 095d355ae26faf447b54a99437c843322efe5cb9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611749"
---
# <a name="microsoftwrldetails-namespace"></a>Microsoft::WRL::Details 名前空間

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
namespace Microsoft::WRL::Details;
```

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|名前|説明|
|----------|-----------------|
|[ComPtrRef クラス](../windows/comptrref-class.md)|ComPtr の型のオブジェクトへの参照を表す\<T >。|
|[ComPtrRefBase クラス](../windows/comptrrefbase-class.md)|基本クラスを表します、 [ComPtrRef](../windows/comptrref-class.md)クラス。|
|[DontUseNewUseMake クラス](../windows/dontusenewusemake-class.md)|演算子を使用できないように**新しい**で`RuntimeClass`します。 したがって、使用する必要があります、[関数](../windows/make-function.md)代わりにします。|
|[EventTargetArray クラス](../windows/eventtargetarray-class.md)|イベント ハンドラーの配列を表します。|
|[MakeAllocator クラス](../windows/makeallocator-class.md)|弱い参照のサポートの有無のアクティブ化可能なクラスのメモリを割り当てます。|
|[ModuleBase クラス](../windows/modulebase-class.md)|基本クラスを表します、[モジュール](../windows/module-class.md)クラス。|
|[RemoveIUnknown クラス](../windows/removeiunknown-class.md)|等価の型を作成、 `IUnknown`-ベースの型が、非仮想`QueryInterface`、 `AddRef`、および`Release`メソッド。|
|[WeakReference クラス](../windows/weakreference-class1.md)|表す、*弱い参照*Windows ランタイムまたはクラシック COM で使用できます。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。|

### <a name="structures"></a>構造体

|名前|説明|
|----------|-----------------|
|[ArgTraits 構造体](../windows/argtraits-structure.md)|インターフェイスとを指定した数のパラメーターを持つ匿名のメンバー関数は、指定したデリゲートを宣言します。|
|[ArgTraitsHelper 構造体](../windows/argtraitshelper-structure.md)|定義のデリゲート引数の一般的な特性に役立ちます。|
|[BoolStruct 構造体](../windows/boolstruct-structure.md)|定義するかどうかを`ComPtr`インターフェイスのオブジェクトの有効期間を管理します。 `BoolStruct` 内部で使用される、 [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)演算子。|
|[CreatorMap 構造体](../windows/creatormap-structure.md)|初期化し登録、およびオブジェクトの登録を解除する方法についてを説明します。|
|[DerefHelper 構造体](../windows/derefhelper-structure.md)|逆参照されたポインターを表す、`T*`テンプレート パラメーター。|
|[EnableIf 構造体](../windows/enableif-structure.md)|最初のテンプレート パラメーターが評価された場合は、2 番目のテンプレート パラメーターで指定された型のデータ メンバーを定義**true**します。|
|[FactoryCache 構造体](../windows/factorycache-structure.md)|クラス ファクトリと登録済みの Windows ランタイムまたは COM クラスのオブジェクトを識別する値の場所が含まれています。|
|[ImplementsBase 構造体](../windows/implementsbase-structure.md)|テンプレート パラメーターの型の検証に使用される[Implements 構造体](../windows/implements-structure.md)します。|
|[ImplementsHelper 構造体](../windows/implementshelper-structure.md)|により、実装、[実装](../windows/implements-structure.md)構造体。|
|[InterfaceList 構造体](../windows/interfacelist-structure.md)|インターフェイスの再帰的な一覧を作成するために使用します。|
|[InterfaceListHelper 構造体](../windows/interfacelisthelper-structure.md)|ビルド、`InterfaceList`型パラメーターの引数が指定したテンプレートの適用を再帰的にします。|
|[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)|インターフェイスの一般的な特性を実装します。|
|[InvokeHelper 構造体](../windows/invokehelper-structure.md)|実装を提供、`Invoke()`方法、指定した数値と引数の型に基づいています。|
|[IsBaseOfStrict 構造体](../windows/isbaseofstrict-structure.md)|一方の型がもう一方の型の基本クラスであるかどうかをテストします。|
|[IsSame 構造体](../windows/issame-structure.md)|別のと同じ型を指定した 1 つかどうかがテストには、種類が指定されました。|
|[Nil 構造体](../windows/nil-structure.md)|指定されていない、省略可能なテンプレート パラメーターを示すために使用されます。|
|[RemoveReference 構造体](../windows/removereference-structure.md)|指定されたクラス テンプレートのパラメーターから参照または右辺値参照の特徴を取り除きます。|
|[RuntimeClassBase 構造体](../windows/runtimeclassbase-structure.md)|検出するために使用される`RuntimeClass`で、[ように](../windows/make-function.md)関数。|
|[RuntimeClassBaseT 構造体](../windows/runtimeclassbaset-structure.md)|ヘルパー メソッドを提供します`QueryInterface`操作とのインターフェイス Id を取得します。|
|[VerifyInheritanceHelper 構造体](../windows/verifyinheritancehelper-structure.md)|1 つのインターフェイスが別のインターフェイスから派生したかどうかをテストします。|
|[VerifyInterfaceHelper 構造体](../windows/verifyinterfacehelper-structure.md)|テンプレート パラメーターで指定されたインターフェイスが特定の要件を満たしていることを確認します。|

### <a name="enumerations"></a>列挙

|name|説明|
|----------|-----------------|
|[AsyncStatusInternal 列挙型](../windows/asyncstatusinternal-enumeration.md)|非同期操作の状態の内部列挙値の間のマッピングを指定します、`Windows::Foundation::AsyncStatus`列挙体。|

### <a name="functions"></a>関数

|名前|説明|
|----------|-----------------|
|[ActivationFactoryCallback 関数](../windows/activationfactorycallback-function.md)|指定されたアクティブ化 ID のアクティベーション ファクトリを取得します。|
|[Move 関数](../windows/move-function.md)|指定した引数を 1 つの場所から移動します。|
|[RaiseException 関数](../windows/raiseexception-function.md)|呼び出し元のスレッドで例外が発生します。|
|[Swap 関数 (Windows ランタイム C++ テンプレート ライブラリ)](../windows/swap-function-windows-runtime-cpp-template-library.md)|指定された 2 つの引数の値を交換します。|
|[TerminateMap 関数](../windows/terminatemap-function.md)|指定されたモジュールでクラス ファクトリをシャット ダウンします。|

## <a name="requirements"></a>要件

**ヘッダー:** async.h、client.h、corewrappers.h、event.h、ftm.h、implements.h、internal.h、module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)  
[Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)