---
title: "Postupy: Vytváření souborů dokumentace XML pomocí modelu CodeDOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7ce95b1c4f33ed500eabf3f9c7a7ac01a3a08e03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a><span data-ttu-id="3053a-102">Postupy: Vytváření souborů dokumentace XML pomocí modelu CodeDOM</span><span class="sxs-lookup"><span data-stu-id="3053a-102">How to: Create an XML Documentation File Using CodeDOM</span></span>
<span data-ttu-id="3053a-103">CodeDOM lze použít k vytvoření kód, který generuje dokumentace XML.</span><span class="sxs-lookup"><span data-stu-id="3053a-103">CodeDOM can be used to create code that generates XML documentation.</span></span> <span data-ttu-id="3053a-104">Proces zahrnuje vytvoření grafu modelu CodeDOM, který obsahuje dokumentační komentáře XML, generování kódu a kompilace generovaného kódu s možností kompilátoru, která vytvoří výstupní dokumentace XML.</span><span class="sxs-lookup"><span data-stu-id="3053a-104">The process involves creating the CodeDOM graph that contains the XML documentation comments, generating the code, and compiling the generated code with the compiler option that creates the XML documentation output.</span></span>  
  
### <a name="to-create-a-codedom-graph-that-contains-xml-documentation-comments"></a><span data-ttu-id="3053a-105">K vytvoření grafu modelu CodeDOM, který obsahuje XML – dokumentační komentáře</span><span class="sxs-lookup"><span data-stu-id="3053a-105">To create a CodeDOM graph that contains XML documentation comments</span></span>  
  
1.  <span data-ttu-id="3053a-106">Vytvoření <xref:System.CodeDom.CodeCompileUnit> obsahující grafu modelu CodeDOM pro ukázkovou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="3053a-106">Create a <xref:System.CodeDom.CodeCompileUnit> containing the CodeDOM graph for the sample application.</span></span>  
  
2.  <span data-ttu-id="3053a-107">Použití <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> konstruktor s `docComment` parametr nastaven na `true` vytvoříte elementy komentáře dokumentace XML a text.</span><span class="sxs-lookup"><span data-stu-id="3053a-107">Use the <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> constructor with the `docComment` parameter set to `true` to create the XML documentation comment elements and text.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="to-generate-the-code-from-the-codecompileunit"></a><span data-ttu-id="3053a-108">Ke generování kódu z vlastnosti CodeCompileUnit</span><span class="sxs-lookup"><span data-stu-id="3053a-108">To generate the code from the CodeCompileUnit</span></span>  
  
1.  <span data-ttu-id="3053a-109">Použití <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> metodu pro generování kódu a vytvoření zdrojového souboru mají být zkompilovány, do.</span><span class="sxs-lookup"><span data-stu-id="3053a-109">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code and create a source file to be compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="to-compile-the-code-and-generate-the-documentation-file"></a><span data-ttu-id="3053a-110">Ke kompilaci kódu a generování souborů dokumentace</span><span class="sxs-lookup"><span data-stu-id="3053a-110">To compile the code and generate the documentation file</span></span>  
  
1.  <span data-ttu-id="3053a-111">Přidat **/doc** – možnost kompilátoru k <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> vlastnost <xref:System.CodeDom.Compiler.CompilerParameters> objektu a předat objekt, který má <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> metodu pro vytvoření souborů dokumentace XML při kompilaci kódu.</span><span class="sxs-lookup"><span data-stu-id="3053a-111">Add the **/doc** compiler option to the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property of a <xref:System.CodeDom.Compiler.CompilerParameters> object and pass the object to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method to create the XML documentation file when the code is compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="3053a-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="3053a-112">Example</span></span>  
 <span data-ttu-id="3053a-113">Následující příklad kódu vytvoří grafu modelu CodeDOM s dokumentační komentáře, vygeneruje soubor kódu z grafu a zkompiluje soubor a vytvoří přidružené souborů dokumentace XML.</span><span class="sxs-lookup"><span data-stu-id="3053a-113">The following code example creates a CodeDOM graph with documentation comments, generates a code file from the graph, and compiles the file and creates an associated XML documentation file.</span></span>  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 <span data-ttu-id="3053a-114">Příklad kódu vytvoří následující dokumentace XML v souboru HelloWorldDoc.xml.</span><span class="sxs-lookup"><span data-stu-id="3053a-114">The code example creates the following XML documentation in the HelloWorldDoc.xml file.</span></span>  
  
```xml  
<?xml version="1.0" ?>   
<doc>  
  <assembly>  
    <name>HelloWorld</name>   
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.   
        <seealso cref="M:Samples.Class1.Main" />   
      </summary>  
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.   
        <para>Add a new paragraph to the description.</para>   
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3053a-115">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="3053a-115">Compiling the Code</span></span>  
  
-   <span data-ttu-id="3053a-116">Tento příklad kódu vyžaduje `FullTrust` nastavit oprávnění při spuštění.</span><span class="sxs-lookup"><span data-stu-id="3053a-116">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3053a-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="3053a-117">See Also</span></span>  
 [<span data-ttu-id="3053a-118">Dokumentace kódu s XML</span><span class="sxs-lookup"><span data-stu-id="3053a-118">Documenting Your Code with XML</span></span>](~/docs/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="3053a-119">Dokumentační komentáře XML</span><span class="sxs-lookup"><span data-stu-id="3053a-119">XML Documentation Comments</span></span>](~/docs/csharp/programming-guide/xmldoc/xml-documentation-comments.md)  
 [<span data-ttu-id="3053a-120">Dokumentace XML</span><span class="sxs-lookup"><span data-stu-id="3053a-120">XML Documentation</span></span>](/cpp/ide/xml-documentation-visual-cpp)