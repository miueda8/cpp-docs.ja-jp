---
title: -検証-文字セット (互換性のある文字の検証) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- /validate-charset
- validate-charset
dev_langs:
- C++
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adfda3d287bbea6c85ae6d4bcebe009b610d719e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219293"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/validate-charset (互換性のある文字の検証)
ソース ファイルのテキストに表現できる文字のみが含まれていることを検証します。 utf-8 として。  
  
## <a name="syntax"></a>構文  
  
```  
/validate-charset[-]  
```  
  
## <a name="remarks"></a>Remarks  
 使用することができます、 **/validate-charset**ソース コードには、ソース文字で表現できる文字の設定し、実行文字セットのみが含まれることを検証するにはオプションです。 指定すると、このチェックが自動的に有効 **/source-charset**、 **/execution-charset**、または **/utf-8**コンパイラ オプション。 指定することでこのチェックを無効にすることが明示的に、 **/validate -文字セット-** オプション。  
  
 既定では、Visual Studio は、utf-8 または utf-16、たとえば、ソース ファイルが、エンコードされた Unicode 形式であるか判断のバイト順マークを検出します。 バイト順マークが見つからない場合は、ソース ファイルを使ってエンコードされる現在のユーザーのコード ページを使用してコード ページを指定していない限り想定しています。 **/utf-8**または **/source-charset**オプション。 Visual Studio では、いくつかの文字エン コードのいずれかを使用して、C++ ソース コードを保存できます。 ソースと実行文字セットの詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)言語ドキュメント。 一覧には、コード ページ識別子がサポートされている文字セットの名前を参照してください。[コード ページ識別子](/windows/desktop/Intl/code-page-identifiers)します。  
  
 Visual Studio では、として、ソース文字セットと、実行文字セットの間の変換中に内部の文字エンコーディング utf-8 を使用します。 Utf-8 変換が疑問符 () を置き換える場合は、実行文字セットでは、ソース ファイル内の文字を表すことができない、'?' 文字。 **/Validate-charset**オプションは、このような場合に警告をレポートにコンパイルします。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  展開、**構成プロパティ**、 **C/C++**、**コマンドライン**フォルダー。  
  
3.  **オプションの高度な**、追加、 **/validate-charset**オプション、および、使用するエンコーディングを指定します。  
  
4.  **OK** を選択して変更を保存してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/execution-charset (実行文字セット)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/source-charset (ソース文字セット)](../../build/reference/source-charset-set-source-character-set.md)   
 [/utf-8 (ソースと実行可能ファイルの文字セットを UTF-8 に設定する)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)