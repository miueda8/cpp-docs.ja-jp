---
title: コンボ ボックスとドロップダウン リストのサイズの設定 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.combo
dev_langs:
- C++
helpviewer_keywords:
- combo boxes, sizing
- controls [C++], sizing
ms.assetid: 51fb53cf-9ddf-4a20-962e-8553938e55ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8ecc04f0e8bda3045dcad141fa3fe467039c3f23
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605561"
---
# <a name="setting-the-size-of-the-combo-box-and-its-drop-down-list"></a>コンボ ボックスとドロップダウン リストのサイズの設定

ダイアログ ボックスを追加すると、コンボ ボックスを調整することができます。 ドロップダウン リスト ボックスのサイズを指定することもできます。

### <a name="to-size-a-combo-box"></a>コンボ ボックスのサイズ

1. ダイアログ ボックスで、コンボ ボックス コントロールを選択します。

   最初に、左右のサイズ変更ハンドルのみがアクティブです。

2. コンボ ボックスの幅を設定するのにには、サイズ変更ハンドルを使用します。

コンボ ボックスのドロップダウン部分の縦のサイズを設定することもできます。

#### <a name="to-set-the-size-of-the-combo-box-drop-down-list"></a>コンボ ボックスのサイズのボックスのドロップダウン リストを設定するには

1. コンボ ボックスの右側にある下矢印ボタンをクリックします。

   ![MFC プロジェクト コンボ ボックスの矢印](../mfc/media/vccomboboxarrow.gif "vcComboBoxArrow")

   拡張領域のドロップダウンの一覧をコンボ ボックスのサイズを表示するコントロールの変更の概略です。

2. 下のサイズ変更ハンドルを使用すると、ドロップダウン リストの領域の初期サイズを変更できます。

   ![コンボ&#45;MFC プロジェクトで、ボックスのサイズ変更](../mfc/media/vccomboboxsizing.gif "vcComboBoxSizing")

3. コンボ ボックスのドロップダウン リストの部分を終了するには、もう一度ドロップダウン矢印をクリックします。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[コンボ ボックス コントロールへの値の追加](../windows/adding-values-to-a-combo-box-control.md)  
[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)  
[コントロール](../mfc/controls-mfc.md)