---
title: 同時実行ランタイムでの一般的なベスト プラクティス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, general best practices
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2cd9cffa76ce179f478422af9c8efce380a2465
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694119"
---
# <a name="general-best-practices-in-the-concurrency-runtime"></a>同時実行ランタイムに関する全般的なベスト プラクティス
ここでは、同時実行ランタイムの複数の領域に適用されるベスト プラクティスについて説明します。  
  
##  <a name="top"></a> セクション  
 このドキュメントは、次のトピックに分かれています。  
  
- [可能であれば協調的同期コンストラクトを使用します。](#synchronization)  
  
- [譲渡なしで実行時間のかかるタスクを回避します。](#yield)  
  
- [オーバー サブスクリプションをブロックまたは待機時間の長いオフセットの操作を使用します。](#oversubscription)  
  
- [使用可能な場合は、同時実行メモリ管理関数](#memory)  
  
- [RAII を使用して、同時実行オブジェクトの有効期間を管理するには](#raii)  
  
- [グローバル スコープで同時実行オブジェクトを作成できません。](#global-scope)  
  
- [共有データ セグメントで同時実行オブジェクトを使用しないでください。](#shared-data)  
  
##  <a name="synchronization"></a> 可能であれば協調的同期コンストラクトを使用します。  
 同時実行ランタイムには、外部同期オブジェクトを必要としない同時実行セーフのコンストラクトが多数用意されています。 たとえば、 [::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)クラスは、同時実行セーフの追加と操作へのアクセスの要素。 ただし、リソースへの排他アクセスを必要とする場合、ランタイムは、提供、 [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md)、 [:reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)、および[同時実行: イベント](../../parallel/concrt/reference/event-class.md)クラスです。 これらの型は協調的に動作するため、タスク スケジューラは、最初のタスクがデータを待っている間、処理リソースを別のコンテキストに再割り当てすることができます。 可能であれば、協調的に動作しない他の同期機構 (Windows API に用意されている同期機構など) の代わりに、これらの同期型を使用してください。 これらの同期型およびコード例の詳細については、次を参照してください。[同期データ構造](../../parallel/concrt/synchronization-data-structures.md)と[を比較する同期データ構造体を、Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="yield"></a> 譲渡なしで実行時間のかかるタスクを回避します。  
 タスク スケジューラは協調的に動作するため、タスク間で公平性は保たれません。 したがって、1 つのタスクが原因で他のタスクを開始できなくなることがあります。 このような状況は許容される場合もありますが、デッドロックやスタベーションを引き起こす場合もあります。  
  
 次の例では、割り当てられている処理リソースの数を超えるタスクを実行します。 1 つ目のタスクはタスク スケジューラに譲渡しないため、そのタスクが終了するまで 2 つ目のタスクは開始されません。  
  
 [!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
 1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000  
  

 いくつかの方法を使用して、2 つのタスク間の協調を有効にすることができます。 1 つは、長時間実行されるタスクの中でタスク スケジューラに譲渡する時間を不定期に設けることです。 次の例を変更、`task`関数を呼び出して、 [:yield](reference/context-class.md#yield)メソッドを別のタスクが実行できるように、タスク スケジューラに実行を譲渡します。  

  
 [!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_2.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
1: 250000000  
2: 250000000  
1: 500000000  
2: 500000000  
1: 750000000  
2: 750000000  
1: 1000000000  
2: 1000000000  
```  
  
 `Context::Yield` メソッドが譲渡するのは、現在のスレッドが属しているスケジューラ上の別のアクティブ スレッド、軽量タスク、または別のオペレーティング システム スレッドのみです。 このメソッドには譲渡しません作業実行がスケジュールされている、 [concurrency::task_group](reference/task-group-class.md)または[concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)オブジェクトしますが、まだ開始されていません。  
  
 他の方法を使用して、長時間実行されるタスク間の協調を有効にすることもできます。 大きなタスクを小さなサブタスクに分割できます。 また、時間のかかるタスクの中でオーバーサブスクリプションを有効にすることもできます。 オーバーサブスクリプションを使用すると、使用可能なハードウェア スレッドよりも多くのスレッドを作成できます。 オーバーサブスクリプションは、長時間実行されるタスクの中で非常に長い待機時間 (ディスクやネットワーク接続からのデータの読み取りなど) が発生するような場合に特に役立ちます。 軽量タスクとオーバー サブスクリプションに関する詳細については、次を参照してください。[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="oversubscription"></a> オーバー サブスクリプションをブロックまたは待機時間の長いオフセットの操作を使用します。  
 同時実行ランタイムがなどの同期プリミティブを提供[concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md)、協調的ブロッキングや譲渡を互いにタスクを有効にします。 最初のタスクが協調的なブロッキングや譲渡を行った場合、タスク スケジューラは、そのタスクがデータを待っている間、処理リソースを別のコンテキストに再割り当てすることができます。  
  
 同時実行ランタイムに用意されている協調的ブロッキング機構を使用できない場合もあります。 たとえば、使用する外部ライブラリによっては、別の同期機構が使用されることがあります。 別の例としては、Windows API `ReadFile` 関数を使用してネットワーク接続からデータを読み取る場合など、非常に長い待機時間が発生するような操作を実行する場合です。 このような場合、オーバーサブスクリプションを使用して、該当するタスクがアイドル状態のときに他のタスクが実行されるようにすることができます。 オーバーサブスクリプションを使用すると、使用可能なハードウェア スレッドよりも多くのスレッドを作成できます。  
  
 次の関数 `download` について考えます。この関数では、特定の URL にあるファイルをダウンロードします。 この例では、 [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe)メソッドを一時的にアクティブなスレッド数を増やします。  

 [!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_3.cpp)]  
  
 `GetHttpFile` 関数は潜在的な操作を実行するため、オーバーサブスクリプションを使用することで、現在のタスクがデータを待っている間、他のタスクを実行できるようになります。 この例の完全なバージョンを参照してください。[する方法: を使用して、オーバー サブスクリプション待機時間のオフセットを](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="memory"></a> 使用可能な場合は、同時実行メモリ管理関数  

 メモリ管理関数を使用して[concurrency::alloc](reference/concurrency-namespace-functions.md#alloc)と[concurrency::free](reference/concurrency-namespace-functions.md#free)有効期間が比較的短い小さなオブジェクトを頻繁に割り当てる粒度の細かいタスクがあるときに、します。 同時実行ランタイムでは、実行中のスレッドごとに別個のメモリ キャッシュが保持されます。 `Alloc` 関数と `Free` 関数は、ロックやメモリ バリアを使用することなく、これらのキャッシュからメモリの割り当てと解放を行います。  
  
 これらのメモリ管理機能の詳細については、次を参照してください。[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)です。 これらの関数を使用する例は、次を参照してください。[する方法: 使用 Alloc と Free メモリ パフォーマンスを向上させる](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="raii"></a> RAII を使用して、同時実行オブジェクトの有効期間を管理するには  
 同時実行ランタイムでは、例外処理を使用して、取り消し処理などの機能を実装します。 したがって、ランタイムを呼び出す場合や、ランタイムを呼び出す別のライブラリを呼び出す場合は、例外セーフなコードを記述してください。  
  
 *Resource Acquisition Is Initialization* (RAII) パターンは、特定のスコープで同時実行オブジェクトの有効期間を安全に管理する方法の 1 つです。 RAII パターンでは、データ構造はスタック上に割り当てられます。 データ構造は、作成されたときにリソースを初期化または取得し、破棄されたときにそのリソースを破棄または解放します。 RAII パターンでは、外側のスコープが終了する前に、常にデストラクターが呼び出されます。 このパターンは、関数に複数の `return` ステートメントが含まれる場合に便利です。 また、このパターンは、例外セーフなコードを記述するのにも役立ちます。 `throw` ステートメントによってスタックがアンワインドされると、RAII オブジェクトのデストラクターが呼び出されます。そのため、リソースが常に正しく削除または解放されます。  
  
 など、RAII パターンを使用するいくつかのクラスを定義して、ランタイム[concurrency::critical_section::scoped_lock](../../parallel/concrt/reference/critical-section-class.md#critical_section__scoped_lock_class)と[concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class)です。 これらのヘルパー クラスと呼ばれる*スコープ ロック*です。 使用する場合、これらのクラスがいくつかの利点を提供[concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md)または[:reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)オブジェクト。 これらのクラスのコンストラクターは、提供された `critical_section` オブジェクトまたは `reader_writer_lock` オブジェクトへのアクセスを取得し、デストラクターはそのオブジェクトへのアクセスを解放します。 相互排他オブジェクトが破棄されると、スコープ ロックはそのオブジェクトへのアクセスを自動的に解放するため、基になるオブジェクトのロックを手動で解除する必要はありません。  
  
 次のクラス `account` について考えます。このクラスは、外部ライブラリで定義されているため、変更できません。  
  
 [!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_4.h)]  
  
 次の例では、`account` オブジェクトに対して複数のトランザクションを並列に実行します。 この例では、`critical_section` オブジェクトを使用して、`account` オブジェクトへのアクセスを同期します。`account` クラスは同時実行セーフではないためです。 各並列操作では、`critical_section::scoped_lock` オブジェクトを使用して、操作が成功または失敗したときに `critical_section` オブジェクトのロックが確実に解除されるようにします。 口座残高が負の場合、`withdraw` 操作は例外をスローして失敗します。  
  
 [!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_5.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
```Output  
Balance before deposit: 1924  
Balance after deposit: 2924  
Balance before withdrawal: 2924  
Balance after withdrawal: -76  
Balance before withdrawal: -76  
Error details:  
    negative balance: -76  
```  
  
 同時実行オブジェクトの有効期間を管理する、RAII パターンを使用するその他の例では、次を参照してください[チュートリアル: ユーザー インターフェイス スレッドからの処理の除去](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)、[する方法: Context クラスを使用して協調的に実装するには。セマフォ](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)、および[する方法: オーバー サブスクリプションを使用して、待機時間のオフセットを](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="global-scope"></a> グローバル スコープで同時実行オブジェクトを作成できません。  
 グローバル スコープで同時実行オブジェクトを作成すると、アプリケーションでデッドロックやメモリ アクセス違反などの問題が発生する可能性があります。  
  
 たとえば、同時実行ランタイム オブジェクトの作成時にスケジューラがまだ作成されていない場合、既定のスケジューラが作成されます。 グローバル オブジェクトの構築時に作成されるランタイム オブジェクトにより、ランタイムがこの既定のスケジューラを作成します。 ただし、このプロセスでは内部ロックが使用され、同時実行ランタイムのインフラストラクチャをサポートする他のオブジェクトの初期化を妨げる可能性があります。 まだ初期化されていない別のインフラストラクチャ オブジェクトでこの内部ロックが必要になる場合があるため、アプリケーションでデッドロックが発生する可能性があります。  
  
 次の例では、グローバルの作成[concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)オブジェクト。 このパターンは、`Scheduler` クラスだけでなく、同時実行ランタイムに用意されている他のすべての型にも適用されます。 このパターンはアプリケーションの予期しない動作を引き起こす可能性があるため、使用しないことをお勧めします。  
  
 [!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_6.cpp)]  
  
 作成するための正しい方法の例については`Scheduler`、オブジェクトを参照してください[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="shared-data"></a> 共有データ セグメントで同時実行オブジェクトを使用しないでください。  
 同時実行ランタイムは、共有データ セクションによって作成されるデータのセクションなどでの同時実行オブジェクトの使用をサポートしていません、 [data_seg](../../preprocessor/data-seg.md) `#pragma`ディレクティブです。 同時実行オブジェクトがプロセス境界をまたいで共有される場合、ランタイムが不整合な状態または無効な状態になる可能性があります。  
  
 [[トップ](#top)]  
  
## <a name="see-also"></a>関連項目  
 [同時実行ランタイムに関するベスト プラクティスします。](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [同期データ構造](../../parallel/concrt/synchronization-data-structures.md)   
 [Windows API の同期データ構造との比較](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)   
 [方法: Alloc を使用してメモリ パフォーマンスを改善するために解放し](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)   
 [方法: オーバー サブスクリプションを使用して、待機時間のオフセットを](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)   
 [方法: Context クラスを使用して協調セマフォを実装するには](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [チュートリアル: ユーザー インターフェイス スレッドからの処理の除去](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)   
 [並列パターン ライブラリに関するベスト プラクティス](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [非同期エージェント ライブラリに関するベスト プラクティス](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)
