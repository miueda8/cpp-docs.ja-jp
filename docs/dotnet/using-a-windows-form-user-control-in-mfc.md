---
title: MFC では、ユーザー コントロールをフォーム、Windows を使用して |Microsoft Docs
ms.custom: ''
ms.date: 1/08/2018
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 795c16a46356eb9599e02b43b51066b603b8b9ce
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222109"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>MFC での Windows フォーム ユーザー コントロールの使用

MFC Windows フォームのサポート クラスを使用してホストできます Windows フォーム コントロール、MFC アプリケーション内で MFC ダイアログ ボックスまたはビュー内で ActiveX コントロールとして。 さらに、Windows フォームのフォームの場合は、MFC ダイアログ ボックスとしてホストされていることができます。

次のセクションで説明する方法。

- MFC ダイアログ ボックスでの Windows フォーム コントロールをホストします。

- MFC ビューとしての Windows フォーム ユーザー コントロールをホストします。

- MFC ダイアログ ボックスとしては、Windows フォームをホストします。

> [!NOTE]
> MFC Windows フォームの統合は、MFC と動的にリンクするプロジェクトでのみ機能 (プロジェクトを`_AFXDLL`が定義されている)。

> [!NOTE]
> MFC Windows フォーム インターフェイス (mfcmifc80.dll へ) を DLL の場合は、プライベート (変更) コピーを使用してアプリケーションをビルドするときに、ベンダー独自キーを使用して Microsoft キーを交換しない限り、GAC にインストールするには失敗します。 アセンブリの署名の詳細については、次を参照してください。[アセンブリを使ったプログラミング](/dotnet/framework/app-domains/programming-with-assemblies)と[厳密な名前のアセンブリ (アセンブリ署名) (C +/cli CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)します。

MFC アプリケーションでは、Windows フォームを使用する場合は、アプリケーションと共に mfcmifc80.dll への再配布する必要があります。 詳細については、次を参照してください。 [MFC ライブラリの再頒布](../ide/redistributing-the-mfc-library.md)します。

## <a name="in-this-section"></a>このセクションの内容

[MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)

[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

[MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="reference"></a>参照

[CWinFormsControl クラス](../mfc/reference/cwinformscontrol-class.md)

[CWinFormsDialog クラス](../mfc/reference/cwinformsdialog-class.md)

[CWinFormsView クラス](../mfc/reference/cwinformsview-class.md)

[ICommandSource インターフェイス](../mfc/reference/icommandsource-interface.md)

[ICommandTarget インターフェイス](../mfc/reference/icommandtarget-interface.md)

[ICommandUI インターフェイス](../mfc/reference/icommandui-interface.md)

[IView インターフェイス](../mfc/reference/iview-interface.md)

[CommandHandler](../atl/commandhandler.md)

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)

[UICheckState](../mfc/reference/uicheckstate-enumeration.md)

## <a name="related-sections"></a>関連項目

[Windows フォーム](/dotnet/framework/winforms/index)

[Windows フォーム コントロール](/dotnet/framework/winforms/controls/index)

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)  
[フォーム ビュー](../mfc/form-views-mfc.md)  
