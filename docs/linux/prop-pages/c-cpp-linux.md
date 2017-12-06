---
title: "C/C++ プロパティ (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bb8894b-c874-4a68-935e-b127d54e484f
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCClangCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCClangCompilerTool.DebugInformationFormat
- VC.Project.VCClangCompilerTool.ObjectFile
- VC.Project.VCClangCompilerTool.WarningLevel
- VC.Project.VCClangCompilerTool.WarnAsError
- VC.Project.VCClangCompilerTool.AdditionalWarning
- VC.Project.VCClangCompilerTool.Verbose
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCClangCompilerTool.Optimization
- VC.Project.VCClangCompilerTool.StrictAliasing
- VC.Project.VCClangCompilerTool.UnrollLoops
- VC.Project.VCClangCompilerTool.LinkTimeOptimization
- VC.Project.VCClangCompilerTool.OmitFramePointers
- VC.Project.VCClangCompilerTool.NoCommonBlocks
- VC.Project.VCClangCompilerTool.PIC
- VC.Project.VCClangCompilerTool.ThreadSafeStatics
- VC.Project.VCClangCompilerTool.RelaxIEEE
- VC.Project.VCClangCompilerTool.HideInlineMethods
- VC.Project.VCClangCompilerTool.SymbolsHiddenByDefault
- VC.Project.VCClangCompilerTool.ExceptionHandling
- VC.Project.VCClangCompilerTool.RuntimeTypeInfo
- VC.Project.VCClangCompilerTool.CLanguageStandard
- VC.Project.VCClangCompilerTool.CppLanguageStandard
- VC.Project.VCClangCompilerTool.PreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefineAllPreprocessorDefinitions
- VC.Project.VCClangCompilerTool.ShowIncludes
- VC.Project.VCClangCompilerTool.CompileAs
- VC.Project.VCClangCompilerTool.ForcedIncludeFiles
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: 94a22843c15e537a7af8e1e44827f8c1ab365165
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="cc-properties-linux-c"></a>C/C++ プロパティ (Linux C++)

## <a name="general"></a>全般
プロパティ | 説明 | オプション
--- | ---| ---
追加のインクルード ディレクトリ | インクルード パスに追加するディレクトリを 1 つ以上指定します。複数指定する場合には、セミコロンで区切ってください。 (-I[パス])。
デバッグ情報の形式 | コンパイラによって生成されるデバッグ情報の種類を指定します。 | **なし** - デバッグ情報が生成されないため、コンパイルが高速になる可能性があります。<br>**最小限のデバッグ情報** - 最小限のデバッグ情報を生成します。<br>**完全なデバッグ情報 (DWARF2)** - DWARF2 デバッグ情報を生成します。<br>
オブジェクト ファイル名 | 既定のオブジェクト ファイル名を上書きする名前を指定します。ファイル名またはディレクトリ名を指定できます。 (-o [名前])。
警告レベル | コード エラーに対するコンパイラの警告レベルを指定します。  その他のフラグは追加オプションに直接追加してください。 (/w, /Weverything)。 | **すべての警告を非表示にする** - すべてのコンパイラ警告を無効にします。<br>**警告をすべて有効にする** - 既定で無効にされている警告を含む、すべての警告を有効にします。<br>
警告をエラーとして扱う | コンパイラ警告をすべてエラーとして扱います。 新しいプロジェクトの場合、すべてのコンパイルで /Werror を使用することをお勧めします。すべての警告を解決することで、コードの欠陥を見逃す可能性が低くなります。
C の追加の警告 | 追加の警告メッセージのセットを定義します。
C++ の追加の警告 | 追加の警告メッセージのセットを定義します。
詳細モードを有効にする | 詳細モードを有効にすると、このツールはビルドの診断用に詳細な情報を出力します。
C コンパイラ | C ソース ファイルのコンパイル中に起動するプログラムか、またはリモート システム上の C コンパイラへのパスを指定します。
C++ コンパイラ | C++ ソース ファイルのコンパイル中に起動するプログラムか、またはリモート システム上の C++ コンパイラへのパスを指定します。
コンパイルのタイムアウト | リモート コンパイルのタイムアウト (ミリ秒)。
オブジェクト ファイルのコピー | リモート システムからローカル コンピューターにコンパイルされたオブジェクト ファイルをコピーするかどうかを指定します。

## <a name="optimization"></a>最適化
プロパティ | 説明 | オプション
--- | ---| ---
最適化 | アプリケーションの最適化レベルを指定します。 | **カスタム** - カスタムの最適化。<br>**無効** - 最適化を無効にします。<br>**サイズの最小化** - サイズを最適化します。<br>**実行速度の最大化** - 速度を最適化します。<br>**最大限の最適化** - 高価な最適化。<br>
厳密なエイリアス | 厳密なエイリアスのルールを想定します。  ある型のオブジェクトが別の型のオブジェクトと同じアドレスに存在することは決してないと想定します。
ループのアンロール | コードのサイズは大きくなりますが、実行されるブランチの数を減らすことにより、ループをアンロールしてアプリケーションの実行速度を上げます。
リンク時の最適化 | オプティマイザーがアプリケーション内の全オブジェクト ファイルを考慮に入れられるようにすることにより、プロシージャ間最適化を有効にします。
フレーム ポインターを省略する | 呼び出し履歴にフレーム ポインターが作成されなくなります。
共通ブロックなし | 初期化されていないグローバル変数さえ、共通ブロックとして生成しないでオブジェクト ファイルのデータ セクションに割り当てます。

## <a name="preprocessor"></a>プリプロセッサ
プロパティ | 説明 | オプション
--- | ---| ---
プリプロセッサの定義 | ソース ファイルの前処理シンボルを定義します。 (-D)
指定したプリプロセッサ定義の無効化 | 1 つ以上のプリプロセッサ定義の無効化を指定します。  (-U [マクロ])
すべてのプリプロセッサ定義の無効化 | すべてのプリプロセッサの定義済み定義を無効にします。  (-undef)
インクルード ファイルの表示 | コンパイラ出力を持つインクルード ファイルのリストを生成します。  (-H)

## <a name="code-generation"></a>コード生成
プロパティ | 説明 | オプション
--- | ---| ---
位置独立コード | 共有ライブラリで使用する位置独立コード (PIC) を生成します。
スタティックがスレッド セーフ | ローカル スタティックのスレッド セーフな初期化のために、追加のコードを生成し、C++ ABI で指定されたルーチンを使用します。 | **いいえ** - スレッド セーフなスタティックを無効にします。<br>**はい** - スレッド セーフなスタティックを有効にします。<br>
浮動小数点の最適化 | IEEE-754 の準拠を緩和して、浮動小数点の最適化を有効にします。
インライン メソッドの非表示 | 有効にすると、インライン メソッドの外部のコピーが 'private extern' として宣言されます。
既定でシンボルを非表示にする | '__attribute' マクロを使用してエクスポートするように明示的にマークされていない限り、すべてのシンボルが 'private extern' として宣言されます。
C++ の例外を有効にする | コンパイラで使用する例外処理のモデルを指定します。 | **いいえ** - 例外処理を無効にします。<br>**はい** - 例外処理を有効にします。<br>

## <a name="language"></a>言語
プロパティ | 説明 | オプション
--- | ---| ---
ランタイム型情報を有効にする | 実行時に C++ のオブジェクト型をチェックするコードを追加します (ランタイム型情報)。     (frtti, fno-rtti)
C 言語標準 | C 言語標準を決定します。 | **既定値**<br>**C89** - C89 言語標準。<br>**C99** - C99 言語標準。<br>**C11** - C11 言語標準。<br>**C99 (GNU 言語)** - C99 (GNU 言語) 言語標準。<br>**C11 (GNU 言語)** - C11 (GNU 言語) 言語標準。<br>
C++ 言語標準 | C++ 言語標準を決定します。 | **既定値**<br>**C++03** - C++03 言語標準。<br>**C++11** - C++11 言語標準。<br>**C++14** - C++14 言語標準。<br>**C++03 (GNU 言語)** - C++03 (GNU 言語) 言語標準。<br>**C++11 (GNU 言語)** - C++11 (GNU 言語) 言語標準。<br>**C++14 (GNU 言語)** - C++14 (GNU 言語) 言語標準。<br>

## <a name="advanced"></a>詳細設定
プロパティ | 説明 | オプション
--- | ---| ---
コンパイル言語の選択 | .c および .cpp ファイルのコンパイル言語オプションを選択します。  'Default' は .c または .cpp 拡張に基づいて検出します。 (-x c, -x c++) | **既定** - 既定。<br>**C コードとしてコンパイル** - C コードとしてコンパイルします。<br>**C++ コードとしてコンパイル** - C++ コードとしてコンパイルします。<br>
必ず使用されるインクルード ファイル | 1 つ以上の強制インクルード ファイルです (-include [名前])

## <a name="additional-options"></a>その他のオプション 