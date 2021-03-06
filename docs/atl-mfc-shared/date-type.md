---
title: 日付の種類 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DATE
dev_langs:
- C++
helpviewer_keywords:
- Date data type, implementing
- Date data type
- DATE type
- Date data type, about Date data type
- MFC, date and time
- hour values representation
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 314b943b171d43f8b1723321ac3a942ed33fd100
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883467"
---
# <a name="date-type"></a>日付型
日付型は、8 バイトの浮動小数点数を使用して実装されます。 日付は 1899 年 12 月 30 日 0 時として午前 0 時から始まる整数値の増分で表されます。 時間の値は、数値の小数部の絶対値として表現されます。 次の表は、それらの日付型の数値とと共にいくつかの日付を示しています。  
  
|日付と時刻|表現|  
|-------------------|--------------------|  
|1899 年 12 月 30日午前 0 時|0.00|  
|1900 年 1 月 1日午前 0 時|2.00|  
|1900 年 1 月 4日午前 0 時|5.00|  
|1900 年 1 月 4日午前 6 時|5.25|  
|1900 年 1 月 4日正午|5.50|  
|1900 年 1 月 4日の午後 9|5.875|  
  
 日付の日付型だけでなく`COleDateTime`クラスを表す日付とクラシックの数直線として時刻。 `COleDateTime`クラスにはとその他の一般的な日付形式の間の変換などの日付の値を操作するためのいくつかのメソッドが含まれています。  
  
 Automation でこれらの日付と時刻の形式を使用する場合、次の点に注意します。  
  
-   ローカル時刻で日付を指定します。異なるタイム ゾーンの日付を扱うときに、同期を手動で実行する必要があります。  
  
-   夏時間には、日付型は考慮されません。  
  
-   日付のタイムラインになります (30 1899 年 12 月) の前に 0 未満の日付値を連続していません。 日付値の整数部分が署名済み、小数部分の処理中にものとして扱われるため、これは符号なしとします。 つまり、日付の値の整数部分があります正または負の場合、日付の値の小数部は常に、全体的な論理日付を追加中に。 次の表は、いくつかの例を示しています。  
  
|日付と時刻|表現|  
|-------------------|--------------------|  
|1899 年 12 月 27日午前 0 時|-3.00|  
|28 1899 年 12 月、正午|-2.50|  
|1899 年 12 月 28日午前 0 時|-2.00|  
|1899 年 12 月 29日午前 0 時|-1.00|  
|1899 年 12 月 30日午後 6 時|-0.75|  
|1899 年 12 月 30日正午|-0.50|  
|1899 年 12 月 30日午前 6 時|-0.25|  
|1899 年 12 月 30日午前 0 時|0.00|  
|1899 年 12 月 30日午前 6 時|0.25|  
|1899 年 12 月 30日正午|0.50|  
|1899 年 12 月 30日午後 6 時|0.75|  
|1899 年 12 月 31日午前 0 時|1.00|  
|1900 年 1 月 1日午前 0 時|2.00|  
|1900 年 1 月 1日正午|2.50|  
|1900 年 1 月 2日午前 0 時|3.00|  
  
> [!CAUTION]
>  6時 00分 AM がかどうか、1 日を表す整数が正の値 (1899 年 12 月 30 日) の後に関係なく 0.25 小数値で表される常にまたは負の値 (1899 年 12 月 30 日) の前に、単純な浮動ポイントの比較は誤って並べ替えために注意してください。任意の日付として 12/30/1899 より前の日に 6時 00分 AM を表す*後*同じ日に 7時 00分 AM を表す日付よりもします。  
  
 問題の詳細については、日付に関連して`COleDateTime`型は、「 [COleDateTime クラス](../atl-mfc-shared/reference/coledatetime-class.md)と[日付と時刻: オートメーション サポート](../atl-mfc-shared/date-and-time-automation-support.md)。  
  
## <a name="see-also"></a>関連項目  
 [日付と時刻](../atl-mfc-shared/date-and-time.md)   
 [COleDateTime クラス](../atl-mfc-shared/reference/coledatetime-class.md)

