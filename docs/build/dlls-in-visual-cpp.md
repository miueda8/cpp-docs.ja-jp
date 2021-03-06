---
title: Visual C の Dll |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4554ae6aab9a6d8d488607ab22c26460116c751d
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2018
ms.locfileid: "42572890"
---
# <a name="dlls-in-visual-c"></a>Visual C++ の DLL  
  
Windows では、ダイナミック リンク ライブラリ (DLL) はある種の関数とリソースの共有ライブラリとして機能する実行可能ファイルです。 関数を呼び出すか、別のファイルに格納されているリソースを使用する実行可能ファイルを使用するオペレーティング システムの機能は、動的リンクします。 これらの関数とリソースはコンパイルできるだけでなく、これらを使用する実行可能ファイルとは別に配置することができます。 DLL がないスタンドアロン実行可能ファイルです。これを呼び出すアプリケーションのコンテキストで実行されます。 オペレーティング システムは、アプリケーションが読み込まれるときに、アプリケーションのメモリ領域の DLL を読み込むことができます (*暗黙的リンク*)、または実行時にオンデマンドで (*明示的リンク*)。 また、DLL は、実行可能ファイル間で関数とリソースを共有しやすくします。 メモリ内の DLL の内容には、同時に複数のアプリケーションがアクセスできます。  
  
## <a name="differences-between-dynamic-linking-and-static-linking"></a>動的リンクと、静的リンク間の違い  
  
静的リンク オブジェクトのすべてのコードをスタティック ライブラリで構築されているときに使用できる実行可能ファイルにコピーします。 動的リンクには、Windows で実行時に検索して、データ項目または関数を含む DLL を読み込むために必要な情報のみが含まれています。 DLL を作成するときに、この情報を含むインポート ライブラリを作成します。 DLL を呼び出す実行可能ファイルをビルドすると、リンカーは、Windows ローダーは、この情報を格納するのにインポート ライブラリにエクスポートされたシンボルを使用します。 ローダーが DLL を読み込むときに、DLL は、アプリケーションのメモリ領域にマップされます。 存在する場合、特殊な関数、DLL `DllMain`DLL が必要です。 初期化を行うには呼び出されます。  
  
<a name="differences-between-applications-and-dlls"></a>  
  
## <a name="differences-between-applications-and-dlls"></a>アプリケーションと Dll の違い  
  
Dll とアプリケーションは、両方の実行可能モジュールには、いくつかの方法が異なります。 ユーザーが、最も明白な違いは、Dll は直接実行できるアプリケーションではありません。 システム側から見ると、アプリケーションと DLL には次の 2 つの根本的な違いがあります。  
  
-   アプリケーションはシステム内で稼働する複数のインスタンスを同時に持つことができるのに対し、DLL のインスタンスは 1 つしかありません。  
  
-   など、スタック、スレッドの実行、グローバル メモリ、ファイル ハンドル、およびメッセージ キューを所有できるプロセスとしてアプリケーションを読み込むことができますが、DLL ことはできません。  
  
<a name="advantages-of-using-dlls"></a>  
  
## <a name="advantages-of-using-dlls"></a>Dll の利点  
  
いくつかの利点を提供するコードとリソースに静的リンクではなく動的にリンクします。 DLL を使用すると、メモリ領域を節約し、スワップを低減できます。 複数のアプリケーションが DLL の 1 つのコピーを使用すると、ディスク領域とダウンロードの帯域幅を節約することができます。 DLL は、個別に配置および更新できます。これにより、すべてのコードのリビルドと出荷をしなくても、出荷後のサポートとソフトウェアの更新プログラムを提供することができます。 DLL は、ロケール固有のリソースを指定する便利な方法です。多言語のプログラムをサポートし、アプリケーションの各国語バージョンを簡単に作成することができます。 明示的リンクを許可するアプリケーションを検出し、新しい機能を提供する拡張機能など、実行時に Dll を読み込むことができます。  
  
動的リンクには、以下の利点があります。  
  
-   動的リンクと、メモリを節約し、スワップ処理を抑制します。 多くのプロセスでは、DLL を同時に使用できるため、メモリ内の DLL の読み取り専用の部分の 1 つのコピーを共有します。 これに対し、静的にリンクされたライブラリを使用して組み込まれているすべてのアプリケーションは、Windows がメモリに読み込む必要があるライブラリ コードの完全なコピーを保持します。  
  
-   動的リンクには、ディスク領域と帯域幅が節約できます。 複数のアプリケーションが、ディスク上の DLL を共有できます。 これに対し、スタティック リンク ライブラリを使用してビルドされたアプリケーションより多くのディスク領域を使用し、転送する多くの帯域幅は、実行可能ファイル、イメージにリンクされているライブラリ コードがあります。  
  
-   メンテナンス、セキュリティの修正プログラムし、アップグレードが簡単になります。 アプリケーションでは、DLL 内で共通の関数を使用するときに関数の引数と戻り値は変更しない限り、限りできますバグの修正を実装し、DLL への更新プログラムの展開します。 Dll が更新されると、それらを使用するアプリケーションは、再コンパイルや再リンクすると、必要はありませんし、新しい DLL が展開されているとすぐに使用します。 これに対し、静的にリンクされたオブジェクト コードの修正には、再リンクして、それを使用するすべてのアプリケーションを再デプロイすることが必要です。  
  
-   出荷のサポートを提供するのに Dll を使用することができます。 たとえば、アプリケーションの出荷時には利用できなかったディスプレイをサポートするよう、ディスプレイ ドライバー DLL を後から変更することもできます。 明示的リンクを使用して、Dll としてのアプリケーションの拡張機能を読み込むしを再構築または再デプロイせず、新しい機能をアプリに追加できます。  
  
-   動的リンクすると、さまざまなプログラミング言語で記述されたアプリケーションをサポートしやすきます。 異なるプログラミング言語で書かれたプログラムでも、関数の呼び出し規則に従う限り、同じ DLL 関数を呼び出すことができます。 ただし、引数がスタックにプッシュされる順序、スタックのクリアをアプリケーションと関数のどちらが行うか、引数のレジスタ渡しの有無に関しては、使用する側のプログラムと DLL 関数の間に互換性が成立している必要があります。  
  
-   動的リンクは、MFC ライブラリ クラスを拡張するためのメカニズムを提供します。 既存の MFC クラスの派生クラスを作成し、MFC アプリケーションから使用可能な MFC 拡張 DLL に配置できます。  
  
-   動的リンクと、アプリケーションの各国語バージョンの作成が簡単にできます。 DLL のロケール固有のリソースを配置すると、アプリケーションの各国語バージョンを作成するはるかに簡単です。 多くのローカライズされたバージョンのアプリケーションを配布するには、代わりに別のリソース DLL に文字列と言語ごとにイメージを配置してし、アプリケーションが実行時にそのロケールの適切なリソースを読み込むことができます。   
  
 Dll を使用する潜在的なデメリットは、アプリケーションが自己完結していること配置またはインストールの一部として自分で確認する必要がある個別の DLL モジュールの存在に依存します。  
  
  
## <a name="more-information-on-how-to-create-and-use-dlls"></a>作成して Dll を使用する方法の詳細について  
  
次のトピックでは、Visual c dll のプログラミン方法に関する詳細を説明します。  
  
 [チュートリアル: ダイナミック リンク ライブラリの作成と使用 (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
 Visual Studio を使用して DLL を作成および使用する方法について説明します。  
  
 [DLL の種類](../build/kinds-of-dlls.md)  
 ビルドできる各種 DLL に関する情報を提供します。  
  
 [DLL のよく寄せられる質問](../build/dll-frequently-asked-questions.md)  
 DLL に関してよく寄せられる質問への回答を示します。  
  
 [実行可能ファイルと DLL のリンク](../build/linking-an-executable-to-a-dll.md)  
 DLL との明示的なリンクと暗黙的なリンクについて説明します。  
  
 [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)  
 DLL の読み込み時に実行する必要があります DLL の初期化コードをについて説明します。  
  
 [DLL と Visual C++ ランタイム ライブラリの動作](../build/run-time-library-behavior.md)  
 ランタイム ライブラリで DLL の起動処理をどのように実行するかについて説明します。  
  
 [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
 使用について説明**LoadLibrary**と`AfxLoadLibrary`実行時に DLL を明示的にリンクします。  
  
 [GetProcAddress](../build/getprocaddress.md)  
 使用について説明**GetProcAddress** DLL でエクスポートされた関数のアドレスを取得します。  
  
 [FreeLibrary と AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
 使用について説明**FreeLibrary**と`AfxFreeLibrary`DLL モジュールが不要になった場合。  
  
 [ダイナミック リンク ライブラリの検索順序](/windows/desktop/Dlls/dynamic-link-library-search-order)  
 Windows オペレーティング システムがシステム上の DLL を検索するために使用する検索パスについて説明します。  
  
 [MFC と動的にリンクされるレギュラー MFC DLL のモジュール状態](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
 MFC と動的にリンクされている MFC DLL の通常のモジュールの状態について説明します。  
  
 [MFC 拡張 DLL](../build/extension-dlls-overview.md)  
 既存の MFC ライブラリ クラスから派生した再利用可能なクラスを主に実装する DLL について説明します。  
  
 [リソースのみの DLL の作成](../build/creating-a-resource-only-dll.md)  
 アイコン、ビットマップ、文字列、ダイアログ ボックスなどのリソースだけを含む、リソースのみの DLL について説明します。  
  
 [MFC アプリケーションのローカライズされたリソース: サテライト DLL](../build/localized-resources-in-mfc-applications-satellite-dlls.md)  
 混合言語にローカライズされるアプリケーションの作成に役立つ、サテライト DLL のサポートを強化します。  
  
 [インポートとエクスポート](../build/importing-and-exporting.md)  
 アプリケーションへのパブリック シンボルのインポート、または DLL からの関数のエクスポートについて説明します。  
  
 [Active テクノロジと DLL](../build/active-technology-and-dlls.md)  
 オブジェクト サーバーを DLL 内部に実装できます。  
  
 [DLL でのオートメーション](../build/automation-in-a-dll.md)  
 MFC DLL ウィザードの [オートメーション] オプションについて説明します。  
  
 [MFC DLL の名前付け規則](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)  
 MFC に含まれる DLL やライブラリに適用される一定の名前付け規則について説明します。  
  
 [Visual Basic アプリケーションから DLL 関数を呼び出す](../build/calling-dll-functions-from-visual-basic-applications.md)  
 Visual Basic アプリケーションから DLL 関数を呼び出す方法について説明します。  
  
## <a name="related-sections"></a>関連項目  
  
 [DLL の一部としての MFC の使用](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
 MFC ライブラリを Windows ダイナミック リンク ライブラリの一部として使用することができますが、レギュラー MFC Dll について説明します。  
  
 [MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)  
 MFCxx.dll を使用して MFCxxD.dll (x は MFC のバージョン番号です) は、MFC アプリケーションや MFC 拡張 Dll とダイナミック リンク ライブラリを共有する方法について説明します。  
