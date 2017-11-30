---
title: "Logické a bitové operátory v jazyce Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba48f722a11e93f82ae99aa407c3096a964e5ddd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="ef941-102">Logické a bitové operátory v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ef941-102">Logical and Bitwise Operators in Visual Basic</span></span>
<span data-ttu-id="ef941-103">Logické operátory porovnání `Boolean` výrazy a vraťte se `Boolean` výsledek.</span><span class="sxs-lookup"><span data-stu-id="ef941-103">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="ef941-104">`And`, `Or`, `AndAlso`, `OrElse`, A `Xor` operátory jsou *binární* vzhledem k tomu, že jejich trvat dva operandy, při `Not` operátor je *unární* vzhledem k tomu, jak dlouho trvá jeden operand.</span><span class="sxs-lookup"><span data-stu-id="ef941-104">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="ef941-105">Některé z těchto operátorů můžete také provést bitové logické operace na celočíselné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="ef941-105">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="ef941-106">Unární logický operátor</span><span class="sxs-lookup"><span data-stu-id="ef941-106">Unary Logical Operator</span></span>  
 <span data-ttu-id="ef941-107">[Operátor Not](../../../../visual-basic/language-reference/operators/not-operator.md) provede logické *negace* na `Boolean` výraz.</span><span class="sxs-lookup"><span data-stu-id="ef941-107">The [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="ef941-108">Vrací logickou opak jeho operand.</span><span class="sxs-lookup"><span data-stu-id="ef941-108">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="ef941-109">Pokud je výsledkem výrazu `True`, pak `Not` vrátí `False`; Pokud je výsledkem výrazu `False`, pak `Not` vrátí `True`.</span><span class="sxs-lookup"><span data-stu-id="ef941-109">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="ef941-110">Toto dokládá následující příklad.</span><span class="sxs-lookup"><span data-stu-id="ef941-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="ef941-111">Binární logické operátory</span><span class="sxs-lookup"><span data-stu-id="ef941-111">Binary Logical Operators</span></span>  
 <span data-ttu-id="ef941-112">[a operátor](../../../../visual-basic/language-reference/operators/and-operator.md) provede logické *spojení* na dva `Boolean` výrazy.</span><span class="sxs-lookup"><span data-stu-id="ef941-112">The [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="ef941-113">Pokud jsou oba výrazy vyhodnoceny `True`, pak `And` vrátí `True`.</span><span class="sxs-lookup"><span data-stu-id="ef941-113">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="ef941-114">Pokud je alespoň jeden z výrazů výsledkem `False`, pak `And` vrátí `False`.</span><span class="sxs-lookup"><span data-stu-id="ef941-114">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="ef941-115">[Operátor nebo](../../../../visual-basic/language-reference/operators/or-operator.md) provede logické *disjunkce* nebo *zahrnutí* na dva `Boolean` výrazy.</span><span class="sxs-lookup"><span data-stu-id="ef941-115">The [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="ef941-116">Pokud výraz vyhodnocen jako `True`, nebo obě vyhodnocení `True`, pak `Or` vrátí `True`.</span><span class="sxs-lookup"><span data-stu-id="ef941-116">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="ef941-117">Pokud ani výraz vyhodnocen `True`, `Or` vrátí `False`.</span><span class="sxs-lookup"><span data-stu-id="ef941-117">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="ef941-118">[Xor Operátor](../../../../visual-basic/language-reference/operators/xor-operator.md) provede logické *vyloučení* na dva `Boolean` výrazy.</span><span class="sxs-lookup"><span data-stu-id="ef941-118">The [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="ef941-119">Pokud je výsledkem přesně jeden výraz `True`, ale ne obojí `Xor` vrátí `True`.</span><span class="sxs-lookup"><span data-stu-id="ef941-119">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="ef941-120">Pokud jsou oba výrazy vyhodnoceny `True` nebo obě vyhodnocení `False`, `Xor` vrátí `False`.</span><span class="sxs-lookup"><span data-stu-id="ef941-120">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="ef941-121">Následující příklad ukazuje `And`, `Or`, a `Xor` operátory.</span><span class="sxs-lookup"><span data-stu-id="ef941-121">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_2.vb)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="ef941-122">Krátká smyčka logických operací</span><span class="sxs-lookup"><span data-stu-id="ef941-122">Short-Circuiting Logical Operations</span></span>  
 <span data-ttu-id="ef941-123">[AndAlso – operátor](../../../../visual-basic/language-reference/operators/andalso-operator.md) je velmi podobné `And` operátor, v tom, že provádí taky logické spojení na dva `Boolean` výrazy.</span><span class="sxs-lookup"><span data-stu-id="ef941-123">The [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="ef941-124">Klíčovým rozdílem mezi těmito dvěma je, že `AndAlso` jádro vykazuje *krátká smyčka* chování.</span><span class="sxs-lookup"><span data-stu-id="ef941-124">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="ef941-125">Pokud k prvnímu výrazu v `AndAlso` výraz vyhodnocen jako `False`, pak je výraz druhé není vyhodnotit, protože jej nelze změnit konečný výsledek a `AndAlso` vrátí `False`.</span><span class="sxs-lookup"><span data-stu-id="ef941-125">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="ef941-126">Podobně [orelse – operátor](../../../../visual-basic/language-reference/operators/orelse-operator.md) provede zkrácenou logickou disjunkci dvou `Boolean` výrazy.</span><span class="sxs-lookup"><span data-stu-id="ef941-126">Similarly, the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="ef941-127">Pokud k prvnímu výrazu v `OrElse` výraz vyhodnocen jako `True`, pak je výraz druhé není vyhodnotit, protože jej nelze změnit konečný výsledek a `OrElse` vrátí `True`.</span><span class="sxs-lookup"><span data-stu-id="ef941-127">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="ef941-128">Krátká smyčka kompromis</span><span class="sxs-lookup"><span data-stu-id="ef941-128">Short-Circuiting Trade-Offs</span></span>  
 <span data-ttu-id="ef941-129">Krátká smyčka může zlepšit výkon není vyhodnocením výraz, který nelze změnit výsledek logické operace.</span><span class="sxs-lookup"><span data-stu-id="ef941-129">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="ef941-130">Pokud tento výraz provede další akce, ale krátká smyčka přeskočí tyto akce.</span><span class="sxs-lookup"><span data-stu-id="ef941-130">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="ef941-131">Například, pokud výraz obsahuje volání `Function` postupu, že není procedura volána, pokud je výraz zkratována a všechny další kód obsažené v `Function` není spuštěna.</span><span class="sxs-lookup"><span data-stu-id="ef941-131">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="ef941-132">Proto funkce může spustit pouze občas a nemusí být testována správně.</span><span class="sxs-lookup"><span data-stu-id="ef941-132">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="ef941-133">Nebo program logiku může záviset na kód `Function`.</span><span class="sxs-lookup"><span data-stu-id="ef941-133">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="ef941-134">Následující příklad ukazuje rozdíl mezi `And`, `Or`a jejich short-circuiting protějšky.</span><span class="sxs-lookup"><span data-stu-id="ef941-134">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_5.vb)]  
  
 <span data-ttu-id="ef941-135">V předchozím příkladu, Všimněte si, že některé důležité kód uvnitř `checkIfValid()` nejde spustit po zkratována volání.</span><span class="sxs-lookup"><span data-stu-id="ef941-135">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="ef941-136">První `If` příkaz volání `checkIfValid()` i když `12 > 45` vrátí `False`, protože `And` není krátká smyčka.</span><span class="sxs-lookup"><span data-stu-id="ef941-136">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="ef941-137">Druhý `If` příkaz nevyvolá `checkIfValid()`, protože při `12 > 45` vrátí `False`, `AndAlso` zkratům druhý výraz.</span><span class="sxs-lookup"><span data-stu-id="ef941-137">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="ef941-138">Třetí `If` příkaz volání `checkIfValid()` i když `12 < 45` vrátí `True`, protože `Or` není krátká smyčka.</span><span class="sxs-lookup"><span data-stu-id="ef941-138">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="ef941-139">Čtvrtý `If` příkaz nevyvolá `checkIfValid()`, protože při `12 < 45` vrátí `True`, `OrElse` zkratům druhý výraz.</span><span class="sxs-lookup"><span data-stu-id="ef941-139">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="ef941-140">Bitové operace</span><span class="sxs-lookup"><span data-stu-id="ef941-140">Bitwise Operations</span></span>  
 <span data-ttu-id="ef941-141">Bitové operace vyhodnotit dvě celočíselné hodnoty v podobě binárního souboru (se základem 2).</span><span class="sxs-lookup"><span data-stu-id="ef941-141">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="ef941-142">Tyto porovnat bits na odpovídající pozic a přiřadit hodnoty, které jsou založeny na porovnávání.</span><span class="sxs-lookup"><span data-stu-id="ef941-142">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="ef941-143">Následující příklad ukazuje `And` operátor.</span><span class="sxs-lookup"><span data-stu-id="ef941-143">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_6.vb)]  
  
 <span data-ttu-id="ef941-144">V předchozím příkladu nastaví hodnotu `x` na 1.</span><span class="sxs-lookup"><span data-stu-id="ef941-144">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="ef941-145">To se stane z následujících důvodů:</span><span class="sxs-lookup"><span data-stu-id="ef941-145">This happens for the following reasons:</span></span>  
  
-   <span data-ttu-id="ef941-146">Hodnoty jsou považovány za binární:</span><span class="sxs-lookup"><span data-stu-id="ef941-146">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="ef941-147">3 v binárním formátu = 011</span><span class="sxs-lookup"><span data-stu-id="ef941-147">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="ef941-148">5 v binárním formátu = 101</span><span class="sxs-lookup"><span data-stu-id="ef941-148">5 in binary form = 101</span></span>  
  
-   <span data-ttu-id="ef941-149">`And` Operátor porovná binární reprezentace jednu binární pozici (verze) v čase.</span><span class="sxs-lookup"><span data-stu-id="ef941-149">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="ef941-150">Pokud jsou obě služby bits na dané pozici 1, 1 umístit na této pozici v výsledek.</span><span class="sxs-lookup"><span data-stu-id="ef941-150">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="ef941-151">Pokud je buď bit 0, 0 je umístěn na této pozici v výsledek.</span><span class="sxs-lookup"><span data-stu-id="ef941-151">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="ef941-152">V předchozím příkladu toto funguje takto:</span><span class="sxs-lookup"><span data-stu-id="ef941-152">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="ef941-153">011 (3 v binárním formátu)</span><span class="sxs-lookup"><span data-stu-id="ef941-153">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="ef941-154">101 (5 v binárním formátu)</span><span class="sxs-lookup"><span data-stu-id="ef941-154">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="ef941-155">001 (výsledek v binárním formátu)</span><span class="sxs-lookup"><span data-stu-id="ef941-155">001 (The result, in binary form)</span></span>  
  
-   <span data-ttu-id="ef941-156">Výsledkem je považována za decimal.</span><span class="sxs-lookup"><span data-stu-id="ef941-156">The result is treated as decimal.</span></span> <span data-ttu-id="ef941-157">Hodnota 001 je binární reprezentace 1, takže `x` = 1.</span><span class="sxs-lookup"><span data-stu-id="ef941-157">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="ef941-158">Bitové hodnotě `Or` operace je podobné, s tím rozdílem, že 1 je přiřazen k bit výsledek, pokud jedné nebo obou porovnání bits je 1.</span><span class="sxs-lookup"><span data-stu-id="ef941-158">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="ef941-159">`Xor`přiřadí bit výsledek 1, pokud právě jeden z porovnání služby bits (ne obojí) je 1.</span><span class="sxs-lookup"><span data-stu-id="ef941-159">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="ef941-160">`Not`má jeden operand Invertuje výběr všech bitů, včetně bit přihlášení a přiřadí tuto hodnotu na výsledek.</span><span class="sxs-lookup"><span data-stu-id="ef941-160">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="ef941-161">To znamená, že pro přihlášení kladná čísla `Not` vždy vrátí hodnotu záporná a záporná čísla `Not` vždy vrátí hodnotu u kladné číslo nebo nula.</span><span class="sxs-lookup"><span data-stu-id="ef941-161">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="ef941-162">`AndAlso` a `OrElse` operátory nepodporují bitové operace.</span><span class="sxs-lookup"><span data-stu-id="ef941-162">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef941-163">Bitové operace můžete provádět na pouze pro integrální typy.</span><span class="sxs-lookup"><span data-stu-id="ef941-163">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="ef941-164">Hodnoty s plovoucí desetinnou čárkou musí před pokračováním bitové operace převést na integrální typy.</span><span class="sxs-lookup"><span data-stu-id="ef941-164">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef941-165">Viz také</span><span class="sxs-lookup"><span data-stu-id="ef941-165">See Also</span></span>  
 [<span data-ttu-id="ef941-166">Logické/bitové operátory (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef941-166">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="ef941-167">Logické výrazy</span><span class="sxs-lookup"><span data-stu-id="ef941-167">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="ef941-168">Aritmetické operátory v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ef941-168">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="ef941-169">Operátory porovnání v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ef941-169">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="ef941-170">Operátory řetězení v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ef941-170">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [<span data-ttu-id="ef941-171">Účinná kombinace operátorů</span><span class="sxs-lookup"><span data-stu-id="ef941-171">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)