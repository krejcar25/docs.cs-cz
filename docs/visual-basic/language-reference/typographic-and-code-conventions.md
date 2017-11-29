---
title: "Typografická pravidla a pravidla vytváření kódu (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7b6db5c223b0548e308b49a686cff72eaaf8da36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="typographic-and-code-conventions-visual-basic"></a><span data-ttu-id="46563-102">Typografická pravidla a pravidla vytváření kódu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46563-102">Typographic and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="46563-103">Dokumentace jazyka Visual Basic používá následující typografická pravidla a pravidla týkající se kódu.</span><span class="sxs-lookup"><span data-stu-id="46563-103">Visual Basic documentation uses the following typographic and code conventions.</span></span>  
  
## <a name="typographic-conventions"></a><span data-ttu-id="46563-104">Typografické konvence</span><span class="sxs-lookup"><span data-stu-id="46563-104">Typographic Conventions</span></span>  
  
|<span data-ttu-id="46563-105">Příklad</span><span class="sxs-lookup"><span data-stu-id="46563-105">Example</span></span>|<span data-ttu-id="46563-106">Popis</span><span class="sxs-lookup"><span data-stu-id="46563-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46563-107">`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`</span><span class="sxs-lookup"><span data-stu-id="46563-107">`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`</span></span>|<span data-ttu-id="46563-108">Klíčová slova specifická pro jazyk a runtime členů mají počáteční velká písmena a zda jsou formátovány jak je znázorněno v tomto příkladu.</span><span class="sxs-lookup"><span data-stu-id="46563-108">Language-specific keywords and runtime members have initial uppercase letters and are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="46563-109">**SmallProject**, **ButtonCollection**</span><span class="sxs-lookup"><span data-stu-id="46563-109">**SmallProject**, **ButtonCollection**</span></span>|<span data-ttu-id="46563-110">Jak je znázorněno v tomto příkladu jsou formátovaná slova a slovní spojení, nebudete vyzváni k zadání.</span><span class="sxs-lookup"><span data-stu-id="46563-110">Words and phrases you are instructed to type are formatted as shown in this example.</span></span>|  
|[<span data-ttu-id="46563-111">Module – příkaz</span><span class="sxs-lookup"><span data-stu-id="46563-111">Module Statement</span></span>](../../visual-basic/language-reference/statements/module-statement.md)|<span data-ttu-id="46563-112">Odkazy, které lze klepnout a přejít na jinou stránku nápovědy jsou formátovaná, jak je znázorněno v tomto příkladu.</span><span class="sxs-lookup"><span data-stu-id="46563-112">Links you can click to go to another Help page are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="46563-113">*objekt*, *NázevProměnné*,`argumentList`</span><span class="sxs-lookup"><span data-stu-id="46563-113">*object*, *variableName*, `argumentList`</span></span>|<span data-ttu-id="46563-114">Zástupné symboly pro informace, které zadáte jsou formátovaná, jak je znázorněno v tomto příkladu.</span><span class="sxs-lookup"><span data-stu-id="46563-114">Placeholders for information that you supply are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="46563-115">[Stínů], [ *expressionList* ]</span><span class="sxs-lookup"><span data-stu-id="46563-115">[ Shadows ], [ *expressionList* ]</span></span>|<span data-ttu-id="46563-116">V syntaxi jsou volitelné položky uzavřený v závorkách.</span><span class="sxs-lookup"><span data-stu-id="46563-116">In syntax, optional items are enclosed in brackets.</span></span>|  
|<span data-ttu-id="46563-117">{ `Public` &#124; `Friend` &#124; `Private` }</span><span class="sxs-lookup"><span data-stu-id="46563-117">{ `Public` &#124; `Friend` &#124; `Private` }</span></span>|<span data-ttu-id="46563-118">V syntaxi když je nutné vybrat mezi dva nebo více položek, jsou uzavřené do složených závorek a položky oddělených svislých pruhů.</span><span class="sxs-lookup"><span data-stu-id="46563-118">In syntax, when you must make a choice between two or more items, the items are enclosed in braces and separated by vertical bars.</span></span><br /><br /> <span data-ttu-id="46563-119">Je nutné vybrat jeden a pouze jeden položky.</span><span class="sxs-lookup"><span data-stu-id="46563-119">You must select one, and only one, of the items.</span></span>|  
|<span data-ttu-id="46563-120">[ `Protected` &#124; `Friend` ]</span><span class="sxs-lookup"><span data-stu-id="46563-120">[ `Protected` &#124; `Friend` ]</span></span>|<span data-ttu-id="46563-121">V syntaxi když máte možnost výběru mezi dva nebo více položek, jsou uzavřeny do hranatých závorek a položky oddělených svislých pruhů.</span><span class="sxs-lookup"><span data-stu-id="46563-121">In syntax, when you have the option of selecting between two or more items, the items are enclosed in square brackets and separated by vertical bars.</span></span><br /><br /> <span data-ttu-id="46563-122">Můžete vybrat libovolnou kombinaci položky nebo žádná položka.</span><span class="sxs-lookup"><span data-stu-id="46563-122">You can select any combination of the items, or no item.</span></span>|  
|<span data-ttu-id="46563-123">[{ `ByVal` &#124; `ByRef` }]</span><span class="sxs-lookup"><span data-stu-id="46563-123">[{ `ByVal` &#124; `ByRef` }]</span></span>|<span data-ttu-id="46563-124">V syntaxi když vyberete více než jednu položku, ale položky můžete vypustit úplně, jsou položky uzavřeny do hranatých závorek obklopená složené závorky a oddělených svislých pruhů.</span><span class="sxs-lookup"><span data-stu-id="46563-124">In syntax, when you can select no more than one item, but you can also omit the items completely, the items are enclosed in square brackets surrounded by braces and separated by vertical bars.</span></span>|  
|<span data-ttu-id="46563-125">*memberName*1, *memberName*2, *memberName*3</span><span class="sxs-lookup"><span data-stu-id="46563-125">*memberName*1, *memberName*2, *memberName*3</span></span>|<span data-ttu-id="46563-126">Více instancí stejné zástupný symbol jsou rozlišené pomocí dolní indexy, jak je znázorněno v příkladu.</span><span class="sxs-lookup"><span data-stu-id="46563-126">Multiple instances of the same placeholder are differentiated by subscripts, as shown in the example.</span></span>|  
|<span data-ttu-id="46563-127">*memberName1*</span><span class="sxs-lookup"><span data-stu-id="46563-127">*memberName1*</span></span><br /><br /> <span data-ttu-id="46563-128">...</span><span class="sxs-lookup"><span data-stu-id="46563-128">...</span></span><br /><br /> <span data-ttu-id="46563-129">*memberNameN*</span><span class="sxs-lookup"><span data-stu-id="46563-129">*memberNameN*</span></span>|<span data-ttu-id="46563-130">V syntaxi, třemi tečkami (...) slouží k označení nekonečný počet položek typu bezprostředně před se třemi tečkami.</span><span class="sxs-lookup"><span data-stu-id="46563-130">In syntax, an ellipsis (...) is used to indicate an indefinite number of items of the kind immediately in front of the ellipsis.</span></span><br /><br /> <span data-ttu-id="46563-131">V kódu symbol tří teček označily kód vynechání v zájmu přehlednosti.</span><span class="sxs-lookup"><span data-stu-id="46563-131">In code, ellipses signify code omitted for the sake of clarity.</span></span>|  
|<span data-ttu-id="46563-132">ESC, ZADEJTE</span><span class="sxs-lookup"><span data-stu-id="46563-132">ESC, ENTER</span></span>|<span data-ttu-id="46563-133">Názvy klíčů a posloupnosti kláves na klávesnici zobrazí velkými písmeny.</span><span class="sxs-lookup"><span data-stu-id="46563-133">Key names and key sequences on the keyboard appear in all uppercase letters.</span></span>|  
|<span data-ttu-id="46563-134">ALT + F1</span><span class="sxs-lookup"><span data-stu-id="46563-134">ALT+F1</span></span>|<span data-ttu-id="46563-135">Jakmile se zobrazí znak plus (+) mezi názvy klíčů, můžete při dalších stisknutím stisknutou jeden klíč.</span><span class="sxs-lookup"><span data-stu-id="46563-135">When plus signs (+) appear between key names, you must hold down one key while pressing the other.</span></span> <span data-ttu-id="46563-136">ALT + F1 například znamená, podržte klávesu ALT a stisknutím klávesy F1.</span><span class="sxs-lookup"><span data-stu-id="46563-136">For example, ALT+F1 means hold down the ALT key while pressing the F1 key.</span></span>|  
  
## <a name="code-conventions"></a><span data-ttu-id="46563-137">Pravidla týkající se kódu</span><span class="sxs-lookup"><span data-stu-id="46563-137">Code Conventions</span></span>  
  
|<span data-ttu-id="46563-138">Příklad</span><span class="sxs-lookup"><span data-stu-id="46563-138">Example</span></span>|<span data-ttu-id="46563-139">Popis</span><span class="sxs-lookup"><span data-stu-id="46563-139">Description</span></span>|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|<span data-ttu-id="46563-140">Ukázky kódu se zobrazí v neproporcionální písmo a zda jsou formátovány jak je znázorněno v tomto příkladu.</span><span class="sxs-lookup"><span data-stu-id="46563-140">Code samples appear in a fixed-pitch font and are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="46563-141">Předchozí příkaz nastaví hodnotu `sampleString` na "Hello, world!"</span><span class="sxs-lookup"><span data-stu-id="46563-141">The previous statement sets the value of `sampleString` to "Hello, world!"</span></span>|<span data-ttu-id="46563-142">Elementy kódu v vysvětlující text se zobrazí v neproporcionální písmo, jak je uvedeno v tomto příkladu.</span><span class="sxs-lookup"><span data-stu-id="46563-142">Code elements in explanatory text appear in a fixed-pitch font, as shown in this example.</span></span>|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|<span data-ttu-id="46563-143">Komentáře kódu jsou zavedené službou apostrof (') nebo klíčové slovo REM.</span><span class="sxs-lookup"><span data-stu-id="46563-143">Code comments are introduced by an apostrophe (') or the REM keyword.</span></span>|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|<span data-ttu-id="46563-144">Mezeru a podtržítko (_) na konci řádku označuje, zda příkaz bude pokračovat na následující řádek.</span><span class="sxs-lookup"><span data-stu-id="46563-144">A space followed by an underscore ( _) at the end of a line indicates that the statement continues on the following line.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46563-145">Viz také</span><span class="sxs-lookup"><span data-stu-id="46563-145">See Also</span></span>  
 [<span data-ttu-id="46563-146">Referenční dokumentace jazyka Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46563-146">Visual Basic Language Reference</span></span>](../../visual-basic/language-reference/index.md)  
 [<span data-ttu-id="46563-147">Klíčová slova</span><span class="sxs-lookup"><span data-stu-id="46563-147">Keywords</span></span>](../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="46563-148">Členové knihovny prostředí Runtime jazyka Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46563-148">Visual Basic Runtime Library Members</span></span>](../../visual-basic/language-reference/runtime-library-members.md)  
 [<span data-ttu-id="46563-149">Zásady vytváření názvů jazyka Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46563-149">Visual Basic Naming Conventions</span></span>](../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="46563-150">Postupy: přerušení a kombinace příkazů v kódu</span><span class="sxs-lookup"><span data-stu-id="46563-150">How to: Break and Combine Statements in Code</span></span>](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [<span data-ttu-id="46563-151">Komentáře v kódu</span><span class="sxs-lookup"><span data-stu-id="46563-151">Comments in Code</span></span>](../../visual-basic/programming-guide/program-structure/comments-in-code.md)