---
title: "-warn (možnosti kompilátoru C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab5748f43777ec545e76100543473785894461cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="warn-c-compiler-options"></a><span data-ttu-id="dbe33-102">/warn (Možnosti kompilátoru C#)</span><span class="sxs-lookup"><span data-stu-id="dbe33-102">/warn (C# Compiler Options)</span></span>
<span data-ttu-id="dbe33-103">**/ Warn** možnost určuje úroveň pro upozornění pro kompilátor zobrazovat.</span><span class="sxs-lookup"><span data-stu-id="dbe33-103">The **/warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe33-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="dbe33-104">Syntax</span></span>  
  
```console  
/warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="dbe33-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="dbe33-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="dbe33-106">Úroveň pro upozornění, které chcete zobrazit pro kompilace: nižší čísla zobrazují pouze vysokou závažností upozornění; vyšší čísla zobrazit další varování.</span><span class="sxs-lookup"><span data-stu-id="dbe33-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="dbe33-107">Platné hodnoty jsou 0-4:</span><span class="sxs-lookup"><span data-stu-id="dbe33-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="dbe33-108">Úroveň upozornění</span><span class="sxs-lookup"><span data-stu-id="dbe33-108">Warning level</span></span>|<span data-ttu-id="dbe33-109">Význam</span><span class="sxs-lookup"><span data-stu-id="dbe33-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="dbe33-110">0</span><span class="sxs-lookup"><span data-stu-id="dbe33-110">0</span></span>|<span data-ttu-id="dbe33-111">Vypne vyvolávání všechny zprávy upozornění.</span><span class="sxs-lookup"><span data-stu-id="dbe33-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="dbe33-112">1</span><span class="sxs-lookup"><span data-stu-id="dbe33-112">1</span></span>|<span data-ttu-id="dbe33-113">Zobrazí závažné zprávy upozornění.</span><span class="sxs-lookup"><span data-stu-id="dbe33-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="dbe33-114">2</span><span class="sxs-lookup"><span data-stu-id="dbe33-114">2</span></span>|<span data-ttu-id="dbe33-115">Zobrazí upozornění úrovně 1 a některé méně závažné upozornění, jako jsou třeba upozornění o skrývání členy třídy.</span><span class="sxs-lookup"><span data-stu-id="dbe33-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="dbe33-116">3</span><span class="sxs-lookup"><span data-stu-id="dbe33-116">3</span></span>|<span data-ttu-id="dbe33-117">Zobrazí upozornění úrovně 2 a některé méně závažné upozornění, jako jsou třeba upozornění o výrazech, které jsou vždy vyhodnoceny na `true` nebo `false`.</span><span class="sxs-lookup"><span data-stu-id="dbe33-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="dbe33-118">4 (výchozí)</span><span class="sxs-lookup"><span data-stu-id="dbe33-118">4 (the default)</span></span>|<span data-ttu-id="dbe33-119">Zobrazí všechny úrovně 3 upozornění a informační upozornění.</span><span class="sxs-lookup"><span data-stu-id="dbe33-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbe33-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dbe33-120">Remarks</span></span>  
 <span data-ttu-id="dbe33-121">Chcete-li získat informace o chybě nebo upozornění, můžete vyhledat kód chyby v rejstříku nápovědy.</span><span class="sxs-lookup"><span data-stu-id="dbe33-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="dbe33-122">Další způsoby, jak získat informace o chybě nebo upozornění, naleznete v části [chyby kompilátoru jazyka C#](../../../csharp/language-reference/compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="dbe33-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="dbe33-123">Použití [/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) zachází všech upozornění jako chyby.</span><span class="sxs-lookup"><span data-stu-id="dbe33-123">Use [/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="dbe33-124">Použití [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) zakázat některé upozornění.</span><span class="sxs-lookup"><span data-stu-id="dbe33-124">Use [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="dbe33-125">**/w** je zkratka pro **/ warn**.</span><span class="sxs-lookup"><span data-stu-id="dbe33-125">**/w** is the short form of **/warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="dbe33-126">Nastavení tohoto parametru kompilátoru ve vývojovém prostředí Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dbe33-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="dbe33-127">Otevření projektu **vlastnosti** stránky.</span><span class="sxs-lookup"><span data-stu-id="dbe33-127">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="dbe33-128">Klikněte **sestavení** stránku vlastností.</span><span class="sxs-lookup"><span data-stu-id="dbe33-128">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="dbe33-129">Změnit **úroveň pro upozornění** vlastnost.</span><span class="sxs-lookup"><span data-stu-id="dbe33-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="dbe33-130">Informace o tom, jak nastavení této možnosti kompilátoru programu najdete v tématu <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbe33-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbe33-131">Příklad</span><span class="sxs-lookup"><span data-stu-id="dbe33-131">Example</span></span>  
 <span data-ttu-id="dbe33-132">Kompilace `in.cs` kompilátor zobrazuje pouze upozornění úrovně 1:</span><span class="sxs-lookup"><span data-stu-id="dbe33-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc /warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="dbe33-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="dbe33-133">See Also</span></span>  
 [<span data-ttu-id="dbe33-134">Možnosti kompilátoru C#</span><span class="sxs-lookup"><span data-stu-id="dbe33-134">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="dbe33-135">Správa vlastností projektů a řešení</span><span class="sxs-lookup"><span data-stu-id="dbe33-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)