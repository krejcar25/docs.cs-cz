---
title: "Datové typy konstanty a literálu (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 554753e26d185593ce43b741b3b2f9e3cb1ad6dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="fd8a7-102">Datové typy konstanty a literálu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="fd8a7-103">Literál je hodnota, která je vyjádřena jako samotný a nikoli jako hodnota proměnné nebo výsledek výrazu, například číslo 3 nebo text "Hello".</span><span class="sxs-lookup"><span data-stu-id="fd8a7-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="fd8a7-104">Konstanta je smysluplný název, který přebírá místo literál a uchovává tento stejnou hodnotu v rámci programu, a proměnnou, jehož hodnota může změnit.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="fd8a7-105">Když [Option Infer –](../../../../visual-basic/language-reference/statements/option-infer-statement.md) je `Off` a [možnost striktní](../../../../visual-basic/language-reference/statements/option-strict-statement.md) je `On`, musíte deklarovat všechny konstanty explicitně s datovým typem.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="fd8a7-106">V následujícím příkladu, datový typ `MyByte` explicitně je deklarován jako datový typ `Byte`:</span><span class="sxs-lookup"><span data-stu-id="fd8a7-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="fd8a7-107">Když `Option Infer` je `On` nebo `Option Strict` je `Off`, můžou deklarovat konstanta bez zadání datový typ s `As` klauzule.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="fd8a7-108">Kompilátor Určuje typ konstanty z typu výraz.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="fd8a7-109">Ve výchozím nastavení je přetypovat celé číselný literál číslo `Integer` datového typu.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="fd8a7-110">Výchozí datový typ pro čísla s plovoucí desetinnou čárkou je `Double`a klíčová slova `True` a `False` zadejte `Boolean` konstantní.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="fd8a7-111">Literály a převod typu</span><span class="sxs-lookup"><span data-stu-id="fd8a7-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="fd8a7-112">V některých případech můžete chtít vynutit literál na konkrétní typ; například při přiřazování zvlášť velké integrální literálovou hodnotou proměnné typu `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="fd8a7-113">Následující příklad vytvoří chybu:</span><span class="sxs-lookup"><span data-stu-id="fd8a7-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="fd8a7-114">Chyba výsledků reprezentace literál.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="fd8a7-115">`Decimal` Datový typ může obsahovat hodnotu velké, ale literálové implicitně vyjádřené `Long`, který nelze.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="fd8a7-116">Můžete coerce literál na konkrétní typ. dvěma způsoby: připojením – znak typu k němu nebo tím, že v rámci uzavření znaků.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="fd8a7-117">– Znak typu nebo uzavření znaky musí okamžitě předcházet nebo postupujte podle literál bez použité místo nebo znaků jakéhokoli druhu.</span><span class="sxs-lookup"><span data-stu-id="fd8a7-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="fd8a7-118">Chcete-li předchozí příklad fungovat, můžete připojit `D` zadejte znak, který má literál, což způsobí, že mohla být reprezentován jako `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="fd8a7-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="fd8a7-119">Následující příklad ukazuje správné použití typu znaků a nadřazených znaků:</span><span class="sxs-lookup"><span data-stu-id="fd8a7-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="fd8a7-120">Následující tabulka uvádí nadřazených znaků a typů znaků k dispozici v [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd8a7-120">The following table shows the enclosing characters and type characters available in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
|<span data-ttu-id="fd8a7-121">Datový typ</span><span class="sxs-lookup"><span data-stu-id="fd8a7-121">Data type</span></span>|<span data-ttu-id="fd8a7-122">Nadřazených znak</span><span class="sxs-lookup"><span data-stu-id="fd8a7-122">Enclosing character</span></span>|<span data-ttu-id="fd8a7-123">Znak připojením typu</span><span class="sxs-lookup"><span data-stu-id="fd8a7-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="fd8a7-124">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-124">(none)</span></span>|<span data-ttu-id="fd8a7-125">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="fd8a7-126">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-126">(none)</span></span>|<span data-ttu-id="fd8a7-127">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="fd8a7-128">"</span><span class="sxs-lookup"><span data-stu-id="fd8a7-128">"</span></span>|<span data-ttu-id="fd8a7-129">C</span><span class="sxs-lookup"><span data-stu-id="fd8a7-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="fd8a7-130">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="fd8a7-131">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-131">(none)</span></span>|<span data-ttu-id="fd8a7-132">D nebo @</span><span class="sxs-lookup"><span data-stu-id="fd8a7-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="fd8a7-133">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-133">(none)</span></span>|<span data-ttu-id="fd8a7-134">R nebo #</span><span class="sxs-lookup"><span data-stu-id="fd8a7-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="fd8a7-135">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-135">(none)</span></span>|<span data-ttu-id="fd8a7-136">I nebo %</span><span class="sxs-lookup"><span data-stu-id="fd8a7-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="fd8a7-137">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-137">(none)</span></span>|<span data-ttu-id="fd8a7-138">L nebo &</span><span class="sxs-lookup"><span data-stu-id="fd8a7-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="fd8a7-139">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-139">(none)</span></span>|<span data-ttu-id="fd8a7-140">S</span><span class="sxs-lookup"><span data-stu-id="fd8a7-140">S</span></span>|  
|`Single`|<span data-ttu-id="fd8a7-141">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-141">(none)</span></span>|<span data-ttu-id="fd8a7-142">F nebo!</span><span class="sxs-lookup"><span data-stu-id="fd8a7-142">F or !</span></span>|  
|`String`|<span data-ttu-id="fd8a7-143">"</span><span class="sxs-lookup"><span data-stu-id="fd8a7-143">"</span></span>|<span data-ttu-id="fd8a7-144">(žádný)</span><span class="sxs-lookup"><span data-stu-id="fd8a7-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd8a7-145">Viz také</span><span class="sxs-lookup"><span data-stu-id="fd8a7-145">See Also</span></span>  
 [<span data-ttu-id="fd8a7-146">Uživatelem definované konstanty</span><span class="sxs-lookup"><span data-stu-id="fd8a7-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [<span data-ttu-id="fd8a7-147">Postupy: deklarace konstanty</span><span class="sxs-lookup"><span data-stu-id="fd8a7-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [<span data-ttu-id="fd8a7-148">Přehled konstant</span><span class="sxs-lookup"><span data-stu-id="fd8a7-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="fd8a7-149">Option Strict – příkaz</span><span class="sxs-lookup"><span data-stu-id="fd8a7-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="fd8a7-150">Option Explicit – příkaz</span><span class="sxs-lookup"><span data-stu-id="fd8a7-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="fd8a7-151">Přehled výčtů</span><span class="sxs-lookup"><span data-stu-id="fd8a7-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="fd8a7-152">Postupy: deklarace výčtů</span><span class="sxs-lookup"><span data-stu-id="fd8a7-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="fd8a7-153">Výčty a kvalifikace názvu</span><span class="sxs-lookup"><span data-stu-id="fd8a7-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="fd8a7-154">Datové typy</span><span class="sxs-lookup"><span data-stu-id="fd8a7-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="fd8a7-155">Konstanty a výčty</span><span class="sxs-lookup"><span data-stu-id="fd8a7-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)