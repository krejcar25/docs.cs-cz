---
title: "-definovat (možnosti kompilátoru C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d4c7e4e646e6796cff6bbfbe05038ff361fa80c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="define-c-compiler-options"></a><span data-ttu-id="2ed01-102">/define (Možnosti kompilátoru C#)</span><span class="sxs-lookup"><span data-stu-id="2ed01-102">/define (C# Compiler Options)</span></span>
<span data-ttu-id="2ed01-103">**/ Define** možnost definuje `name` jako symbol v kódu všechny zdrojové soubory vašeho programu.</span><span class="sxs-lookup"><span data-stu-id="2ed01-103">The **/define** option defines `name` as a symbol in all source code files your program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed01-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2ed01-104">Syntax</span></span>  
  
```console  
/define:name[;name2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2ed01-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="2ed01-105">Arguments</span></span>  
 <span data-ttu-id="2ed01-106">`name`, `name2`</span><span class="sxs-lookup"><span data-stu-id="2ed01-106">`name`, `name2`</span></span>  
 <span data-ttu-id="2ed01-107">Název jeden nebo více znaky, které chcete definovat.</span><span class="sxs-lookup"><span data-stu-id="2ed01-107">The name of one or more symbols that you want to define.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ed01-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2ed01-108">Remarks</span></span>  
 <span data-ttu-id="2ed01-109">**/ Define** možnost má stejný účinek jako použití [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) direktivy preprocesoru s tím rozdílem, že možnost kompilátoru platí pro všechny soubory v projektu.</span><span class="sxs-lookup"><span data-stu-id="2ed01-109">The **/define** option has the same effect as using a [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive except that the compiler option is in effect for all files in the project.</span></span> <span data-ttu-id="2ed01-110">Symbol zůstává definované ve zdrojovém souboru až [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) – direktiva ve zdrojovém souboru odebere definici.</span><span class="sxs-lookup"><span data-stu-id="2ed01-110">A symbol remains defined in a source file until an [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directive in the source file removes the definition.</span></span> <span data-ttu-id="2ed01-111">Při použití / define – možnost, `#undef` – direktiva v jednom souboru nemá žádný vliv na jiné soubory zdrojového kódu v projektu.</span><span class="sxs-lookup"><span data-stu-id="2ed01-111">When you use the /define option, an `#undef` directive in one file has no effect on other source code files in the project.</span></span>  
  
 <span data-ttu-id="2ed01-112">Můžete použít symboly, které jsou vytvořené pomocí této možnosti [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), a [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) Podmíněná kompilace zdrojové soubory.</span><span class="sxs-lookup"><span data-stu-id="2ed01-112">You can use symbols created by this option with [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), and [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="2ed01-113">**/d** je zkratka pro **/ define**.</span><span class="sxs-lookup"><span data-stu-id="2ed01-113">**/d** is the short form of **/define**.</span></span>  
  
 <span data-ttu-id="2ed01-114">Můžete definovat více symbolů s **/ define** pomocí středníkem nebo čárkou jednotlivé názvy symbolů.</span><span class="sxs-lookup"><span data-stu-id="2ed01-114">You can define multiple symbols with **/define** by using a semicolon or comma to separate symbol names.</span></span> <span data-ttu-id="2ed01-115">Příklad:</span><span class="sxs-lookup"><span data-stu-id="2ed01-115">For example:</span></span>  
  
```console  
/define:DEBUG;TUESDAY  
```  
  
 <span data-ttu-id="2ed01-116">Kompilátor jazyka C#, samotné definuje žádné symboly nebo makra, které můžete použít ve zdrojovém kódu; všechny definice symbolu musí být definovaný uživatelem.</span><span class="sxs-lookup"><span data-stu-id="2ed01-116">The C# compiler itself defines no symbols or macros that you can use in your source code; all symbol definitions must be user-defined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ed01-117">C# `#define` neumožňuje symbol má být poskytnut hodnotu jako jazyků, například C++.</span><span class="sxs-lookup"><span data-stu-id="2ed01-117">The C# `#define` does not allow a symbol to be given a value, as in languages such as C++.</span></span> <span data-ttu-id="2ed01-118">Například `#define` nelze použít k vytvoření makra nebo definovat konstantu.</span><span class="sxs-lookup"><span data-stu-id="2ed01-118">For example, `#define` cannot be used to create a macro or to define a constant.</span></span> <span data-ttu-id="2ed01-119">Pokud potřebujete definovat konstantu, použijte `enum` proměnné.</span><span class="sxs-lookup"><span data-stu-id="2ed01-119">If you need to define a constant, use an `enum` variable.</span></span> <span data-ttu-id="2ed01-120">Pokud chcete vytvořit makro ve stylu C++, zvažte možnosti například obecné typy.</span><span class="sxs-lookup"><span data-stu-id="2ed01-120">If you want to create a C++ style macro, consider alternatives such as generics.</span></span> <span data-ttu-id="2ed01-121">Vzhledem k tomu, že jsou náchylné makra, C# zakazuje jejich použití, ale poskytuje bezpečnějších alternativ.</span><span class="sxs-lookup"><span data-stu-id="2ed01-121">Since macros are notoriously error-prone, C# disallows their use but provides safer alternatives.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="2ed01-122">Nastavení tohoto parametru kompilátoru ve vývojovém prostředí Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2ed01-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="2ed01-123">Otevření projektu **vlastnosti** stránky.</span><span class="sxs-lookup"><span data-stu-id="2ed01-123">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="2ed01-124">Na **sestavení** , zadejte symbol, který má být definován v **Podmíněná kompilace symboly** pole.</span><span class="sxs-lookup"><span data-stu-id="2ed01-124">On the **Build** tab, type the symbol that is to be defined in the **Conditional compilation symbols** box.</span></span> <span data-ttu-id="2ed01-125">Například pokud používáte příklad kódu, který následuje, právě zadejte `xx` do textového pole.</span><span class="sxs-lookup"><span data-stu-id="2ed01-125">For example, if you are using the code example that follows, just type `xx` into the text box.</span></span>  
  
 <span data-ttu-id="2ed01-126">Informace o tom, jak nastavení této možnosti kompilátoru programu najdete v tématu <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ed01-126">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ed01-127">Příklad</span><span class="sxs-lookup"><span data-stu-id="2ed01-127">Example</span></span>  
  
```csharp  
// preprocessor_define.cs  
// compile with: /define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test   
{  
    public static void Main()   
    {  
        #if (xx)   
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ed01-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="2ed01-128">See Also</span></span>  
 [<span data-ttu-id="2ed01-129">Možnosti kompilátoru C#</span><span class="sxs-lookup"><span data-stu-id="2ed01-129">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="2ed01-130">Správa vlastností projektů a řešení</span><span class="sxs-lookup"><span data-stu-id="2ed01-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)