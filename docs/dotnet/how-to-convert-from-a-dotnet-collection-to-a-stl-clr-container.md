---
title: '方法: STL/CLR コンテナーを .NET コレクションから変換 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR, converting from .NET collections
- STL/CLR Containers [STL/CLR]
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8b6469c035a1f0daca5c789525778aab1119c9f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132802"
---
# <a name="how-to-convert-from-a-net-collection-to-a-stlclr-container"></a>方法: .NET コレクションを STL/CLR コンテナーに変換する
このトピックでは、同等の STL/CLR コンテナーを .NET コレクションに変換する方法を示します。 例として、.NET に変換する方法を示します<xref:System.Collections.Generic.List%601>、STL/CLR に[ベクター](../dotnet/vector-stl-clr.md) .NET を変換する方法および<xref:System.Collections.Generic.Dictionary%602>、STL/CLR に[マップ](../dotnet/map-stl-clr.md)手順はすべてのコレクションとコンテナーは似ていますが、.  
  
### <a name="to-create-a-container-from-a-collection"></a>コレクションからコンテナーを作成するには  
  
1.  コレクション全体を変換するには、STL/CLR コンテナーを作成し、コレクションをコンス トラクターに渡します。  
  
     最初の例では、この手順を示します。  
  
 または  
  
1.  作成して、汎用的な STL/CLR コンテナーを作成、 [collection_adapter](../dotnet/collection-adapter-stl-clr.md)オブジェクト。 このテンプレート クラスは、引数として .NET コレクション インターフェイスを使用します。 どのインターフェイスがサポートされていることを確認するには、次を参照してください。 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)です。  
  
2.  コンテナーを .NET コレクションの内容をコピーします。 STL/CLR を使用してこれ行う[アルゴリズム](../dotnet/algorithm-stl-clr.md)、.NET コレクションを反復処理して、STL/CLR コンテナーに各要素のコピーを挿入するか、します。  
  
     2 番目の例では、この手順を示します。  
  
## <a name="example"></a>例  
 この例では、ジェネリック型を作成<xref:System.Collections.Generic.List%601>し 5 つの要素を追加します。 次に、作成、`vector`を受け取るコンス トラクターを使用して、<xref:System.Collections.Generic.IEnumerable%601>を引数として。  
  
```  
// cliext_convert_list_to_vector.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/algorithm>  
#include <cliext/vector>  
  
using namespace System;  
using namespace System::Collections;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    List<int> ^primeNumbersColl = gcnew List<int>();  
    primeNumbersColl->Add(2);  
    primeNumbersColl->Add(3);  
    primeNumbersColl->Add(5);  
    primeNumbersColl->Add(7);  
    primeNumbersColl->Add(11);  
  
    cliext::vector<int> ^primeNumbersCont =  
        gcnew cliext::vector<int>(primeNumbersColl);  
  
    Console::WriteLine("The contents of the cliext::vector are:");  
    cliext::vector<int>::const_iterator it;  
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)  
    {  
        Console::WriteLine(*it);  
    }  
}  
```  
  
```Output  
The contents of the cliext::vector are:  
2  
3  
5  
7  
11  
```  
  
## <a name="example"></a>例  
 この例では、ジェネリック型を作成<xref:System.Collections.Generic.Dictionary%602>し 5 つの要素を追加します。 次に、作成、`collection_adapter`をラップする、<xref:System.Collections.Generic.Dictionary%602>単純な STL/CLR コンテナーとして。 最後に、作成、`map`の内容をコピーして、<xref:System.Collections.Generic.Dictionary%602>を`map`を反復処理して、`collection_adapter`です。 このプロセス中を使用して、新しいペアを作成、`make_pair`関数とに直接新しいペアを挿入、`map`です。  
  
```  
// cliext_convert_dictionary_to_map.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/algorithm>  
#include <cliext/map>  
  
using namespace System;  
using namespace System::Collections;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    System::Collections::Generic::Dictionary<float, int> ^dict =  
        gcnew System::Collections::Generic::Dictionary<float, int>();  
    dict->Add(42.0, 42);  
    dict->Add(13.0, 13);  
    dict->Add(74.0, 74);  
    dict->Add(22.0, 22);  
    dict->Add(0.0, 0);  
  
    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);  
    cliext::map<float, int> aMap;  
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)  
    {  
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);  
        aMap.insert(aPair);  
    }  
  
    Console::WriteLine("The contents of the cliext::map are:");  
    cliext::map<float, int>::const_iterator it;  
    for (it = aMap.begin(); it != aMap.end(); it++)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);  
    }  
}  
```  
  
```Output  
The contents of the cliext::map are:  
Key: 0.00 Value: 0  
Key: 13.00 Value: 13  
Key: 22.00 Value: 22  
Key: 42.00 Value: 42  
Key: 74.00 Value: 74  
```  
  
## <a name="see-also"></a>関連項目  
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)   
 [アダプター (STL/CLR)](../dotnet/adapter-stl-clr.md)   
 [方法: STL/CLR コンテナーを .NET コレクションに変換する](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)