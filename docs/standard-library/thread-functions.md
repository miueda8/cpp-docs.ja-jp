---
title: '&lt;thread&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- thread/std::get_id
- thread/std::sleep_for
- thread/std::sleep_until
- thread/std::swap
- thread/std::yield
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
helpviewer_keywords:
- std::get_id [C++]
- std::sleep_for [C++]
- std::sleep_until [C++]
- std::swap [C++]
- std::yield [C++]
ms.openlocfilehash: 948c00f7c0b773bf366f4ea9e102c832e9878d9b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960451"
---
# <a name="ltthreadgt-functions"></a>&lt;thread&gt; 関数

||||
|-|-|-|
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|
|[swap](#swap)|[yield](#yield)|

## <a name="get_id"></a>  get_id

現在の実行スレッドを一意に識別します。

```cpp
thread::id this_thread::get_id() noexcept;
```

### <a name="return-value"></a>戻り値

現在の実行のスレッドを一意に識別する [thread::id](../standard-library/thread-class.md) 型のオブジェクト。

## <a name="sleep_for"></a>  sleep_for

呼び出し元のスレッドをブロックします。

```cpp
template <class Rep,
class Period>
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>パラメーター

*Rel_time*  
 期間を指定する [duration](../standard-library/duration-class.md) オブジェクト。

### <a name="remarks"></a>Remarks

関数、呼び出し元のスレッドをブロックには少なくともによって指定された時間*Rel_time*します。 この関数では、例外がスローされません。

## <a name="sleep_until"></a>  sleep_until

少なくとも指定された時間まで、呼び出し元スレッドをブロックします。

```cpp
template <class Clock, class Duration>
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```

### <a name="parameters"></a>パラメーター

*Abs_time*  
 特定の時点を表します。

### <a name="remarks"></a>Remarks

この関数では、例外がスローされません。

## <a name="swap"></a>  swap

2 つの状態を交換**スレッド**オブジェクト。

```cpp
void swap(thread& Left, thread& Right) noexcept;
```

### <a name="parameters"></a>パラメーター

*左*  
 左**スレッド**オブジェクト。

*右*  
 右側**スレッド**オブジェクト。

### <a name="remarks"></a>Remarks

関数は `Left.swap(Right)` を呼び出します。

## <a name="yield"></a>  yield

現在のスレッドが通常引き続き実行される場合であっても、他のスレッドを実行するようオペレーティング システムに通知します。

```cpp
inline void yield() noexcept;
```

## <a name="see-also"></a>関連項目

[\<thread>](../standard-library/thread.md)<br/>
