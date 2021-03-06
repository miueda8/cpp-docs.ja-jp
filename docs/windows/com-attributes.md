---
title: COM 属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 857e032f02102a79747b79140207d07905f5b3d2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591592"
---
# <a name="com-attributes"></a>COM 属性
COM 属性は、COM の開発と .NET Framework 共通言語ランタイムによる開発のさまざまな領域をサポートするためにコードを挿入します。 領域はこれらカスタム インターフェイスの実装と既存のインターフェイスのサポートからストック プロパティ、メソッド、およびイベントをサポートする範囲。 さらに、複合デバイスと ActiveX コントロールの実装のサポートを確認できます。
  
|属性|説明|
|---------------|-----------------|
|[aggregatable](../windows/aggregatable.md)|別のコントロールでコントロールを集計できることを示します。|
|[aggregates](../windows/aggregates.md)|コントロールがターゲット クラスを集約することを示します。|
|[coclass](../windows/coclass.md)|COM インターフェイスを実装できる COM オブジェクトを作成します。|
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|COM マップには、インターフェイスのエントリを追加します。|
|[implements_category](../windows/implements-category.md)|クラスの実装されたコンポーネントのカテゴリを指定します。|
|[progid](../windows/progid.md)|コントロールの ProgID を定義します。|
|[rdx](../windows/rdx.md)|作成またはレジストリ キーを変更します。|
|[registration_script](../windows/registration-script.md)|指定した登録スクリプトを実行します。|
|[requires_category](../windows/requires-category.md)|クラスの必須コンポーネントのカテゴリを指定します。|
|[support_error_info](../windows/support-error-info.md)|ターゲット オブジェクトのエラー報告をサポートしています。|
|[synchronize](../windows/synchronize.md)|メソッドへのアクセスを同期します。|
|[スレッド処理](../windows/threading-cpp.md)|COM オブジェクトのスレッド モデルを指定します。|
|[vi_progid](../windows/vi-progid.md)|コントロールのバージョンに依存しないプログラム Id を定義します。|
  
## <a name="see-also"></a>関連項目
 [グループ別の属性](../windows/attributes-by-group.md)