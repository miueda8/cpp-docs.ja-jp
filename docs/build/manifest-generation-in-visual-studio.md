---
title: Visual Studio でのマニフェスト生成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f927e153c25b41b48b783281a36dd2705e42006
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205801"
---
# <a name="manifest-generation-in-visual-studio"></a>Visual Studio でのマニフェスト生成
プロジェクトでは、特定のプロジェクトのマニフェスト ファイルの生成を制御できます**プロパティ ページ**ダイアログ。 **構成プロパティ**] タブで [**リンカー**、し**マニフェスト ファイル**、し**マニフェストの生成**します。 既定では、新しいプロジェクトのプロジェクトのプロパティは、マニフェスト ファイルの生成に設定されます。 ただしを使用して、プロジェクトのマニフェストの生成を無効にすることは、**マニフェストの生成**プロジェクトのプロパティ。 このプロパティを設定すると**はい**、このプロジェクトのマニフェストが生成されます。 リンカーがアセンブリ情報を無視する、アプリケーション コードの依存関係を解決するときにそれ以外の場合、マニフェストを生成しません。  
  
 Visual Studio でビルド システムは、マニフェスト、最終的なアプリケーションでバイナリ ファイルに埋め込むか、外部ファイルとして生成するようにできます。 この動作がによって制御される、**埋め込みマニフェスト**オプション、**プロジェクトのプロパティ**ダイアログ。 このプロパティを設定するには、開く、**マニフェスト ツール**ノードを選択し、**入力し、出力**。 マニフェストが埋め込まれていない場合は、外部ファイルとして生成され、最終的なバイナリと同じディレクトリに保存します。 マニフェストが埋め込まれている場合、Visual Studio には、次のプロセスを使用して、最終的なマニフェストが埋め込まれます。  
  
1.  オブジェクト ファイルをソース コードがコンパイルされると後、リンカーは、依存アセンブリの情報を収集します。 最終的なバイナリをリンクする際に、リンカーは、後で、最終的なマニフェストの生成に使用される中間のマニフェストを生成します。  
  
2.  中間マニフェストとリンクが完了したら後、は、最終的なマニフェストをマージし、外部ファイルとして保存するマニフェストのツールが実行されます。  
  
3.  プロジェクトでは、システムを構築し、マニフェストのツールによって生成されたマニフェストがバイナリに既に埋め込まれたマニフェストは別の情報を含むかどうかを検出します。  
  
4.  マニフェストのツールによって生成されたマニフェストから異なるバイナリに埋め込まれたマニフェストを使用するか、バイナリに埋め込まれたマニフェストが含まれていない場合、Visual Studio はリンカーを呼び出し、もう一度としてバイナリ内の外部のマニフェスト ファイルに埋め込む、リソースです。  
  
5.  バイナリに埋め込まれたマニフェストがマニフェスト ツールによって生成されたマニフェストと同じ場合は、次のビルド ステップに、ビルドは続行します。  
  
 マニフェストは最終的なバイナリ文字列リソースとして埋め込まれを Visual Studio でのファイルとして、最終的なバイナリを開いて表示できます。 マニフェストを適切なライブラリを指していることを確認するには、するで説明されている手順に従います[Visual C アプリケーションの依存関係の理解](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)前または後で説明されている推奨事項、 [のトラブルシューティング](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)セクション。  
  
## <a name="see-also"></a>関連項目  
 [方法: マニフェストを C/C++ アプリケーション内に埋め込む](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [プライベート アセンブリについて](/windows/desktop/SbsCs/about-private-assemblies-)   
 [マニフェスト ツール](/windows/desktop/SbsCs/mt-exe)   
 [C/C++ プログラムのマニフェスト生成についての理解](../build/understanding-manifest-generation-for-c-cpp-programs.md)