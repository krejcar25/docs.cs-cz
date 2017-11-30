---
title: "Postupy: Vynucení předání argumentu podle hodnoty (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdb2df7e114f49c23db9f5b322ca9dd32135ac88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="a6eb5-102">Postupy: Vynucení předání argumentu podle hodnoty (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6eb5-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="a6eb5-103">Deklarace procedury určuje předávání.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="a6eb5-104">Pokud je deklarovaný parametr [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] očekává, že předávají odpovídající argument odkazem.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="a6eb5-105">To umožňuje postup změnit hodnotu programovací element základní argument ve volání kódu.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="a6eb5-106">Pokud chcete chránit základní element proti takové změn, můžete přepsat `ByRef` mechanismus předávání v postupu volání uzavřením argument názvu v závorkách.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="a6eb5-107">Tyto závorek je kromě závorkách ohraničení seznamu argumentů volání.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="a6eb5-108">Volání kódu nejde přepsat [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanismus.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="a6eb5-109">Chcete-li vynutit argumentu předání hodnotou</span><span class="sxs-lookup"><span data-stu-id="a6eb5-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="a6eb5-110">Pokud je deklarovaný s odpovídajícím parametrem `ByVal` v postupu, není nutné žádné další kroky.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="a6eb5-111">Očekává se už k předání argumentu podle hodnoty.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="a6eb5-112">Pokud je deklarovaný s odpovídajícím parametrem `ByRef` v postupu, uzavřete jej v závorkách ve volání procedury.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6eb5-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="a6eb5-113">Example</span></span>  
 <span data-ttu-id="a6eb5-114">Následující příklad přepíše `ByRef` deklarace parametru.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="a6eb5-115">Ve volání, které vynutí `ByVal`, Všimněte si, která je dvě úrovně závorek.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 <span data-ttu-id="a6eb5-116">Když `str` uzavřený v závorkách navíc v seznamu argument `setNewString` procedury nelze změnit její hodnota v kód volání a `MsgBox` zobrazí "Nelze nahradit, pokud předány ByVal".</span><span class="sxs-lookup"><span data-stu-id="a6eb5-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="a6eb5-117">Když `str` není uzavřený v závorkách navíc, postup, můžete ho změnit a `MsgBox` zobrazí "Toto je nová hodnota pro inString argument."</span><span class="sxs-lookup"><span data-stu-id="a6eb5-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a6eb5-118">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="a6eb5-118">Compiling the Code</span></span>  
 <span data-ttu-id="a6eb5-119">Pokud předáte proměnné odkazem, je nutné použít `ByRef` – klíčové slovo zadat Tento mechanismus.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="a6eb5-120">Výchozí hodnota v [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] je předání argumentů hodnotou.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-120">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="a6eb5-121">Ale je dobrým zvykem obsahovat buď programovacím [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) nebo [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) – klíčové slovo s každou deklarovaný parametr.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="a6eb5-122">To výrazně zjednodušuje kódu ke čtení.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a6eb5-123">Robustní programování</span><span class="sxs-lookup"><span data-stu-id="a6eb5-123">Robust Programming</span></span>  
 <span data-ttu-id="a6eb5-124">Pokud procedury deklaruje parametr [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), správné spuštění kódu může záviset na možnost změnit základní elementu v kódu volání.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="a6eb5-125">Pokud volání kód přepíše tento mechanismus volání uzavřením argument do závorek, nebo pokud předává neupravitelnými argument, nelze změnit postup základní elementu.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="a6eb5-126">To může vést k neočekávaným výsledkům v volání kódu.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a6eb5-127">Zabezpečení rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a6eb5-127">.NET Framework Security</span></span>  
 <span data-ttu-id="a6eb5-128">Postup ke změně hodnoty základní argument volající kód, který umožňuje existuje vždy představuje potenciální riziko.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="a6eb5-129">Ujistěte se, že byste měli tuto hodnotu změnit, a zkontrolujte správnost před jeho použitím připravit.</span><span class="sxs-lookup"><span data-stu-id="a6eb5-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6eb5-130">Viz také</span><span class="sxs-lookup"><span data-stu-id="a6eb5-130">See Also</span></span>  
 [<span data-ttu-id="a6eb5-131">Postupy</span><span class="sxs-lookup"><span data-stu-id="a6eb5-131">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="a6eb5-132">Parametry a argumenty procedury</span><span class="sxs-lookup"><span data-stu-id="a6eb5-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="a6eb5-133">Postupy: předání argumentů proceduře</span><span class="sxs-lookup"><span data-stu-id="a6eb5-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="a6eb5-134">Předávání argumentů podle hodnoty a podle Reference</span><span class="sxs-lookup"><span data-stu-id="a6eb5-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="a6eb5-135">Rozdíly mezi upravitelnými a Neupravitelnými argumenty</span><span class="sxs-lookup"><span data-stu-id="a6eb5-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="a6eb5-136">Rozdíly mezi předáním argumentu podle hodnoty a podle Reference</span><span class="sxs-lookup"><span data-stu-id="a6eb5-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="a6eb5-137">Postupy: Změna hodnoty argumentu procedury</span><span class="sxs-lookup"><span data-stu-id="a6eb5-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="a6eb5-138">Postupy: ochrana argumentu procedury proti změnám hodnoty</span><span class="sxs-lookup"><span data-stu-id="a6eb5-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="a6eb5-139">Předávání argumentů podle pozice a názvu</span><span class="sxs-lookup"><span data-stu-id="a6eb5-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="a6eb5-140">Typy hodnot a odkazové typy</span><span class="sxs-lookup"><span data-stu-id="a6eb5-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)