---
title: ユーザー定義の属性 (C++ コンポーネント拡張) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- metadata, extending
- custom attributes, extending metadata
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 605759e241498e83174f4d6b16435c3119c56671
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600382"
---
# <a name="user-defined-attributes--c-component-extensions"></a>ユーザー定義の属性 (C++ コンポーネント拡張)

カスタム属性を使用すると、インターフェイス、クラスまたは構造体、メソッド、パラメーター、または列挙型のメタデータを拡張できます。

## <a name="all-runtimes"></a>すべてのランタイム

すべてのランタイムは、カスタム属性をサポートします。

## <a name="windows-runtime"></a>Windows ランタイム

C + + CX 属性のプロパティのみをサポートがない属性のコンス トラクターまたはメソッドです。

### <a name="remarks"></a>Remarks

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

カスタム属性を使用して、管理対象の要素のメタデータを拡張できます。 詳細については、「[属性](/dotnet/standard/attributes/index)」を参照してください。

### <a name="remarks"></a>Remarks

情報と、このトピックで示した構文で説明する情報を置き換えるものでは[属性](../windows/attribute.md)します。

カスタム属性を定義するには、型を定義して<xref:System.Attribute>型と、必要に応じて、基本クラスを適用する、<xref:System.AttributeUsageAttribute>属性。

などの Microsoft サーバー (MTS Transaction) 1.0 では、トランザクション、同期、に関する動作の負荷分散とでは、ODL カスタム属性を使用してタイプ ライブラリに追加されたカスタム Guid により指定されました。 そのため、MTS サーバーのクライアントでは、タイプ ライブラリを参照してその特性を決定でした。 .NET framework では、タイプ ライブラリのアナログはメタデータで、ODL カスタム属性のアナログはカスタム属性です。 また、タイプ ライブラリを読み取り、型でリフレクションを使用してに似ています。

詳細については、次のトピックを参照してください。

- [属性の対象](../windows/attribute-targets-cpp-component-extensions.md)

- [属性パラメーターの型](../windows/attribute-parameter-types-cpp-component-extensions.md)

Visual C でのアセンブリへの署名については、次を参照してください。[厳密な名前のアセンブリ (アセンブリ署名) (C +/cli CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)します。

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

次の例では、カスタム属性を定義する方法を示します。

```cpp
// user_defined_attributes.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
ref struct Attr : public Attribute {
   Attr(bool i){}
   Attr(){}
};

[Attr]
ref class MyClass {};
```

次の例では、カスタム属性のいくつかの重要な機能を示します。 たとえば、この例は、カスタム属性の一般的な使用方法を示しています。: 完全に記述できる自体をクライアントにサーバーをインスタンス化します。

```cpp
// extending_metadata_b.cpp
// compile with: /clr
using namespace System;
using namespace System::Reflection;

public enum class Access { Read, Write, Execute };

// Defining the Job attribute:
[AttributeUsage(AttributeTargets::Class, AllowMultiple=true )]
public ref class Job : Attribute {
public:
   property int Priority {
      void set( int value ) { m_Priority = value; }
      int get() { return m_Priority; }
   }

   // You can overload constructors to specify Job attribute in different ways
   Job() { m_Access = Access::Read; }
   Job( Access a ) { m_Access = a; }
   Access m_Access;

protected:
   int m_Priority;
};

interface struct IService {
   void Run();
};

   // Using the Job attribute:
   // Here we specify that QueryService is to be read only with a priority of 2.
   // To prevent namespace collisions, all custom attributes implicitly
   // end with "Attribute".

[Job( Access::Read, Priority=2 )]
ref struct QueryService : public IService {
   virtual void Run() {}
};

// Because we said AllowMultiple=true, we can add multiple attributes
[Job(Access::Read, Priority=1)]
[Job(Access::Write, Priority=3)]
ref struct StatsGenerator : public IService {
   virtual void Run( ) {}
};

int main() {
   IService ^ pIS;
   QueryService ^ pQS = gcnew QueryService;
   StatsGenerator ^ pSG = gcnew StatsGenerator;

   //  use QueryService
   pIS = safe_cast<IService ^>( pQS );

   // use StatsGenerator
   pIS = safe_cast<IService ^>( pSG );

   // Reflection
   MemberInfo ^ pMI = pIS->GetType();
   array <Object ^ > ^ pObjs = pMI->GetCustomAttributes(false);

   // We can now quickly and easily view custom attributes for an
   // Object through Reflection */
   for( int i = 0; i < pObjs->Length; i++ ) {
      Console::Write("Service Priority = ");
      Console::WriteLine(static_cast<Job^>(pObjs[i])->Priority);
      Console::Write("Service Access = ");
      Console::WriteLine(static_cast<Job^>(pObjs[i])->m_Access);
   }
}
```

```Output
Service Priority = 0

Service Access = Write

Service Priority = 3

Service Access = Write

Service Priority = 1

Service Access = Read
```

`Object^`型はバリアント データ型を置き換えます。 次の例では、カスタム属性の配列を受け取る`Object^`パラメーターとして。

属性の引数はコンパイル時定数である必要があります。ほとんどの場合、定数リテラルを使用する必要があります。

参照してください[typeid](../windows/typeid-cpp-component-extensions.md)については、カスタム属性ブロックからの system::type の値を返す方法。

```cpp
// extending_metadata_e.cpp
// compile with: /clr /c
using namespace System;
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Method)]
public ref class AnotherAttr : public Attribute {
public:
   AnotherAttr(array<Object^>^) {}
   array<Object^>^ var1;
};

// applying the attribute
[ AnotherAttr( gcnew array<Object ^> { 3.14159, "pi" }, var1 = gcnew array<Object ^> { "a", "b" } ) ]
public ref class SomeClass {};
```

ランタイムは、カスタム属性クラスのパブリックの部分をシリアル化可能でなければならないことが必要です。  カスタム属性を作成するときに、カスタム属性の名前付き引数はコンパイル時定数に限定されます。  (考える一連のビットをメタデータのクラス レイアウトに追加されます。)

```cpp
// extending_metadata_f.cpp
// compile with: /clr /c
using namespace System;
ref struct abc {};

[AttributeUsage( AttributeTargets::All )]
ref struct A : Attribute {
   A( Type^ ) {}
   A( String ^ ) {}
   A( int ) {}
};

[A( abc::typeid )]
ref struct B {};
```

## <a name="see-also"></a>関連項目

[ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)