---
title: "SDK pro platformu .NET kompilátoru koncepty a objektový model"
description: "Tento přehled poskytuje na pozadí, které potřebujete k efektivní práci s kompilátoru .NET SDK. Dozvíte vrstvy rozhraní API, hlavní typy související se situací a celkové objektový model."
author: billwagner
ms.author: wiwagn
ms.date: 10/10/2017
ms.topic: conceptual
ms.prod: .net
ms.devlang: devlang-csharp
ms.custom: mvc
ms.openlocfilehash: 65a4695c6f4e5268582d83452246ed8262d6fe2f
ms.sourcegitcommit: d095094e942eedf09530ea5636fbaf9029853027
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/19/2017
---
# <a name="understand-the-net-compiler-platform-sdk-model"></a><span data-ttu-id="3e3b4-104">Pochopení modelu SDK pro platformu .NET kompilátoru</span><span class="sxs-lookup"><span data-stu-id="3e3b4-104">Understand the .NET Compiler Platform SDK model</span></span>

<span data-ttu-id="3e3b4-105">Kompilátory zpracovat kód, který můžete psát následující strukturovaných pravidla, která se často liší od lidí způsob čtení a pochopení kódu.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-105">Compilers process the code you write following structured rules that often differ from the way humans read and understand code.</span></span> <span data-ttu-id="3e3b4-106">Základní znalosti o modelu používaný kompilátory je nezbytné k pochopení rozhraní API používat při sestavení na základě Roslyn nástroje.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-106">A basic understanding of the model used by compilers is essential to understanding the APIs you use when building Roslyn-based tools.</span></span> 

## <a name="compiler-pipeline-functional-areas"></a><span data-ttu-id="3e3b4-107">Kompilátoru kanálu funkčním oblastem</span><span class="sxs-lookup"><span data-stu-id="3e3b4-107">Compiler pipeline functional areas</span></span>

<span data-ttu-id="3e3b4-108">.NET SDK platformy kompilátoru zpřístupní analýza kódu C# a Visual Basic kompilátory vám jako příjemce tím, že poskytuje vrstvu rozhraní API, které odpovídá tradiční kompilátoru kanálu.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-108">The .NET Compiler Platform SDK exposes the C# and Visual Basic compilers' code analysis to you as a consumer by providing an API layer that mirrors a traditional compiler pipeline.</span></span>

![postup zpracování zdrojového kódu pro kód objektu kanálu kompilátoru](media/compiler-pipeline.png)

<span data-ttu-id="3e3b4-110">Jednotlivé fáze kanálu je samostatná komponenta.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-110">Each phase of this pipeline is a separate component.</span></span> <span data-ttu-id="3e3b4-111">Nejprve fázi analýzy tokenizes a analyzuje zdrojový text do syntaxi, která následuje gramatika jazyka.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-111">First, the parse phase tokenizes and parses source text into syntax that follows the language grammar.</span></span> <span data-ttu-id="3e3b4-112">Druhou fázi deklarace analyzuje zdroje a importované metadata do formuláře s názvem symboly.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-112">Second the declaration phase analyzes source and imported metadata to form named symbols.</span></span> <span data-ttu-id="3e3b4-113">Další fázi vazby odpovídá identifikátory v kódu na symboly.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-113">Next the bind phase matches identifiers in the code to symbols.</span></span> <span data-ttu-id="3e3b4-114">Nakonec fázi vysílat vysílá sestavení všechny informace sestavena kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-114">Finally, the emit phase, emits an assembly with all the information built up by the compiler.</span></span>

![kanál kompilátoru rozhraní api poskytuje přístup k každý krok, který je součástí pipelien kompilátoru](media/compiler-pipeline-api.png)

<span data-ttu-id="3e3b4-116">Odpovídající každé z těchto fází, .NET SDK platformy kompilátoru zpřístupní objektový model, který umožňuje přístup k informacím v této fázi.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-116">Corresponding to each of those phases, the .NET Compiler Platform SDK exposes an object model that allows access to the information at that phase.</span></span> <span data-ttu-id="3e3b4-117">Analýzy fáze zpřístupní stromu syntaxe, fázi deklarace zpřístupní tabulky hierarchické symbolů, fázi vazby zpřístupní výsledek analýzy sémantického kompilátoru a fázi vysílat je rozhraní API, které vytváří IL bajtů kódy.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-117">The parsing phase exposes a syntax tree, the declaration phase exposes a hierarchical symbol table, the binding phase exposes the result of the compiler’s semantic analysis, and the emit phase is an API that produces IL byte codes.</span></span>

![k dispozici z kompilátoru jazyka služby rozhraní api v každém kroku kanálu kompilátoru](media/compiler-pipeline-lang-svc.png)

<span data-ttu-id="3e3b4-119">Každý kompilátoru kombinuje tyto součásti společně jako jeden celek začátku do konce.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-119">Each compiler combines these components together as a single end-to-end whole.</span></span>

<span data-ttu-id="3e3b4-120">Tato rozhraní API jsou stejné využívá sada Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-120">These APIs are the same used by Visual Studio.</span></span> <span data-ttu-id="3e3b4-121">Například kód osnovy a formátování funkce použití syntaxe stromů, prohlížeč objektů a navigační funkce pomocí tabulky symbolů, refaktoring a přejít na definici použití sémantického modelu a upravit a pokračovat používá všechny tyto včetně emitování rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-121">For instance, the code outlining and formatting features use the syntax trees, the Object Browser and navigation features use the symbol table, refactorings and Go to Definition use the semantic model, and Edit and Continue uses all of these, including the Emit API.</span></span> 

## <a name="api-layers"></a><span data-ttu-id="3e3b4-122">Rozhraní API vrstvy</span><span class="sxs-lookup"><span data-stu-id="3e3b4-122">API layers</span></span>

<span data-ttu-id="3e3b4-123">Kompilátor .NET SDK se skládá ze dvou vrstev hlavní rozhraní API: kompilátoru rozhraní API a pracovní prostory rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-123">The .NET compiler SDK consists of two main layers of APIs: compiler APIs and workspaces APIs.</span></span>

![rozhraní api vrstvy reprezentována kompilátor kanálu rozhraní API](media/api-layers.png)

### <a name="compiler-apis"></a><span data-ttu-id="3e3b4-125">Rozhraní API kompilátoru</span><span class="sxs-lookup"><span data-stu-id="3e3b4-125">Compiler APIs</span></span>

<span data-ttu-id="3e3b4-126">Vrstva kompilátoru obsahuje objektové modely, které odpovídají vystavený v jednotlivých fázích kanálu kompilátoru syntaktické a sémantické informace.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-126">The compiler layer contains the object models that correspond to information exposed at each phase of the compiler pipeline, both syntactic and semantic.</span></span> <span data-ttu-id="3e3b4-127">Vrstva kompilátoru také obsahuje neměnné snímku jednoho volání kompilátoru, včetně odkazů na sestavení, – možnosti kompilátoru a soubory zdrojového kódu.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-127">The compiler layer also contains an immutable snapshot of a single invocation of a compiler, including assembly references, compiler options, and source code files.</span></span> <span data-ttu-id="3e3b4-128">Existují dva odlišné rozhraní API, které představují jazyka C# a jazyk Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-128">There are two distinct APIs that represent the C# language and the Visual Basic language.</span></span> <span data-ttu-id="3e3b4-129">Tato dvě rozhraní API jsou podobné ve tvaru ale přizpůsobit pro zachováním pro jednotlivé jednotlivé jazyky.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-129">These two APIs are similar in shape but tailored for high-fidelity to each individual language.</span></span> <span data-ttu-id="3e3b4-130">Tato vrstva nemá žádné závislosti na součásti sady Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-130">This layer has no dependencies on Visual Studio components.</span></span>

### <a name="diagnostic-apis"></a><span data-ttu-id="3e3b4-131">Diagnostické rozhraní API</span><span class="sxs-lookup"><span data-stu-id="3e3b4-131">Diagnostic APIs</span></span>

<span data-ttu-id="3e3b4-132">V rámci analýzy kompilátor může vytvořit sadu diagnostiky pokrývajících vše z syntaxe, sémantického a chyby jednoznačné přiřazení do různých upozornění a informační diagnostiky.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-132">As part of its analysis the compiler may produce a set of diagnostics covering everything from syntax, semantic, and definite assignment errors to various warnings and informational diagnostics.</span></span> <span data-ttu-id="3e3b4-133">Vrstvu rozhraní API kompilátoru Tnelze zpřístupní diagnostiky prostřednictvím rozšiřitelné rozhraní API, která umožňuje uživatelem definované analyzátorů zapojené do procesu kompilace.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-133">TThe Compiler API layer exposes diagnostics through an extensible API that allows user-defined analyzers to be plugged into the compilation process.</span></span> <span data-ttu-id="3e3b4-134">To umožňuje diagnostics definovaný uživatelem, jako jsou ty vyprodukované nástroje, například StyleCop nebo FxCop, se vytváří spolu s definované kompilátoru diagnostiky.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-134">It allows user-defined diagnostics, such as those produced by tools like StyleCop or FxCop, to be produced alongside compiler-defined diagnostics.</span></span> <span data-ttu-id="3e3b4-135">Vytváření diagnostiky tímto způsobem má výhodu přirozeně Integrování nástroje, jako je MSBuild a Visual Studio, který je závislý na diagnostiku pro činnosti, jako je například zastavení sestavení na základě zásad a zobrazující podtržení vlnovkou za provozu v editoru a návrhy kódu opravy.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-135">Producing diagnostics in this way has the benefit of integrating naturally with tools such as MSBuild and Visual Studio which depend on diagnostics for experiences such as halting a build based on policy and showing live squiggles in the editor and suggesting code fixes.</span></span>

### <a name="scripting-apis"></a><span data-ttu-id="3e3b4-136">Skriptovací rozhraní API</span><span class="sxs-lookup"><span data-stu-id="3e3b4-136">Scripting APIs</span></span>

<span data-ttu-id="3e3b4-137">Hostování a skriptovací rozhraní API jsou součástí vrstvě kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-137">Hosting and scripting APIs are part of the compiler layer.</span></span> <span data-ttu-id="3e3b4-138">Můžete je používat pro provádění fragmenty kódu a shromažďování kontext spuštění modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-138">You can use them for executing code snippets and accumulating a runtime execution context.</span></span>
<span data-ttu-id="3e3b4-139">Jazyce C# interaktivní REPL (čtení vyhodnotit tiskových smyčky) používá tato rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-139">The C# interactive REPL (Read-Evaluate-Print Loop) uses these APIs.</span></span> <span data-ttu-id="3e3b4-140">REPL umožňuje použít c jako skriptovací jazyk, provádění kódu interaktivně, jako je.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-140">The REPL enables you to use C# as a scripting language, executing the code interactively as you write it.</span></span>

### <a name="workspaces-apis"></a><span data-ttu-id="3e3b4-141">Rozhraní API pracovních prostorů</span><span class="sxs-lookup"><span data-stu-id="3e3b4-141">Workspaces APIs</span></span>

<span data-ttu-id="3e3b4-142">Pracovní prostory vrstva obsahuje rozhraní API pracovní prostor, který je výchozím bodem pro provádění analýzy kódu a refaktoring přes celé řešení.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-142">The Workspaces layer contains the Workspace API, which is the starting point for doing code analysis and refactoring over entire solutions.</span></span> <span data-ttu-id="3e3b4-143">Je vám usnadní uspořádání všechny informace o projekty v řešení do jednoho objektu modelu, nabídky přímý přístup k objektové modely vrstvy kompilátoru bez nutnosti analyzovat souborů, nakonfigurujte možnosti, nebo spravovat závislosti projektu projektu .</span><span class="sxs-lookup"><span data-stu-id="3e3b4-143">It assists you in organizing all the information about the projects in a solution into single object model, offering you direct access to the compiler layer object models without needing to parse files, configure options, or manage project-to-project dependencies.</span></span>

<span data-ttu-id="3e3b4-144">Kromě toho pracovních prostorů vrstvy povrchy sada rozhraní API používá při implementaci analýza kódu a refaktoring nástroje, které funkce v prostředí hostitele, jako třeba Visual Studio IDE.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-144">In addition, the Workspaces layer surfaces a set of APIs used when implementing code analysis and refactoring tools that function within a host environment like the Visual Studio IDE.</span></span> <span data-ttu-id="3e3b4-145">Mezi příklady patří najít všechny odkazy, formátování a rozhraní API pro generování kódu.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-145">Examples include the Find All References, Formatting, and Code Generation APIs.</span></span>

<span data-ttu-id="3e3b4-146">Tato vrstva nemá žádné závislosti na součásti sady Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-146">This layer has no dependencies on Visual Studio components.</span></span>