---
title: ATL 接続ポイント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec0e902f2b01e33ac460c6210d51c5e0637c3282
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202921"
---
# <a name="atl-connection-points"></a>ATL コネクション ポイント
接続可能オブジェクトは、着信インターフェイスをサポートしているオブジェクトです。 着信インターフェイスにより、オブジェクトはクライアントと通信できます。 着信インターフェイスごとに、接続可能なオブジェクトは接続ポイントを公開しています。 各着信インターフェイスは、シンクと呼ばれるオブジェクト上のクライアントによって実装されます。  
  
 ![接続ポイント](../atl/media/vc2zw31.gif "vc2zw31")  
  
 各接続ポイントをサポートしています、 [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)インターフェイス。 接続可能オブジェクトを使用してクライアントに接続ポイントを公開する、 [IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)インターフェイス。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ATL コネクション ポイント クラス](../atl/atl-connection-point-classes.md)  
 接続ポイントをサポートする ATL クラスを簡単に説明します。  
  
 [オブジェクトへの接続ポイントの追加](../atl/adding-connection-points-to-an-object.md)  
 オブジェクトに接続ポイントを追加するためのステップについて説明します。  
  
 [ATL コネクション ポイントの例](../atl/atl-connection-point-example.md)  
 接続ポイントの宣言の例を示します。  
  
## <a name="related-sections"></a>関連項目  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。  
  
## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)

