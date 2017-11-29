---
title: "yield (Referenční dokumentace jazyka C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords: yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
caps.latest.revision: "46"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4735ab33faea71b792cbc6b567884b64bd6ca029
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="yield-c-reference"></a><span data-ttu-id="0c81b-102">yield (Referenční dokumentace jazyka C#)</span><span class="sxs-lookup"><span data-stu-id="0c81b-102">yield (C# Reference)</span></span>
<span data-ttu-id="0c81b-103">Při použití `yield` – klíčové slovo v příkazu, které označuje, že metoda, operátor, nebo `get` přistupujícího objektu, ve kterých se vyskytuje je iterátor.</span><span class="sxs-lookup"><span data-stu-id="0c81b-103">When you use the `yield` keyword in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="0c81b-104">Pomocí `yield` k definování iterovat odebírá potřebu, explicitní navíc – třída (třída, která obsahuje stav pro výčet, najdete v části <xref:System.Collections.Generic.IEnumerator%601> příklad) při implementaci <xref:System.Collections.IEnumerable> a <xref:System.Collections.IEnumerator> vzor pro vlastní shromažďování typ.</span><span class="sxs-lookup"><span data-stu-id="0c81b-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>  
  
 <span data-ttu-id="0c81b-105">Následující příklad ukazuje dva způsoby `yield` příkaz.</span><span class="sxs-lookup"><span data-stu-id="0c81b-105">The following example shows the two forms of the `yield` statement.</span></span>  
  
```csharp  
yield return <expression>;  
yield break;  
```  
  
## <a name="remarks"></a><span data-ttu-id="0c81b-106">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0c81b-106">Remarks</span></span>  
 <span data-ttu-id="0c81b-107">Můžete použít `yield return` příkaz vrátit každý element, jeden v čase.</span><span class="sxs-lookup"><span data-stu-id="0c81b-107">You use a `yield return` statement to return each element one at a time.</span></span>  
  
 <span data-ttu-id="0c81b-108">Používat metodu iterator přes [foreach](../../../csharp/language-reference/keywords/foreach-in.md) příkaz nebo dotaz LINQ.</span><span class="sxs-lookup"><span data-stu-id="0c81b-108">You consume an iterator method by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="0c81b-109">Každé iteraci `foreach` smyčky volá metodu iterator.</span><span class="sxs-lookup"><span data-stu-id="0c81b-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="0c81b-110">Když `yield return` příkaz je dosaženo v metodě iterator `expression` se vrátí, a se uchovávají aktuální umístění v kódu.</span><span class="sxs-lookup"><span data-stu-id="0c81b-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="0c81b-111">Provádění je restartováno ze zmíněného umístění pokaždé, když je zavolána funkce iterátoru.</span><span class="sxs-lookup"><span data-stu-id="0c81b-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="0c81b-112">Můžete použít `yield break` příkaz k ukončení iterace.</span><span class="sxs-lookup"><span data-stu-id="0c81b-112">You can use a `yield break` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="0c81b-113">Další informace o iterátory najdete v tématu [iterátory](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="0c81b-113">For more information about iterators, see [Iterators](../../iterators.md).</span></span>  
  
## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="0c81b-114">Iterátory a přístupové objekty get</span><span class="sxs-lookup"><span data-stu-id="0c81b-114">Iterator Methods and get Accessors</span></span>  
 <span data-ttu-id="0c81b-115">Deklarace iterátoru musí splňovat následující požadavky:</span><span class="sxs-lookup"><span data-stu-id="0c81b-115">The declaration of an iterator must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="0c81b-116">Návratový typ musí být <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, nebo <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="0c81b-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="0c81b-117">Deklaraci nemůže mít žádné [ref](../../../csharp/language-reference/keywords/ref.md) nebo [out](../../../csharp/language-reference/keywords/out.md) parametry.</span><span class="sxs-lookup"><span data-stu-id="0c81b-117">The declaration can't have any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters.</span></span>  
  
 <span data-ttu-id="0c81b-118">`yield` Typ iterátor, který vrátí <xref:System.Collections.IEnumerable> nebo <xref:System.Collections.IEnumerator> je `object`.</span><span class="sxs-lookup"><span data-stu-id="0c81b-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="0c81b-119">Pokud vrátí iteraci <xref:System.Collections.Generic.IEnumerable%601> nebo <xref:System.Collections.Generic.IEnumerator%601>, musí být implicitní převod z typu výraz v `yield return` příkaz, který má parametr obecného typu.</span><span class="sxs-lookup"><span data-stu-id="0c81b-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>  
  
 <span data-ttu-id="0c81b-120">Nelze zahrnout `yield return` nebo `yield break` příkaz v metody, které mají následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="0c81b-120">You can't include a `yield return` or `yield break` statement in methods that have the following characteristics:</span></span>  
  
-   <span data-ttu-id="0c81b-121">Anonymní metody.</span><span class="sxs-lookup"><span data-stu-id="0c81b-121">Anonymous methods.</span></span> <span data-ttu-id="0c81b-122">Další informace najdete v tématu [anonymní metody](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0c81b-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
-   <span data-ttu-id="0c81b-123">Metody, které obsahují nebezpečné bloky.</span><span class="sxs-lookup"><span data-stu-id="0c81b-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="0c81b-124">Další informace najdete v tématu [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="0c81b-124">For more information, see [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="0c81b-125">Zpracování výjimek</span><span class="sxs-lookup"><span data-stu-id="0c81b-125">Exception Handling</span></span>  
 <span data-ttu-id="0c81b-126">A `yield return` příkaz nebyl nalezen v bloku try-catch.</span><span class="sxs-lookup"><span data-stu-id="0c81b-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="0c81b-127">A `yield return` příkaz se může nacházet v zkuste bloku příkazu try-finally –.</span><span class="sxs-lookup"><span data-stu-id="0c81b-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>  
  
 <span data-ttu-id="0c81b-128">A `yield break` příkaz může být umístěno v bloku try nebo catch bloku, ale není a nakonec blokovat.</span><span class="sxs-lookup"><span data-stu-id="0c81b-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>  
  
 <span data-ttu-id="0c81b-129">Pokud `foreach` textu (mimo metodu iterator) vyvolá výjimku, `finally` bloku v metodě iterator se spustí.</span><span class="sxs-lookup"><span data-stu-id="0c81b-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="0c81b-130">Technická implementace</span><span class="sxs-lookup"><span data-stu-id="0c81b-130">Technical Implementation</span></span>  
 <span data-ttu-id="0c81b-131">Následující kód vrátí `IEnumerable<string>` z metody iterator a pak iteruje jejích elementů.</span><span class="sxs-lookup"><span data-stu-id="0c81b-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>  
  
```csharp  
IEnumerable<string> elements = MyIteratorMethod();  
foreach (string element in elements)  
{  
   ...  
}  
```  
  
 <span data-ttu-id="0c81b-132">Volání `MyIteratorMethod` neprovede těla metody.</span><span class="sxs-lookup"><span data-stu-id="0c81b-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="0c81b-133">Místo toho se volání vrátí `IEnumerable<string>` do `elements` proměnné.</span><span class="sxs-lookup"><span data-stu-id="0c81b-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="0c81b-134">Na iterace `foreach` smyčky, <xref:System.Collections.IEnumerator.MoveNext%2A> metoda je volána pro `elements`.</span><span class="sxs-lookup"><span data-stu-id="0c81b-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="0c81b-135">Toto volání provede text `MyIteratorMethod` až do dalšího `yield return` je dosaženo příkaz.</span><span class="sxs-lookup"><span data-stu-id="0c81b-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="0c81b-136">Výraz vrácený `yield return` příkaz určuje nejen hodnotu `element` proměnná pro spotřeba těla smyčky, ale také <xref:System.Collections.Generic.IEnumerator%601.Current%2A> vlastnost `elements`, který je `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="0c81b-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>  
  
 <span data-ttu-id="0c81b-137">Při každém opakování následné `foreach` cykly, odkud pokračuje v provádění těla iterator bylo přerušeno, znovu zastavit při dosažení `yield return` příkaz.</span><span class="sxs-lookup"><span data-stu-id="0c81b-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="0c81b-138">`foreach` Dokončení smyčky, kdy konec metodu iterator nebo `yield break` je dosaženo příkaz.</span><span class="sxs-lookup"><span data-stu-id="0c81b-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c81b-139">Příklad</span><span class="sxs-lookup"><span data-stu-id="0c81b-139">Example</span></span>  
 <span data-ttu-id="0c81b-140">V následujícím příkladu má `yield return` příkaz, který je uvnitř `for` smyčky.</span><span class="sxs-lookup"><span data-stu-id="0c81b-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="0c81b-141">Každé iteraci `foreach` těla příkazu v `Process` vytvoří volání `Power` iterator funkce.</span><span class="sxs-lookup"><span data-stu-id="0c81b-141">Each iteration of the `foreach` statement body in `Process` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="0c81b-142">Každé volání funkce iterator pokračuje dalším spuštění `yield return` příkaz, který spadá další iterace `for` smyčky.</span><span class="sxs-lookup"><span data-stu-id="0c81b-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>  
  
 <span data-ttu-id="0c81b-143">Návratový typ metody iterator <xref:System.Collections.IEnumerable>, který je typu iterator rozhraní.</span><span class="sxs-lookup"><span data-stu-id="0c81b-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="0c81b-144">Při volání metody iterátoru je vrácen vyčíslitelný objekt, který obsahuje mocniny čísla.</span><span class="sxs-lookup"><span data-stu-id="0c81b-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="0c81b-145">Příklad</span><span class="sxs-lookup"><span data-stu-id="0c81b-145">Example</span></span>  
 <span data-ttu-id="0c81b-146">Následující příklad ukazuje `get` přistupujícího objektu, který je iterátor.</span><span class="sxs-lookup"><span data-stu-id="0c81b-146">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="0c81b-147">V příkladu každý `yield return` příkaz vrací instanci třídy definovaný uživatelem.</span><span class="sxs-lookup"><span data-stu-id="0c81b-147">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0c81b-148">Specifikace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="0c81b-148">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c81b-149">Viz také</span><span class="sxs-lookup"><span data-stu-id="0c81b-149">See Also</span></span>  
 [<span data-ttu-id="0c81b-150">Referenční dokumentace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="0c81b-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0c81b-151">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="0c81b-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0c81b-152">foreach v</span><span class="sxs-lookup"><span data-stu-id="0c81b-152">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="0c81b-153">Iterátory</span><span class="sxs-lookup"><span data-stu-id="0c81b-153">Iterators</span></span>](../../iterators.md)