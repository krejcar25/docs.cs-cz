---
title: "Sestavení z příkazového řádku (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d982506af2c4f01e80ae5b3862fcbcfff2aa9d99
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="f3353-102">Sestavení z příkazového řádku (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3353-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="f3353-103">A [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] projektu se skládá z jedné nebo více samostatných zdrojové soubory.</span><span class="sxs-lookup"><span data-stu-id="f3353-103">A [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project is made up of one or more separate source files.</span></span> <span data-ttu-id="f3353-104">Během procesu říká kompilace, tyto soubory jsou shromážděna do jednoho balíčku – jeden spustitelný soubor, který může běžet jako aplikace.</span><span class="sxs-lookup"><span data-stu-id="f3353-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="f3353-105">poskytuje kompilátoru příkazového řádku jako alternativu k kompilace programů v nástroji [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrované vývojové prostředí (IDE).</span><span class="sxs-lookup"><span data-stu-id="f3353-105"> provides a command-line compiler as an alternative to compiling programs from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrated development environment (IDE).</span></span> <span data-ttu-id="f3353-106">Kompilátor příkazového řádku je navržené pro situace, ve kterých nechcete, aby úplnou sadu funkcí v prostředí IDE – například když používáte nebo zápis pro počítače s omezené systémové paměti nebo úložný prostor.</span><span class="sxs-lookup"><span data-stu-id="f3353-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
 <span data-ttu-id="f3353-107">Při kompilaci z příkazového řádku, musí být explicitně uvedena Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] běhové knihovny prostřednictvím `/reference` – možnost kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="f3353-107">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
 <span data-ttu-id="f3353-108">Zkompilovat zdrojové soubory v rámci [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrovaného vývojového prostředí, vyberte **sestavení** příkaz **sestavení** nabídky.</span><span class="sxs-lookup"><span data-stu-id="f3353-108">To compile source files from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="f3353-109">Při sestavování projektu soubory pomocí prostředí Visual Studio IDE, můžete zobrazit informace o přidruženého **Vbc –** příkazu a jeho přepínače v okně výstupu.</span><span class="sxs-lookup"><span data-stu-id="f3353-109">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="f3353-110">Chcete-li zobrazit tyto informace, otevřete [dialogové okno Možnosti, projekty a řešení, sestavení a spuštění](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)a poté nastavte **výstup sestavení projektu MSBuild podrobností** k **normální** nebo vyšší úrovni podrobností.</span><span class="sxs-lookup"><span data-stu-id="f3353-110">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="f3353-111">Další informace najdete v tématu [postupy: zobrazení, ukládání a konfigurace souborů protokolu sestavení](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="f3353-111">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
 <span data-ttu-id="f3353-112">Soubory projektu (.vbproj) na příkazovém řádku můžete zkompilovat pomocí nástroje MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f3353-112">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="f3353-113">Další informace najdete v tématu [Reference k příkazovému řádku](/visualstudio/msbuild/msbuild-command-line-reference) a [návod: použití nástroje MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="f3353-113">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3353-114">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="f3353-114">In This Section</span></span>  
 [<span data-ttu-id="f3353-115">Postupy: volání kompilátoru příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="f3353-115">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="f3353-116">Popisuje, jak má být vyvolán kompilátoru příkazového řádku do příkazového řádku nebo z určité podadresáři.</span><span class="sxs-lookup"><span data-stu-id="f3353-116">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="f3353-117">Příkazové řádky ukázkové kompilace</span><span class="sxs-lookup"><span data-stu-id="f3353-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="f3353-118">Poskytuje seznam příkazové řádky ukázkové, které lze upravit pro vlastní použití.</span><span class="sxs-lookup"><span data-stu-id="f3353-118">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f3353-119">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="f3353-119">Related Sections</span></span>  
 [<span data-ttu-id="f3353-120">Visual Basic – kompilátor příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="f3353-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="f3353-121">Poskytuje seznam – možnosti kompilátoru, uspořádané podle abecedy nebo účel.</span><span class="sxs-lookup"><span data-stu-id="f3353-121">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="f3353-122">Podmíněná kompilace</span><span class="sxs-lookup"><span data-stu-id="f3353-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="f3353-123">Popisuje, jak zkompilovat určité části kódu.</span><span class="sxs-lookup"><span data-stu-id="f3353-123">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="f3353-124">Sestavování a čištění projektů a řešení v sadě Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3353-124">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="f3353-125">Popisuje, jak uspořádat co budou zahrnuty do různých sestavení, vyberte vlastnosti projektu a ujistěte se, že sestavení projektů ve správném pořadí.</span><span class="sxs-lookup"><span data-stu-id="f3353-125">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>