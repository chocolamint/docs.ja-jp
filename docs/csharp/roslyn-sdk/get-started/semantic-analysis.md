---
title: "セマンティック解析の概要"
description: "このチュートリアルでは、.NET コンパイラ SDK を使用したセマンティック解析の概要を説明します。"
author: billwagner
ms.author: wiwagn
ms.date: 02/06/2018
ms.topic: conceptual
ms.prod: .net
ms.devlang: devlang-csharp
ms.custom: mvc
ms.openlocfilehash: 94a28d21cfec1894c3ee3b631335043e1d0ec817
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2018
---
# <a name="get-started-with-semantic-analysis"></a><span data-ttu-id="d1dca-103">セマンティック解析の概要</span><span class="sxs-lookup"><span data-stu-id="d1dca-103">Get started with semantic analysis</span></span>

<span data-ttu-id="d1dca-104">このチュートリアルでは、構文 API の知識を前提としています。</span><span class="sxs-lookup"><span data-stu-id="d1dca-104">This tutorial assumes you're familiar with the Syntax API.</span></span> <span data-ttu-id="d1dca-105">「[構文解析の概要](syntax-analysis.md)」という記事が入門編になっています。</span><span class="sxs-lookup"><span data-stu-id="d1dca-105">The [get started with syntax analysis](syntax-analysis.md) article provides sufficient introduction.</span></span>

<span data-ttu-id="d1dca-106">このチュートリアルでは、**シンボル API** と**バインドの API** について学習します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-106">In this tutorial, you explore the **Symbol** and **Binding APIs**.</span></span> <span data-ttu-id="d1dca-107">これらの API は、プログラムの_意味論的意味_に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-107">These APIs provide information about the _semantic meaning_ of a program.</span></span> <span data-ttu-id="d1dca-108">プログラムのシンボルが表す型について質問したり、回答したりできます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-108">They enable you to ask and answer questions about the types represented by any symbol in your program.</span></span>

## <a name="understanding-compilations-and-symbols"></a><span data-ttu-id="d1dca-109">コンパイルとシンボルについて</span><span class="sxs-lookup"><span data-stu-id="d1dca-109">Understanding Compilations and Symbols</span></span>

<span data-ttu-id="d1dca-110">.NET コンパイラ SDK での作業が増えると、構文 API とセマンティック API の違いに詳しくなります。</span><span class="sxs-lookup"><span data-stu-id="d1dca-110">As you work more with the .NET Compiler SDK, you become familiar with the distinctions between Syntax API and the Semantic API.</span></span> <span data-ttu-id="d1dca-111">**構文 API** では、プログラムの_構造_を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-111">The **Syntax API** allows you to look at the _structure_ of a program.</span></span> <span data-ttu-id="d1dca-112">ただし、多くの場合、プログラムの意味論または_意味_に関する豊富な情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d1dca-112">However, often you want richer information about the semantics or _meaning_ of a program.</span></span> <span data-ttu-id="d1dca-113">VB または C# の緩いコード ファイルまたはスニペットは分離して構文的に解析できますが、孤立状態では、"この変数の型は何ですか" のような質問を問うことに意味がありません。</span><span class="sxs-lookup"><span data-stu-id="d1dca-113">While a loose code file or snippet of VB or C# code can be syntactically analyzed in isolation, it's not meaningful to ask questions such as "what's the type of this variable" in a vacuum.</span></span> <span data-ttu-id="d1dca-114">型名の意味は、アセンブリ参照、名前空間インポート、その他のコード ファイルに依存することがあります。</span><span class="sxs-lookup"><span data-stu-id="d1dca-114">The meaning of a type name may be dependent on assembly references, namespace imports, or other code files.</span></span> <span data-ttu-id="d1dca-115">このような問いには、**セマンティック API** で、具体的には <xref:Microsoft.CodeAnalysis.Compilation?displayProperty=nameWithType> クラスで答えられます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-115">Those questions are answered using the **Semantic API**, specifically the <xref:Microsoft.CodeAnalysis.Compilation?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="d1dca-116"><xref:Microsoft.CodeAnalysis.Compilation> のインスタンスはコンパイラで見られるように 1 つのプロジェクトに類似し、Visual Basic または C# のプログラムをコンパイルするために必要なすべてを表します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-116">An instance of <xref:Microsoft.CodeAnalysis.Compilation> is analogous to a single project as seen by the compiler and represents everything needed to compile a Visual Basic or C# program.</span></span> <span data-ttu-id="d1dca-117">**コンパイル**には、コンパイルするソース ファイルのセット、アセンブリ参照、コンパイラ オプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-117">The **compilation** includes the set of source files to be compiled, assembly references, and compiler options.</span></span> <span data-ttu-id="d1dca-118">この文脈のその他すべての情報を利用し、コードの意味を推論できます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-118">You can reason about the meaning of the code using all the other information in this context.</span></span> <span data-ttu-id="d1dca-119"><xref:Microsoft.CodeAnalysis.Compilation> では、型、名前空間、メンバー、名前やその他の式が参照する変数などのエンティティである**シンボル**を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-119">A <xref:Microsoft.CodeAnalysis.Compilation> allows you to find **Symbols** - entities such as types, namespaces, members, and variables which names and other expressions refer to.</span></span> <span data-ttu-id="d1dca-120">名前や式を**シンボル**と関連付けるプロセスを**バインド**と呼んでいます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-120">The process of associating names and expressions with **Symbols** is called **Binding**.</span></span>

<span data-ttu-id="d1dca-121"><xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType> と同様に、<xref:Microsoft.CodeAnalysis.Compilation> は言語固有の派生物を持つ抽象クラスです。</span><span class="sxs-lookup"><span data-stu-id="d1dca-121">Like <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>, <xref:Microsoft.CodeAnalysis.Compilation> is an abstract class with language-specific derivatives.</span></span> <span data-ttu-id="d1dca-122">コンパイルのインスタンスを作成するとき、<xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation?displayProperty=nameWithType> (または <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicCompilation?displayProperty=nameWithType>) クラスでファクトリ メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1dca-122">When creating an instance of Compilation, you must invoke a factory method on the <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation?displayProperty=nameWithType> (or <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicCompilation?displayProperty=nameWithType>) class.</span></span>

## <a name="querying-symbols"></a><span data-ttu-id="d1dca-123">シンボルにクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="d1dca-123">Querying symbols</span></span>

<span data-ttu-id="d1dca-124">このチュートリアルでは、"Hello World" プログラムをもう一度見てみます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-124">In this tutorial, you look at the "Hello World" program again.</span></span> <span data-ttu-id="d1dca-125">今回、プログラムの中のシンボルにクエリを実行し、そのシンボルが表す型を理解します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-125">This time, you query the symbols in the program to understand what types those symbols represent.</span></span> <span data-ttu-id="d1dca-126">名前空間の型について問い、型で利用できるメソッドを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-126">You query for the types in a namespace, and learn to find the methods available on a type.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1dca-127">次のサンプルでは、Visual Studio 2017 の一部としてインストールされる **.NET Compiler SDK** が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1dca-127">The following samples require the **.NET Compiler SDK** installed as part of Visual Studio 2017.</span></span> <span data-ttu-id="d1dca-128">**Visual Studio 拡張機能の開発**ワークロードの下にリストされている最後の省略可能なコンポーネントとして、.NET Compiler SDK があります。</span><span class="sxs-lookup"><span data-stu-id="d1dca-128">You can find the .NET Compiler SDK as the last optional component listed under the **Visual Studio extension development** workload.</span></span> <span data-ttu-id="d1dca-129">テンプレートは、このコンポーネントなしではインストールされません。</span><span class="sxs-lookup"><span data-stu-id="d1dca-129">The templates aren't installed without this component.</span></span>

<span data-ttu-id="d1dca-130">このサンプルの完成したコードは、[GitHub のリポジトリ](https://github.com/dotnet/docs/tree/master/samples/csharp/roslyn-sdk/SemanticQuickStart)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-130">You can see the finished code for this sample in [our GitHub repository](https://github.com/dotnet/docs/tree/master/samples/csharp/roslyn-sdk/SemanticQuickStart).</span></span>

> [!NOTE]
> <span data-ttu-id="d1dca-131">構文ツリー型では継承を使用して、プログラムのさまざまな場所で有効なさまざまな構文要素を記述します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-131">The Syntax Tree types use inheritance to describe the different syntax elements that are valid at different locations in the program.</span></span> <span data-ttu-id="d1dca-132">これらの API を使用することは、多くの場合、特定の派生型にプロパティまたはコレクション メンバーをキャストすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-132">Using these APIs often means casting properties or collection members to specific derived types.</span></span> <span data-ttu-id="d1dca-133">次の例では、割り当てとキャストは別のステートメントであり、明示的に型指定された変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-133">In the following examples, the assignment and the casts are separate statements, using explicitly typed variables.</span></span> <span data-ttu-id="d1dca-134">コードを読み取り、API の戻り値の型と返されるオブジェクトのランタイム型を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-134">You can read the code to see the return types of the API and the runtime type of the objects returned.</span></span> <span data-ttu-id="d1dca-135">実際には、暗黙的に型指定された変数を使用して、API 名に依存して、調べられるオブジェクトの型を記述するのがより一般的です。</span><span class="sxs-lookup"><span data-stu-id="d1dca-135">In practice, it's more common to use implicitly typed variables and rely on API names to describe the type of objects being examined.</span></span>

<span data-ttu-id="d1dca-136">次のようにして、新しい C# の **Stand-Alone Code Analysis Tool** プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-136">Create a new C# **Stand-Alone Code Analysis Tool** project:</span></span>

* <span data-ttu-id="d1dca-137">Visual Studio で、**[ファイル]**、**[新規]**、**[プロジェクト]** の順に選択して、[新しいプロジェクト] ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-137">In Visual Studio, choose **File** > **New** > **Project** to display the New Project dialog.</span></span>
* <span data-ttu-id="d1dca-138">**[Visual C#]**、**[機能拡張]** で、**[Stand-Alone Code Analysis Tool]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-138">Under **Visual C#** > **Extensibility**, choose **Stand-Alone Code Analysis Tool**.</span></span>
* <span data-ttu-id="d1dca-139">プロジェクトに "**SemanticQuickStart**" という名前を付け、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1dca-139">Name your project "**SemanticQuickStart**" and click OK.</span></span>

<span data-ttu-id="d1dca-140">前述の基本的な "Hello World!" プログラムを</span><span class="sxs-lookup"><span data-stu-id="d1dca-140">You're going to analyze the basic "Hello World!"</span></span> <span data-ttu-id="d1dca-141">分析します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-141">program shown earlier.</span></span>
<span data-ttu-id="d1dca-142">Hello World プログラムのテキストを `Program` クラスの定数として追加します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-142">Add the text for the Hello World program as a constant in your `Program` class:</span></span>

[!code-csharp[Declare the program test](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#1 "Declare a constant string for the program text to analyze")]

<span data-ttu-id="d1dca-143">次に、以下のコードを追加して、`programText` 定数のコード テキストの構文ツリーをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d1dca-143">Next, add the following code to build the syntax tree for the code text in the `programText` constant.</span></span>  <span data-ttu-id="d1dca-144">次の行を `Main` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-144">Add the following line to your `Main` method:</span></span>

[!code-csharp[Create the tree](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#2 "Create the syntax tree")]

<span data-ttu-id="d1dca-145">次に、作成済みのツリーから <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation> をビルドします。</span><span class="sxs-lookup"><span data-stu-id="d1dca-145">Next, build a <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation> from the tree you already created.</span></span> <span data-ttu-id="d1dca-146">"Hello World" サンプルは、<xref:System.String> 型と <xref:System.Console> 型に基づきます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-146">The "Hello World" sample relies on the <xref:System.String> and <xref:System.Console> types.</span></span> <span data-ttu-id="d1dca-147">コンパイルでこの 2 つの型を宣言するアセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1dca-147">You need to reference the assembly that declares those two types in your compilation.</span></span> <span data-ttu-id="d1dca-148">`Main` メソッドに次の行を追加し、適切なアセンブリの参照を含む、構文ツリーのコンパイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-148">Add the following line to your `Main` method to create a compilation of your syntax tree, including the reference to the appropriate assembly:</span></span>

[!code-csharp[Create the compilation](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#3 "Create the compilation for the semantic model")]

<span data-ttu-id="d1dca-149"><xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation.AddReferences%2A?displayProperty=nameWithType> メソッドはコンパイルに参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-149">The <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation.AddReferences%2A?displayProperty=nameWithType> method adds references to the compilation.</span></span> <span data-ttu-id="d1dca-150"><xref:Microsoft.CodeAnalysis.MetadataReference.CreateFromFile%2A?displayProperty=nameWithType> メソッドは参照としてアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-150">The <xref:Microsoft.CodeAnalysis.MetadataReference.CreateFromFile%2A?displayProperty=nameWithType> method loads an assembly as a reference.</span></span> 

## <a name="querying-the-semantic-model"></a><span data-ttu-id="d1dca-151">セマンティック モデルにクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="d1dca-151">Querying the semantic model</span></span>

<span data-ttu-id="d1dca-152"><xref:Microsoft.CodeAnalysis.Compilation> が与えられたら、その <xref:Microsoft.CodeAnalysis.Compilation> に含まれている <xref:Microsoft.CodeAnalysis.SyntaxTree> について <xref:Microsoft.CodeAnalysis.SemanticModel> を求めることができます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-152">Once you have a <xref:Microsoft.CodeAnalysis.Compilation> you can ask it for a <xref:Microsoft.CodeAnalysis.SemanticModel> for any <xref:Microsoft.CodeAnalysis.SyntaxTree> contained in that <xref:Microsoft.CodeAnalysis.Compilation>.</span></span> <span data-ttu-id="d1dca-153">セマンティック モデルは、通常は IntelliSense から得られるすべての情報源としてとらえることができます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-153">You can think of the semantic model as the source for all the information you would normally get from intellisense.</span></span> <span data-ttu-id="d1dca-154"><xref:Microsoft.CodeAnalysis.SemanticModel> は "この場所のスコープ内にはどのような名前があるか"、"このメソッドからアクセスできるメンバーはどれか"、"このテキストのブロックではどのような変数が使用されているか"、"この名前/式は何を参照しているか" のような質問に答えることができます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-154">A <xref:Microsoft.CodeAnalysis.SemanticModel> can answer questions like "What names are in scope at this location?", "What members are accessible from this method?", "What variables are used in this block of text?", and "What does this name/expression refer to?"</span></span> <span data-ttu-id="d1dca-155">このステートメントを追加し、セマンティック モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-155">Add this statement to create the semantic model:</span></span>

[!code-csharp[Create the semantic model](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#4 "Create the semantic model")]

## <a name="binding-a-name"></a><span data-ttu-id="d1dca-156">名前をバインドする</span><span class="sxs-lookup"><span data-stu-id="d1dca-156">Binding a name</span></span>

<span data-ttu-id="d1dca-157"><xref:Microsoft.CodeAnalysis.Compilation> は <xref:Microsoft.CodeAnalysis.SyntaxTree> から <xref:Microsoft.CodeAnalysis.SemanticModel> を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-157">The <xref:Microsoft.CodeAnalysis.Compilation> creates the  <xref:Microsoft.CodeAnalysis.SemanticModel> from the <xref:Microsoft.CodeAnalysis.SyntaxTree>.</span></span> <span data-ttu-id="d1dca-158">モデルを作成したら、それにクエリを実行し、最初の `using` ディレクティブを見つけ、`System` 名前空間のシンボル情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-158">After creating the model, you can query it to find the first `using` directive, and retrieve the symbol information for the `System` namespace.</span></span> <span data-ttu-id="d1dca-159">この 2 つの行を `Main` メソッドに追加し、セマンティック モデルを作成し、最初の using ステートメントのシンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-159">Add these two lines to your `Main` method to create the semantic model and retrieve the symbol for the first using statement:</span></span>

[!code-csharp[Find the namespace symbol for the first using](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#5 "Find the namespace symbol for the first using")]

<span data-ttu-id="d1dca-160">先のコードは、最初の `using` ディレクティブの名前をバインドして、`System` 名前空間の <xref:Microsoft.CodeAnalysis.SymbolInfo?displayProperty=nameWithType> を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1dca-160">The preceding code shows how to bind the name in the first `using` directive to retrieve a <xref:Microsoft.CodeAnalysis.SymbolInfo?displayProperty=nameWithType> for the `System` namespace.</span></span> <span data-ttu-id="d1dca-161">先のコードでは、**構文モデル**を利用してコードの構造を見つけることも確認できます。**セマンティック モデル**を使用し、その意味を理解します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-161">The preceding code also illustrates that you use the **syntax model** to find the structure of the code; you use the **semantic model** to understand its meaning.</span></span> <span data-ttu-id="d1dca-162">**構文モデル**は、using ステートメントの文字列 `System` を見つけます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-162">The **syntax model** finds the string `System` in the using statement.</span></span> <span data-ttu-id="d1dca-163">**セマンティック モデル**には、`System` 名前空間に定義されている型に関するすべての情報があります。</span><span class="sxs-lookup"><span data-stu-id="d1dca-163">The **semantic model** has all the information about the types defined in the `System` namespace.</span></span>

<span data-ttu-id="d1dca-164"><xref:Microsoft.CodeAnalysis.SymbolInfo> オブジェクトから、<xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> プロパティを利用して <xref:Microsoft.CodeAnalysis.ISymbol?displayProperty=nameWithType> を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-164">From the <xref:Microsoft.CodeAnalysis.SymbolInfo> object you can obtain the <xref:Microsoft.CodeAnalysis.ISymbol?displayProperty=nameWithType> using the <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d1dca-165">このプロパティは、この式が参照するシンボルを返します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-165">This property returns the symbol this expression refers to.</span></span> <span data-ttu-id="d1dca-166">何も参照しない式の場合 (数値リテラルなど)、このプロパティは `null` です。</span><span class="sxs-lookup"><span data-stu-id="d1dca-166">For expressions that don't refer to anything (such as numeric literals) this property is `null`.</span></span> <span data-ttu-id="d1dca-167"><xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> が null ではないとき、<xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> はシンボルの型を示します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-167">When the <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> is not null, the <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> denotes the type of the symbol.</span></span> <span data-ttu-id="d1dca-168">この例では、<xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> プロパティは <xref:Microsoft.CodeAnalysis.SymbolKind.Namespace?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="d1dca-168">In this example, the <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> property is a <xref:Microsoft.CodeAnalysis.SymbolKind.Namespace?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d1dca-169">次のコードを `Main` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-169">Add the following code to your `Main` method.</span></span> <span data-ttu-id="d1dca-170">`System` 名前空間のシンボルを取得し、`System` 名前空間で宣言されているすべての子名前空間を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-170">It retrieves the symbol for the `System` namespace and then displays all the child namespaces declared in the `System` namespace:</span></span>

[!code-csharp[Display all the child namespaces](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#6 "Display all the child namespaces from this compilation")]

<span data-ttu-id="d1dca-171">プログラムを実行します。次の出力が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d1dca-171">Run the program and you should see the following output:</span></span>

```
System.Collections
System.Configuration
System.Deployment
System.Diagnostics
System.Globalization
System.IO
System.Numerics
System.Reflection
System.Resources
System.Runtime
System.Security
System.StubHelpers
System.Text
System.Threading
Press any key to continue . . .
```

> [!NOTE]
> <span data-ttu-id="d1dca-172">この出力には、`System` 名前空間の子名前空間の一部が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d1dca-172">The output does not include every namespace that is a child namespace of the `System` namespace.</span></span> <span data-ttu-id="d1dca-173">このコンパイルに存在し、`System.String` が宣言されているアセンブリのみを参照するすべての名前空間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-173">It displays every namespace that is present in this compilation, which only references the assembly where `System.String` is declared.</span></span> <span data-ttu-id="d1dca-174">他のアセンブリで宣言されている名前空間は、このコンパイルでは認識されません。</span><span class="sxs-lookup"><span data-stu-id="d1dca-174">Any namespaces declared in other assemblies are not known to this compilation</span></span>

### <a name="binding-an-expression"></a><span data-ttu-id="d1dca-175">式をバインドする</span><span class="sxs-lookup"><span data-stu-id="d1dca-175">Binding an expression</span></span>

<span data-ttu-id="d1dca-176">先のコードでは、名前にバインドしてシンボルを見つける方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-176">The preceding code shows how to find a symbol by binding to a name.</span></span> <span data-ttu-id="d1dca-177">C# プログラムには、バウンドできて名前ではない式が他にあります。</span><span class="sxs-lookup"><span data-stu-id="d1dca-177">There are other expressions in a C# program that can be bound that aren't names.</span></span> <span data-ttu-id="d1dca-178">この機能を見るために、単純な文字列リテラルのバインドにアクセスしましょう。</span><span class="sxs-lookup"><span data-stu-id="d1dca-178">To demonstrate this capability, let's access the binding to a simple string literal.</span></span>

<span data-ttu-id="d1dca-179">"Hello World" プログラムに <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LiteralExpressionSyntax?displayProperty=nameWithType> が含まれ、"Hello, World!" </span><span class="sxs-lookup"><span data-stu-id="d1dca-179">The "Hello World" program contains a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LiteralExpressionSyntax?displayProperty=nameWithType>, the "Hello, World!"</span></span> <span data-ttu-id="d1dca-180">文字列がコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-180">string displayed to the console.</span></span>

<span data-ttu-id="d1dca-181">プログラムの中で 1 つの文字列リテラルを見つけることで、</span><span class="sxs-lookup"><span data-stu-id="d1dca-181">You find the "Hello, World!"</span></span> <span data-ttu-id="d1dca-182">"Hello, World!" 文字列が見つかります。</span><span class="sxs-lookup"><span data-stu-id="d1dca-182">string by locating the single string literal in the program.</span></span> <span data-ttu-id="d1dca-183">構文ノードが見つかったら、セマンティック モデルからそのノードの型情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-183">Then, once you've located the syntax node, get the type info for that node from the semantic model.</span></span> <span data-ttu-id="d1dca-184">次のコードを `Main` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-184">Add the following code to your `Main` method:</span></span>

[!code-csharp[Find the namespace symbol for the only using](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#7 "Find the namespace symbol for the only using")]

<span data-ttu-id="d1dca-185"><xref:Microsoft.CodeAnalysis.TypeInfo?displayProperty=nameWithType> 構造体には <xref:Microsoft.CodeAnalysis.TypeInfo.Type?displayProperty=nameWithType> プロパティが含まれます。このプロパティによって、リテラルの型に関するセマンティック情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-185">The <xref:Microsoft.CodeAnalysis.TypeInfo?displayProperty=nameWithType> struct includes a <xref:Microsoft.CodeAnalysis.TypeInfo.Type?displayProperty=nameWithType> property that enables access to the semantic information about the type of the literal.</span></span> <span data-ttu-id="d1dca-186">この例では、`string` 型です。</span><span class="sxs-lookup"><span data-stu-id="d1dca-186">In this example, that's the `string` type.</span></span> <span data-ttu-id="d1dca-187">このプロパティをローカル変数に割り当てる宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-187">Add a declaration that assigns this property to a local variable:</span></span>

[!code-csharp[Find the semantic information about the string type](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#8 "Use the string literal to access the semantic information in the string type.")]

<span data-ttu-id="d1dca-188">このチュートリアルの終わりとして、`string` を返す `string` 型で宣言されているすべてのパブリック メソッドのシーケンスを作成する LINQ クエリをビルドしましょう。</span><span class="sxs-lookup"><span data-stu-id="d1dca-188">To finish this tutorial, let's build a LINQ query that creates a sequence of all the public methods declared on the `string` type that return a `string`.</span></span> <span data-ttu-id="d1dca-189">このクエリは複雑になります。そのため、1 行ずつビルドしてから 1 つのクエリとして再構築します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-189">This query gets complex, so let's build it line by line, then reconstruct it as a single query.</span></span> <span data-ttu-id="d1dca-190">このクエリのソースは、`string` 型で宣言されているすべてのメンバーのシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="d1dca-190">The source for this query is the sequence of all members declared on the `string` type:</span></span>

[!code-csharp[Access the sequence of members on the string type](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#9 "Access the sequence of members on the string type.")]

<span data-ttu-id="d1dca-191">そのソース シーケンスには、プロパティやフィールドなど、すべてのメンバーが含まれています。そのため、<xref:System.Collections.Immutable.ImmutableArray%601.OfType%2A?displayProperty=nameWithType> メソッドでフィルター処理し、<xref:Microsoft.CodeAnalysis.IMethodSymbol?diplayProperty=nameWithType> オブジェクトである要素を見つけます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-191">That source sequence conatins all members, including properties and fields, so filter it using the <xref:System.Collections.Immutable.ImmutableArray%601.OfType%2A?displayProperty=nameWithType> method to find elements that are <xref:Microsoft.CodeAnalysis.IMethodSymbol?diplayProperty=nameWithType> objects:</span></span>

[!code-csharp[Filter the sequence to only methods](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#10 "Find the subset of the collection that is the methods.")]

<span data-ttu-id="d1dca-192">次に、パブリック メソッドのみを返す別のフィルターを追加し、`string` を返します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-192">Next, add another filter to return only those methods that are public and return a `string`:</span></span>

[!code-csharp[Filter on return type and accessibility](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#11 "Find only the public methods that return a string.")]

<span data-ttu-id="d1dca-193">名前プロパティのみを選択します。オーバーロードを削除し、別個の名前のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-193">Select only the name property, and only distinct names by removing any overloads:</span></span>

[!code-csharp[find the distinct names.](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#12 "Use the string literal to access the semantic information in the string type.")]

<span data-ttu-id="d1dca-194">LINQ クエリ構文で完全クエリをビルドし、コンソールにすべてのメソッド名を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-194">You can also build the full query using the LINQ query syntax, and then display all the method names in  the console:</span></span>

[!code-csharp[build and display the results of this query.](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#12 "Build and display the results of the query.")]

<span data-ttu-id="d1dca-195">プログラムをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="d1dca-195">Build and run the program.</span></span> <span data-ttu-id="d1dca-196">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1dca-196">You should see the following output:</span></span>

```
Join
Substring
Trim
TrimStart
TrimEnd
Normalize
PadLeft
PadRight
ToLower
ToLowerInvariant
ToUpper
ToUpperInvariant
ToString
Insert
Replace
Remove
Format
Copy
Concat
Intern
IsInterned
Press any key to continue . . .
```
<span data-ttu-id="d1dca-197">セマンティック API を使用し、このプログラムの含まれるシンボルに関する情報を見つけ、表示しました。</span><span class="sxs-lookup"><span data-stu-id="d1dca-197">You've used the Semantic API to find and display information about the symbols that are part of this program.</span></span>