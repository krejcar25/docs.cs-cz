---
title: "Rozdíly mezi vlastnostmi a proměnnými v jazyce Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb30972e2b49a7005749f57c0223b9fa493cde52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a><span data-ttu-id="625df-102">Rozdíly mezi vlastnostmi a proměnnými v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="625df-102">Differences Between Properties and Variables in Visual Basic</span></span>
<span data-ttu-id="625df-103">Proměnné a vlastnosti představují hodnoty, kterým můžete přistupovat.</span><span class="sxs-lookup"><span data-stu-id="625df-103">Variables and properties both represent values that you can access.</span></span> <span data-ttu-id="625df-104">Existují však rozdíly v úložišti a implementace.</span><span class="sxs-lookup"><span data-stu-id="625df-104">However, there are differences in storage and implementation.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="625df-105">Proměnné</span><span class="sxs-lookup"><span data-stu-id="625df-105">Variables</span></span>  
 <span data-ttu-id="625df-106">A *proměnná* odpovídá přímo do umístění v paměti.</span><span class="sxs-lookup"><span data-stu-id="625df-106">A *variable* corresponds directly to a memory location.</span></span> <span data-ttu-id="625df-107">Definujete proměnnou s příkazem jediné deklaraci.</span><span class="sxs-lookup"><span data-stu-id="625df-107">You define a variable with a single declaration statement.</span></span> <span data-ttu-id="625df-108">Může být proměnné *místní proměnné*, definované uvnitř procedury a k dispozici pouze v rámci tohoto postupu, nebo může být *členské proměnné*, definované v modulu, třídu nebo strukturu, ale ne do žádného postup.</span><span class="sxs-lookup"><span data-stu-id="625df-108">A variable can be a *local variable*, defined inside a procedure and available only within that procedure, or it can be a *member variable*, defined in a module, class, or structure but not inside any procedure.</span></span> <span data-ttu-id="625df-109">Členské proměnné se taky říká *pole*.</span><span class="sxs-lookup"><span data-stu-id="625df-109">A member variable is also called a *field*.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="625df-110">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="625df-110">Properties</span></span>  
 <span data-ttu-id="625df-111">A *vlastnost* je element data, která je definovaná v modulu, třídu nebo strukturu.</span><span class="sxs-lookup"><span data-stu-id="625df-111">A *property* is a data element defined on a module, class, or structure.</span></span> <span data-ttu-id="625df-112">Definuje vlastnost s blok kódu mezi `Property` a `End Property` příkazy.</span><span class="sxs-lookup"><span data-stu-id="625df-112">You define a property with a code block between the `Property` and `End Property` statements.</span></span> <span data-ttu-id="625df-113">Obsahuje blok kódu `Get` postupu `Set` postup nebo obojí.</span><span class="sxs-lookup"><span data-stu-id="625df-113">The code block contains a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="625df-114">Tyto postupy se nazývají *procedury vlastností* nebo *přístupové objekty vlastnosti*.</span><span class="sxs-lookup"><span data-stu-id="625df-114">These procedures are called *property procedures* or *property accessors*.</span></span> <span data-ttu-id="625df-115">Kromě načítání nebo ukládání hodnotu vlastnosti, se můžete také provést vlastní akce, jako je aktualizace čítače k přístupu.</span><span class="sxs-lookup"><span data-stu-id="625df-115">In addition to retrieving or storing the property's value, they can also perform custom actions, such as updating an access counter.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="625df-116">Rozdíly</span><span class="sxs-lookup"><span data-stu-id="625df-116">Differences</span></span>  
 <span data-ttu-id="625df-117">V následující tabulce jsou uvedeny některé rozdíly mezi proměnné a vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="625df-117">The following table shows some important differences between variables and properties.</span></span>  
  
|<span data-ttu-id="625df-118">Bod rozdílu</span><span class="sxs-lookup"><span data-stu-id="625df-118">Point of difference</span></span>|<span data-ttu-id="625df-119">Proměnná</span><span class="sxs-lookup"><span data-stu-id="625df-119">Variable</span></span>|<span data-ttu-id="625df-120">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="625df-120">Property</span></span>|  
|-------------------------|--------------|--------------|  
|<span data-ttu-id="625df-121">Deklarace</span><span class="sxs-lookup"><span data-stu-id="625df-121">Declaration</span></span>|<span data-ttu-id="625df-122">Příkaz jediné deklaraci</span><span class="sxs-lookup"><span data-stu-id="625df-122">Single declaration statement</span></span>|<span data-ttu-id="625df-123">Řadu příkazy v bloku kódu</span><span class="sxs-lookup"><span data-stu-id="625df-123">Series of statements in a code block</span></span>|  
|<span data-ttu-id="625df-124">Implementace</span><span class="sxs-lookup"><span data-stu-id="625df-124">Implementation</span></span>|<span data-ttu-id="625df-125">Jedno umístění úložiště</span><span class="sxs-lookup"><span data-stu-id="625df-125">Single storage location</span></span>|<span data-ttu-id="625df-126">Spustitelný kód (procedury vlastností)</span><span class="sxs-lookup"><span data-stu-id="625df-126">Executable code (property procedures)</span></span>|  
|<span data-ttu-id="625df-127">Úložiště</span><span class="sxs-lookup"><span data-stu-id="625df-127">Storage</span></span>|<span data-ttu-id="625df-128">Přímo spojené s hodnota proměnné</span><span class="sxs-lookup"><span data-stu-id="625df-128">Directly associated with variable's value</span></span>|<span data-ttu-id="625df-129">Obvykle je interní úložiště není k dispozici mimo obsahující třídy nebo modulu vlastnosti</span><span class="sxs-lookup"><span data-stu-id="625df-129">Typically has internal storage not available outside the property's containing class or module</span></span><br /><br /> <span data-ttu-id="625df-130">Hodnota vlastnosti může nebo nemusí existovat jako element uložené <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="625df-130">Property's value might or might not exist as a stored element <sup>1</sup></span></span>|  
|<span data-ttu-id="625df-131">Spustitelného kódu</span><span class="sxs-lookup"><span data-stu-id="625df-131">Executable code</span></span>|<span data-ttu-id="625df-132">Žádné</span><span class="sxs-lookup"><span data-stu-id="625df-132">None</span></span>|<span data-ttu-id="625df-133">Musí mít alespoň jeden postup</span><span class="sxs-lookup"><span data-stu-id="625df-133">Must have at least one procedure</span></span>|  
|<span data-ttu-id="625df-134">Oprávnění ke čtení a zápisu</span><span class="sxs-lookup"><span data-stu-id="625df-134">Read and write access</span></span>|<span data-ttu-id="625df-135">Pro čtení a zápis nebo jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="625df-135">Read/write or read-only</span></span>|<span data-ttu-id="625df-136">Pro čtení a zápis, jen pro čtení, nebo jen pro zápis</span><span class="sxs-lookup"><span data-stu-id="625df-136">Read/write, read-only, or write-only</span></span>|  
|<span data-ttu-id="625df-137">Vlastní akce (kromě přijetí nebo vrací hodnotu)</span><span class="sxs-lookup"><span data-stu-id="625df-137">Custom actions (in addition to accepting or returning value)</span></span>|<span data-ttu-id="625df-138">Není možná.</span><span class="sxs-lookup"><span data-stu-id="625df-138">Not possible</span></span>|<span data-ttu-id="625df-139">Můžete provést v rámci nastavení nebo načtení hodnota vlastnosti</span><span class="sxs-lookup"><span data-stu-id="625df-139">Can be performed as part of setting or retrieving property value</span></span>|  
  
 <span data-ttu-id="625df-140"><sup>1</sup> na rozdíl od proměnné, nemusí odpovídat hodnotě vlastnosti přímo na jednu položku úložiště.</span><span class="sxs-lookup"><span data-stu-id="625df-140"><sup>1</sup> Unlike a variable, the value of a property might not correspond directly to a single item of storage.</span></span> <span data-ttu-id="625df-141">Úložiště může rozdělit na části pro usnadnění práce nebo zabezpečení, nebo hodnota může být uložena v šifrovaném formátu.</span><span class="sxs-lookup"><span data-stu-id="625df-141">The storage might be split into pieces for convenience or security, or the value might be stored in an encrypted form.</span></span> <span data-ttu-id="625df-142">V těchto případech `Get` postup by spojit nebo dešifrovat uložené hodnoty a `Set` procedura by šifrování novou hodnotu nebo jej rozdělte do základní úložiště.</span><span class="sxs-lookup"><span data-stu-id="625df-142">In these cases the `Get` procedure would assemble the pieces or decrypt the stored value, and the `Set` procedure would encrypt the new value or split it into the constituent storage.</span></span> <span data-ttu-id="625df-143">Hodnotu vlastnosti může být dočasné, jako je čas, den, v takovém případě `Get` postup by vypočítat ho za chodu při každém přístupu k vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="625df-143">A property value might be ephemeral, like time of day, in which case the `Get` procedure would calculate it on the fly each time you access the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625df-144">Viz také</span><span class="sxs-lookup"><span data-stu-id="625df-144">See Also</span></span>  
 [<span data-ttu-id="625df-145">Procedury vlastností</span><span class="sxs-lookup"><span data-stu-id="625df-145">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="625df-146">Parametry a argumenty procedury</span><span class="sxs-lookup"><span data-stu-id="625df-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="625df-147">Property – příkaz</span><span class="sxs-lookup"><span data-stu-id="625df-147">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="625df-148">Dim – příkaz</span><span class="sxs-lookup"><span data-stu-id="625df-148">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="625df-149">Postupy: vytvoření vlastnosti</span><span class="sxs-lookup"><span data-stu-id="625df-149">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="625df-150">Postupy: deklarace vlastnosti se smíšenými úrovněmi přístupu</span><span class="sxs-lookup"><span data-stu-id="625df-150">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="625df-151">Postupy: volání procedury vlastnosti</span><span class="sxs-lookup"><span data-stu-id="625df-151">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="625df-152">Postupy: deklarace a volání výchozí vlastnosti v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="625df-152">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="625df-153">Postupy: vložení hodnoty do vlastnosti</span><span class="sxs-lookup"><span data-stu-id="625df-153">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="625df-154">Postupy: získání hodnoty z vlastnosti</span><span class="sxs-lookup"><span data-stu-id="625df-154">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)