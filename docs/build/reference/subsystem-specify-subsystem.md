---
title: -SUBSYSTEM (サブシステムの指定) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
dev_langs:
- C++
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ebfbd7e8cedd522c324743abc5c28c6ac3e9f2b0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200389"
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (サブシステムの指定)
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT_APPLICATION  
 Windows のブート環境で実行するアプリケーションです。 ブート アプリケーションの詳細については、次を参照してください。 [About BCD](/previous-versions/windows/desktop/bcd/about-bcd)します。  
  
 CONSOLE  
 Win32 文字モード アプリケーションに対して使用します。 オペレーティング システムには、コンソール アプリケーションのコンソールが用意されています。 ネイティブ コードに `main` または `wmain` が定義されている場合、マネージド コードに `int main(array<String ^> ^)` が定義されている場合、または `/clr:safe` を使用してアプリケーションを完全にビルドする場合、CONSOLE が既定の設定になります。  
  
 拡張可能なファームウェア インターフェイス  
 EFI_* サブシステムです。 詳細については、EFI の仕様を参照してください。 たとえば、Intel の Web サイトなどを参照してください。 最小および既定のバージョンは 1.0 です。  
  
 NATIVE  
 Windows NT 用のカーネル モード ドライバーです。 このオプションは、通常、Windows システム コンポーネントのために予約されています。 場合[/DRIVER:WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md)を指定すると、既定では、ネイティブです。  
  
 POSIX  
 Windows NT 上の POSIX サブシステムで実行するアプリケーションです。  
  
 WINDOWS  
 アプリケーションにはコンソールは不要です。このシステムにはユーザーとの対話用のウィンドウが作成されるからです。 ネイティブ コードに `WinMain` または `wWinMain` が定義されている場合、あるいはマネージド コードに `WinMain(HISTANCE *, HINSTANCE *, char *, int)` または `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` が定義されている場合、WINDOWS が既定の設定になります。  
  
 `Major` および `minor` (省略可能)  
 サブシステムに最低限必要なバージョンを指定します。 引数には、0 ～ 65535 の範囲の 10 進数を指定します。 詳細については、「解説」を参照してください。 バージョン番号に上限はありません。  
  
## <a name="remarks"></a>Remarks  
 /SUBSYSTEM オプションは、実行可能ファイルの環境を指定します。  
  
 サブシステムの選択によって、リンカーが選択するエントリ ポイント シンボル (またはエントリ ポイント関数) が決まります。  
  
 サブシステムに必要な最小限の既定の `major` および `minor` のバージョン番号は以下のとおりです。  
  
|サブシステム|最小要件|既定値|  
|---------------|-------------|-------------|  
|BOOT_APPLICATION|1|1|  
|CONSOLE|(x86) 5.01 (x64) 5.02 6.02 です (ARM)|(x86、x64) は 6.00 6.02 です (ARM)|  
|WINDOWS|(x86) 5.01 (x64) 5.02 6.02 です (ARM)|(x86、x64) は 6.00 6.02 です (ARM)|  
|NATIVE (DRIVER:WDM を使用する場合)|(x86) 1.00 1.10 (x64、ARM)|(x86) 1.00 1.10 (x64、ARM)|  
|NATIVE (/DRIVER:WDM を使用しない場合)|(x86) 4.00 (x64) 5.02 6.02 です (ARM)|(x86) 4.00 (x64) 5.02 6.02 です (ARM)|  
|POSIX|1|19.90|  
|EFI_APPLICATION、EFI_BOOT_SERVICE_DRIVER、EFI_ROM、EFI_RUNTIME_DRIVER|1|1|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。  
  
2.  [リンカー] フォルダーを選択します。  
  
3.  選択、**システム**プロパティ ページ。  
  
4.  `SubSystem` プロパティを変更します。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)