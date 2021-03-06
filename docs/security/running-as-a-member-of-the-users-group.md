---
title: ユーザー グループのメンバーとして実行されている |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- PRJ0050
- VCD0047
dev_langs:
- C++
helpviewer_keywords:
- Users Group [C++]
- security [C++], Users Group
- Windows accounts [C++]
- non administrator users [C++]
- user accounts [C++]
- administrator (not running as) [C++]
ms.assetid: e48a03ec-d345-49f6-809a-1a291eecbc81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fd9d0deded3180529bfa714519a9b8d415c6b15
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586323"
---
# <a name="running-as-a-member-of-the-users-group"></a>ユーザー グループのメンバーとしての実行
Windows ユーザー アカウントを (Administrators グループではなく) Users グループのメンバーとして構成すると、悪意のあるコードに感染する可能性が低くなるため、セキュリティが強化されます。このトピックでは、そのしくみについて説明します。  
  
## <a name="security-risks"></a>セキュリティ上のリスク  
 管理者として実行するとシステムは脆弱になり、"トロイの木馬" や "バッファー オーバーラン" など、セキュリティに対するいくつかの攻撃を受けやすくなります。 インターネット サイトに管理者としてアクセスしただけで、そのインターネット サイトからダウンロードされる悪意のあるコードによってコンピューターが攻撃され、システムが破壊される恐れがあります。 このような攻撃が成功すると、管理者のアクセス許可が奪われ、すべてのファイルの削除、ハード ドライブの再フォーマット、管理者アクセス権を持つ新しいユーザー アカウントの作成などのアクションが実行される可能性があります。  
  
## <a name="non-administrator-user-groups"></a>非管理者ユーザー グループ  
 開発者が使用する Windows ユーザー アカウントは、通常は Users または Power Users グループのいずれかに追加される必要があります。 開発者は Debugging グループにも追加される必要があります。 Users グループのメンバーは、コンピューターを不要な危険にさらすことなく、プログラムを実行したり、インターネット サイトにアクセスしたりするなどの一般的なタスクを実行できます。 Power Users グループのメンバーは、アプリケーションのインストール、プリンターのインストール、コントロール パネルでの操作などのタスクも実行できます。 オペレーティング システムのアップグレード、システム パラメーターの構成などの管理者タスクを実行する必要がある場合は、管理者タスクを実行するのに適切な管理者アカウントにログインする必要があります。 Windows ではまた、 **runas**管理アクセス権を持つ特定のアプリケーションを起動するコマンドを使用できます。  
  
## <a name="exposing-customers-to-security-risks"></a>ユーザーのセキュリティ上のリスク  
 開発者は Administrators グループに属していないことが特に重要です。Administrators グループに属していなければ、開発コンピューターが保護されることに加え、開発したアプリケーションを実行するためにユーザーに対して Administrators グループに参加することを要求するコードを誤って記述することも回避されます。 開発時に導入されたコードが管理者アクセス権を必要とする場合、そのコードは実行時に失敗し、このアプリケーションを実行するにはユーザーが管理者として実行される必要があることを示す警告が表示されます。  
  
## <a name="code-that-requires-administrator-privileges"></a>管理者特権を必要とするコード  
 コードによっては、それを実行するために管理者アクセス権を必要とする場合があります。 この場合、可能であれば、その代替コードを使用して続行する必要があります。 管理者アクセス権を必要とするコード操作の例を次に示します。  
  
-   Windows または Program Files ディレクトリなど、ファイル システムの保護された領域への書き込み  
  
-   HKEY_LOCAL_MACHINE など、レジストリの保護された領域への書き込み  
  
-   グローバル アセンブリ キャッシュ (GAC: Global Assembly Cache) へのアセンブリのインストール  
  
 一般に、これらのアクションはアプリケーションのセットアップ プログラムでしか実行できないように制限されています。 これにより、ユーザーは一時的にのみ管理者ステータスを使用できます。  
  
## <a name="debugging"></a>デバッグ  
 Debugging グループのメンバーになると、Visual Studio (ネイティブおよびアンマネージ) 内で起動した任意のアプリケーションを非管理者としてデバッグできます。 また、[プロセスにアタッチ] コマンドを使用して、実行中のアプリケーションにアタッチすることもできます。 ただし、別のユーザーが起動したネイティブまたはマネージド アプリケーションをデバッグするには、Administrator グループのメンバーである必要があります。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティ推奨事項](security-best-practices-for-cpp.md)