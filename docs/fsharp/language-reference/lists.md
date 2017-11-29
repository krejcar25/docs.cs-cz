---
title: Seznamy (F#)
description: "Další informace o F # seznamy, seřazené, neměnné řadu elementy stejného typu."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a1a6075f-064d-4aee-8222-2b59ff16cc12
ms.openlocfilehash: 5802a5a1c48ad05c1765c4c0fa2e8a81a92dee8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="lists"></a><span data-ttu-id="e08f4-104">Seznamy</span><span class="sxs-lookup"><span data-stu-id="e08f4-104">Lists</span></span>

> [!NOTE]
<span data-ttu-id="e08f4-105">Referenční dokumentace rozhraní API odkazů v tomto článku se dostanete na webu MSDN.</span><span class="sxs-lookup"><span data-stu-id="e08f4-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="e08f4-106">Referenční dokumentace rozhraní API docs.microsoft.com není dokončena.</span><span class="sxs-lookup"><span data-stu-id="e08f4-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="e08f4-107">Seznam v F # je seřazený, neměnné řadu elementy stejného typu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-107">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="e08f4-108">Provádění základních operací na seznamu, pomocí funkcí v [modul seznam](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="e08f4-108">To perform basic operations on lists, use the functions in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>


## <a name="creating-and-initializing-lists"></a><span data-ttu-id="e08f4-109">Vytváření a inicializace uvádí</span><span class="sxs-lookup"><span data-stu-id="e08f4-109">Creating and Initializing Lists</span></span>
<span data-ttu-id="e08f4-110">Můžete definovat seznam vypsáním explicitně prvky, oddělené středníky a uzavřeny do hranatých závorek, jak je znázorněno na následujícím řádku kódu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-110">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="e08f4-111">Můžete také vložit zalomení mezi elementy, v takovém případě jsou volitelné středníky.</span><span class="sxs-lookup"><span data-stu-id="e08f4-111">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="e08f4-112">Druhé syntaxe může způsobit srozumitelnější kódu po delší inicializace výrazy elementu, nebo když chcete zahrnout komentář pro jednotlivé elementy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-112">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="e08f4-113">Za normálních okolností všechny elementy seznamu musí být stejného typu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-113">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="e08f4-114">Výjimkou je, že seznam, ve kterém jsou elementy zadaný jako základní typ měli prvky, které jsou odvozené typy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-114">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="e08f4-115">Proto je následující přijatelný, protože obě `Button` a `CheckBox` odvozena od `Control`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-115">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="e08f4-116">Seznam prvků můžete definovat i pomocí rozsah indikovaný celých čísel oddělených operátor rozsahu (`..`), jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-116">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="e08f4-117">Prázdný seznam je zadaný pár hranaté závorky stálo mezi nimi.</span><span class="sxs-lookup"><span data-stu-id="e08f4-117">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="e08f4-118">Výraz pořadí také můžete vytvořit seznam.</span><span class="sxs-lookup"><span data-stu-id="e08f4-118">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="e08f4-119">V tématu [sekvenční výrazy](sequences.md#sequence-expressions) Další informace.</span><span class="sxs-lookup"><span data-stu-id="e08f4-119">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="e08f4-120">Například následující kód vytvoří seznam kvadratických celých čísel od 1 do 10.</span><span class="sxs-lookup"><span data-stu-id="e08f4-120">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="e08f4-121">Operátory pro práci s seznamy</span><span class="sxs-lookup"><span data-stu-id="e08f4-121">Operators for Working with Lists</span></span>
<span data-ttu-id="e08f4-122">Prvky v seznamu můžete připojit pomocí `::` – operátor (cons).</span><span class="sxs-lookup"><span data-stu-id="e08f4-122">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="e08f4-123">Pokud `list1` je `[2; 3; 4]`, následující kód vytvoří `list2` jako `[100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-123">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="e08f4-124">Můžete řetězení seznamy, které mají kompatibilní typy pomocí `@` operátor jako v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-124">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="e08f4-125">Pokud `list1` je `[2; 3; 4]` a `list2` je `[100; 2; 3; 4 ]`, tento kód vytvoří `list3` jako `[2; 3; 4; 100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-125">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4 ]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="e08f4-126">Funkce pro provádění operací na seznamy jsou k dispozici v [modul seznam](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="e08f4-126">Functions for performing operations on lists are available in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>

<span data-ttu-id="e08f4-127">Vzhledem k tomu, že seznamy v F # jsou neměnné, všechny změny operace generovat nové seznamy místo úprava existující seznamy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-127">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="e08f4-128">Seznamy v F # jsou implementované jako jednotlivě propojené seznamy, které znamená, že operace, které přístup pouze první pozice v seznamu jsou o(1), která, a element přístup je O (*n*).</span><span class="sxs-lookup"><span data-stu-id="e08f4-128">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>


## <a name="properties"></a><span data-ttu-id="e08f4-129">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="e08f4-129">Properties</span></span>
<span data-ttu-id="e08f4-130">Typ seznamu podporuje následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="e08f4-130">The list type supports the following properties:</span></span>

|<span data-ttu-id="e08f4-131">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="e08f4-131">Property</span></span>|<span data-ttu-id="e08f4-132">Typ</span><span class="sxs-lookup"><span data-stu-id="e08f4-132">Type</span></span>|<span data-ttu-id="e08f4-133">Popis</span><span class="sxs-lookup"><span data-stu-id="e08f4-133">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="e08f4-134">HEAD</span><span class="sxs-lookup"><span data-stu-id="e08f4-134">Head</span></span>](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)|`'T`|<span data-ttu-id="e08f4-135">První prvek.</span><span class="sxs-lookup"><span data-stu-id="e08f4-135">The first element.</span></span>|
|[<span data-ttu-id="e08f4-136">Prázdný</span><span class="sxs-lookup"><span data-stu-id="e08f4-136">Empty</span></span>](https://msdn.microsoft.com/library/44406ecb-1918-4d32-b32a-ca1f69840386)|`'T list`|<span data-ttu-id="e08f4-137">Statické vlastnosti, která vrací prázdný seznam příslušného typu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-137">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="e08f4-138">IsEmpty –</span><span class="sxs-lookup"><span data-stu-id="e08f4-138">IsEmpty</span></span>](https://msdn.microsoft.com/library/3ba087b2-2fc2-406d-b10a-cff6a19322da)|`bool`|<span data-ttu-id="e08f4-139">`true`Pokud seznam obsahuje žádné elementy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-139">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="e08f4-140">Položka</span><span class="sxs-lookup"><span data-stu-id="e08f4-140">Item</span></span>](https://msdn.microsoft.com/library/bdb2553a-0e54-4ff8-baed-ab1aac8f5dae)|`'T`|<span data-ttu-id="e08f4-141">Element v zadaném indexu (počítáno od nuly).</span><span class="sxs-lookup"><span data-stu-id="e08f4-141">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="e08f4-142">Délka</span><span class="sxs-lookup"><span data-stu-id="e08f4-142">Length</span></span>](https://msdn.microsoft.com/library/25f715c8-9daa-4c4d-a6c7-26772f9dab4d)|`int`|<span data-ttu-id="e08f4-143">Počet elementů.</span><span class="sxs-lookup"><span data-stu-id="e08f4-143">The number of elements.</span></span>|
|[<span data-ttu-id="e08f4-144">Tail</span><span class="sxs-lookup"><span data-stu-id="e08f4-144">Tail</span></span>](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)|`'T list`|<span data-ttu-id="e08f4-145">Seznam bez první prvek.</span><span class="sxs-lookup"><span data-stu-id="e08f4-145">The list without the first element.</span></span>|
<span data-ttu-id="e08f4-146">Tady jsou některé příklady použití těchto vlastností.</span><span class="sxs-lookup"><span data-stu-id="e08f4-146">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]
    
## <a name="using-lists"></a><span data-ttu-id="e08f4-147">Použití seznamů</span><span class="sxs-lookup"><span data-stu-id="e08f4-147">Using Lists</span></span>
<span data-ttu-id="e08f4-148">Programování s seznamy umožňuje provádět komplexní operace s malou část kódu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-148">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="e08f4-149">Tato část popisuje běžné operace na seznamy, které jsou důležité pro funkční programování.</span><span class="sxs-lookup"><span data-stu-id="e08f4-149">This section describes common operations on lists that are important to functional programming.</span></span>


### <a name="recursion-with-lists"></a><span data-ttu-id="e08f4-150">Rekurze se seznamy</span><span class="sxs-lookup"><span data-stu-id="e08f4-150">Recursion with Lists</span></span>
<span data-ttu-id="e08f4-151">Seznamy jsou jedinečně vhodná pro rekurzivní programování techniky.</span><span class="sxs-lookup"><span data-stu-id="e08f4-151">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="e08f4-152">Vezměte v úvahu operace, která je potřeba provést na každý element seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-152">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="e08f4-153">Můžete provést tento rekurzivně tak, že provoz na záhlaví seznamu a následné předání konec seznamu, která je menší seznam, který se skládá z původní seznam bez první prvek, znovu zpět na další úroveň rekurze.</span><span class="sxs-lookup"><span data-stu-id="e08f4-153">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="e08f4-154">Zápis rekurzivní funkci, použijte operátor cons (`::`) v porovnávání vzorů, což umožňuje oddělit head seznamu zadní.</span><span class="sxs-lookup"><span data-stu-id="e08f4-154">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="e08f4-155">Následující příklad kódu ukazuje, jak použít porovnávání vzorů k implementaci rekurzivní funkce, která provádí operace v seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-155">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="e08f4-156">Předchozí kód funguje dobře pro malé seznamy, ale pro větší seznamy ho může přetečení zásobníku.</span><span class="sxs-lookup"><span data-stu-id="e08f4-156">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="e08f4-157">Následující kód zlepšuje na tento kód pomocí argumentu akumulátorová standardní technika pro práci s rekurzivní funkce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-157">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="e08f4-158">Použití argumentu akumulátorová díky tail rekurzivní funkce, které šetří místo zásobníku.</span><span class="sxs-lookup"><span data-stu-id="e08f4-158">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="e08f4-159">Funkce `RemoveAllMultiples` je rekurzivní funkce, která přebírá dva seznamy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-159">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="e08f4-160">První seznam obsahuje čísla, jejichž násobků, které se odeberou, a druhý seznam je seznam, ze kterého mají být odebrány čísla.</span><span class="sxs-lookup"><span data-stu-id="e08f4-160">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="e08f4-161">Kód v následujícím příkladu používá k vyloučení všech jiných prime čísel ze seznamu, a seznam prvočísel v důsledku této rekurzivní funkce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-161">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="e08f4-162">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-162">The output is as follows:</span></span>

```
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="e08f4-163">Funkce modulu</span><span class="sxs-lookup"><span data-stu-id="e08f4-163">Module Functions</span></span>
<span data-ttu-id="e08f4-164">[Modul seznam](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) poskytuje funkce, které přístup k elementům seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-164">The [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) provides functions that access the elements of a list.</span></span> <span data-ttu-id="e08f4-165">Head element je nejrychlejší a nejjednodušší přístup.</span><span class="sxs-lookup"><span data-stu-id="e08f4-165">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="e08f4-166">Použijte vlastnost [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) nebo funkce modulu [list.HEAD –](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span><span class="sxs-lookup"><span data-stu-id="e08f4-166">Use the property [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) or the module function [List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span></span> <span data-ttu-id="e08f4-167">Máte přístup k konec seznamu pomocí [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) vlastnost nebo [list.Tail –](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) funkce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-167">You can access the tail of a list by using the [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) property or the [List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) function.</span></span> <span data-ttu-id="e08f4-168">Chcete-li při vyhledávání prvku pomocí indexu, použijte [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) funkce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-168">To find an element by index, use the [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) function.</span></span> <span data-ttu-id="e08f4-169">`List.nth`prochází seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-169">`List.nth` traverses the list.</span></span> <span data-ttu-id="e08f4-170">Proto je O (*n*).</span><span class="sxs-lookup"><span data-stu-id="e08f4-170">Therefore, it is O(*n*).</span></span> <span data-ttu-id="e08f4-171">Pokud váš kód používá `List.nth` často, můžete chtít zvážit použití pole místo seznam.</span><span class="sxs-lookup"><span data-stu-id="e08f4-171">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="e08f4-172">O(1), která je element přístup v polích.</span><span class="sxs-lookup"><span data-stu-id="e08f4-172">Element access in arrays is O(1).</span></span>


### <a name="boolean-operations-on-lists"></a><span data-ttu-id="e08f4-173">Na seznamu logických operací</span><span class="sxs-lookup"><span data-stu-id="e08f4-173">Boolean Operations on Lists</span></span>
<span data-ttu-id="e08f4-174">[List.IsEmpty –](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) funkce určuje, zda seznam obsahuje všechny elementy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-174">The [List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) function determines whether a list has any elements.</span></span>

<span data-ttu-id="e08f4-175">[List.EXISTS –](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) funkce se vztahuje na booleovskou hodnotu test, který prvky seznam a vrátí `true` Pokud libovolný element, splňuje test.</span><span class="sxs-lookup"><span data-stu-id="e08f4-175">The [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="e08f4-176">[List.exists2 –](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) se podobá ale funguje v následných páry elementů v dva seznamy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-176">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="e08f4-177">Následující kód ukazuje použití `List.exists`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-177">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="e08f4-178">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-178">The output is as follows:</span></span>

```
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="e08f4-179">Následující příklad ukazuje použití `List.exists2`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-179">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="e08f4-180">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-180">The output is as follows:</span></span>

```
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="e08f4-181">Můžete použít [list.ForAll –](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) Pokud chcete otestovat, zda všechny elementy seznamu splňují podmínku.</span><span class="sxs-lookup"><span data-stu-id="e08f4-181">You can use [List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="e08f4-182">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-182">The output is as follows:</span></span>

```
true
false
```

<span data-ttu-id="e08f4-183">Podobně [list.forall2 –](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) Určuje, zda splňují všechny elementy ve odpovídající pozice v dva seznamy logický výraz, který zahrnuje každý pár elementů.</span><span class="sxs-lookup"><span data-stu-id="e08f4-183">Similarly, [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="e08f4-184">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-184">The output is as follows:</span></span>

```
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="e08f4-185">Operace řazení v seznamech</span><span class="sxs-lookup"><span data-stu-id="e08f4-185">Sort Operations on Lists</span></span>
<span data-ttu-id="e08f4-186">[List.Sort –](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [list.sortby –](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), a [list.sortwith –](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) funkce seřadit seznamy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-186">The [List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), and [List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) functions sort lists.</span></span> <span data-ttu-id="e08f4-187">Funkce třídění určuje, které z těchto tří funkcí používat.</span><span class="sxs-lookup"><span data-stu-id="e08f4-187">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="e08f4-188">`List.sort`používá výchozí obecné porovnání.</span><span class="sxs-lookup"><span data-stu-id="e08f4-188">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="e08f4-189">Obecné porovnání pro porovnání hodnot používá globální operátory podle funkce obecné porovnání.</span><span class="sxs-lookup"><span data-stu-id="e08f4-189">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="e08f4-190">Efektivní funguje se širokou škálu element typy, jako je jednoduchý číselnými typy, řazené kolekce členů, záznamy, rozlišovaná sjednocení, seznamy, pole a žádný typ, který implementuje `System.IComparable`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-190">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="e08f4-191">Pro typy, které implementují `System.IComparable`, používá obecné porovnání `System.IComparable.CompareTo()` funkce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-191">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="e08f4-192">Obecné porovnání také funguje s řetězci, ale s pořadí řazení nezávislé na jazykové verzi.</span><span class="sxs-lookup"><span data-stu-id="e08f4-192">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="e08f4-193">Obecné porovnání není vhodné používat na nepodporované typy, jako jsou typy funkce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-193">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="e08f4-194">Navíc výkon obecné výchozím porovnáním je nejvhodnější pro malé strukturovaných typy; pro větší strukturovaných typy, které třeba porovnání a seřazeny často, zvažte implementaci `System.IComparable` a zajištění efektivní provádění `System.IComparable.CompareTo()` metoda.</span><span class="sxs-lookup"><span data-stu-id="e08f4-194">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="e08f4-195">`List.sortBy`provede funkci, která vrátí hodnotu, která se používá jako kritérium řazení a `List.sortWith` přijímá jako argument funkce porovnání.</span><span class="sxs-lookup"><span data-stu-id="e08f4-195">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="e08f4-196">Tyto pozdější dvě funkce jsou užitečné, když pracujete s typy, které nepodporují porovnání nebo při porovnání vyžaduje složitější sémantiku porovnání, jako v případě podporující jazykové verze řetězce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-196">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="e08f4-197">Následující příklad ukazuje použití `List.sort`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-197">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="e08f4-198">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-198">The output is as follows:</span></span>

```
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="e08f4-199">Následující příklad ukazuje použití `List.sortBy`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-199">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="e08f4-200">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-200">The output is as follows:</span></span>

```
[1; -2; 4; 5; 8]
```

<span data-ttu-id="e08f4-201">Další příklad ukazuje použití `List.sortWith`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-201">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="e08f4-202">V tomto příkladu vlastní porovnání funkce `compareWidgets` se používá k porovnání nejprve do jednoho pole z vlastního typu a pak další, kdy jsou stejné hodnoty první pole.</span><span class="sxs-lookup"><span data-stu-id="e08f4-202">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="e08f4-203">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-203">The output is as follows:</span></span>

```
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="e08f4-204">Operace hledání v seznamech</span><span class="sxs-lookup"><span data-stu-id="e08f4-204">Search Operations on Lists</span></span>
<span data-ttu-id="e08f4-205">Pro seznamy jsou podporovány mnoha operace hledání.</span><span class="sxs-lookup"><span data-stu-id="e08f4-205">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="e08f4-206">Nejjednodušším, [list.find –](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), umožňuje najít první prvek, který odpovídá dané podmínce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-206">The simplest, [List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="e08f4-207">Následující příklad kódu ukazuje použití `List.find` najít číslo, kterým dělitelná 5 v seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-207">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="e08f4-208">Výsledkem je 5.</span><span class="sxs-lookup"><span data-stu-id="e08f4-208">The result is 5.</span></span>

<span data-ttu-id="e08f4-209">Elementy musí nejdřív transformuje, kontaktujte [list.Pick –](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), což trvá funkci, vrátí možnost a hledá první možnost hodnotu, která je `Some(x)`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-209">If the elements must be transformed first, call [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="e08f4-210">Místo vrácení elementu `List.pick` vrátí výsledek `x`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-210">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="e08f4-211">Pokud se nenajde žádný odpovídající element, `List.pick` vyvolá `System.Collections.Generic.KeyNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-211">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="e08f4-212">Následující kód ukazuje použití `List.pick`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-212">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="e08f4-213">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-213">The output is as follows:</span></span>

```
"b"
```

<span data-ttu-id="e08f4-214">Jiná skupina operace hledání [list.tryfind –](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) a souvisejících funkcí, vrátí hodnotu možnosti.</span><span class="sxs-lookup"><span data-stu-id="e08f4-214">Another group of search operations, [List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) and related functions, return an option value.</span></span> <span data-ttu-id="e08f4-215">`List.tryFind` Funkce vrátí první prvek seznamu, který splňuje podmínku, pokud takový prvek existuje, ale hodnota možnosti `None` není-li.</span><span class="sxs-lookup"><span data-stu-id="e08f4-215">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="e08f4-216">Variaci [list.tryfindindex –](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) vrátí index elementu, pokud ho najde, místo elementu samotného.</span><span class="sxs-lookup"><span data-stu-id="e08f4-216">The variation [List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="e08f4-217">Tyto funkce jsou znázorněné v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-217">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="e08f4-218">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-218">The output is as follows:</span></span>

```
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="e08f4-219">Aritmetické operace na seznamy</span><span class="sxs-lookup"><span data-stu-id="e08f4-219">Arithmetic Operations on Lists</span></span>
<span data-ttu-id="e08f4-220">Běžné aritmetické operace, jako je sum a průměr jsou součástí [modul seznam](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="e08f4-220">Common arithmetic operations such as sum and average are built into the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="e08f4-221">Pro práci s [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), musí podporovat typ elementu seznamu `+` operátor a mít nulovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-221">To work with [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="e08f4-222">Všechny vestavěné typy aritmetické splňovat tyto podmínky.</span><span class="sxs-lookup"><span data-stu-id="e08f4-222">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="e08f4-223">Pro práci s [list.average –](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), typ elementu musí podporovat dělení beze zbytku, který vyloučí integrální typy, ale umožňuje plovoucí typy bodů.</span><span class="sxs-lookup"><span data-stu-id="e08f4-223">To work with [List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="e08f4-224">[List.sumby –](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) a [list.averageby –](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) funkce využít funkce jako parametr a výsledky tato funkce slouží k výpočtu hodnoty pro SUMA nebo průměr.</span><span class="sxs-lookup"><span data-stu-id="e08f4-224">The [List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) and [List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="e08f4-225">Následující kód ukazuje použití `List.sum`, `List.sumBy`, a `List.average`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-225">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="e08f4-226">Výstupem je `1.000000`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-226">The output is `1.000000`.</span></span>

<span data-ttu-id="e08f4-227">Následující kód ukazuje použití `List.averageBy`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-227">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="e08f4-228">Výstupem je `5.5`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-228">The output is `5.5`.</span></span>


### <a name="lists-and-tuples"></a><span data-ttu-id="e08f4-229">Seznamy a řazených kolekcí členů</span><span class="sxs-lookup"><span data-stu-id="e08f4-229">Lists and Tuples</span></span>
<span data-ttu-id="e08f4-230">Seznamy, které obsahují řazených kolekcí členů smí uživatel manipulovat zip a rozbalte funkce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-230">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="e08f4-231">Tyto funkce sloučit dva seznamy jeden hodnot do jediného seznamu řazené kolekce členů nebo oddělení jeden seznam řazených kolekcí členů do dva seznamy jedné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="e08f4-231">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="e08f4-232">Nejjednodušším [list.zip –](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) funkce přebírá dva seznamy jednotlivé prvky a vytvoří jeden seznam dvojic řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="e08f4-232">The simplest [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="e08f4-233">Jiná verze [list.zip3 –](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), trvá tři seznam jednotlivé prvky a vytvoří jeden seznam záznamů, které mají tři prvky.</span><span class="sxs-lookup"><span data-stu-id="e08f4-233">Another version, [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="e08f4-234">Následující příklad kódu ukazuje použití `List.zip`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-234">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="e08f4-235">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-235">The output is as follows:</span></span>

```
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="e08f4-236">Následující příklad kódu ukazuje použití `List.zip3`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-236">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="e08f4-237">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-237">The output is as follows:</span></span>

```
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="e08f4-238">Odpovídající verze, rozbalte [list.Unzip –](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) a [list.unzip3 –](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), provést seznam řazených kolekcí členů a vrátí seznamy v řazené kolekce členů, kde první seznam obsahuje všechny elementy, které byly první v každá řazená kolekce členů a druhý seznam obsahuje druhý prvkem každý řazené kolekce členů, a tak dále.</span><span class="sxs-lookup"><span data-stu-id="e08f4-238">The corresponding unzip versions, [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) and [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="e08f4-239">Následující příklad kódu ukazuje použití [list.Unzip –](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span><span class="sxs-lookup"><span data-stu-id="e08f4-239">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="e08f4-240">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-240">The output is as follows:</span></span>

```
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="e08f4-241">Následující příklad kódu ukazuje použití [list.unzip3 –](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span><span class="sxs-lookup"><span data-stu-id="e08f4-241">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="e08f4-242">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-242">The output is as follows:</span></span>

```
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="e08f4-243">Pracující na prvky seznamu</span><span class="sxs-lookup"><span data-stu-id="e08f4-243">Operating on List Elements</span></span>
<span data-ttu-id="e08f4-244">F # podporuje různé operace v seznamu elementů.</span><span class="sxs-lookup"><span data-stu-id="e08f4-244">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="e08f4-245">Nejjednodušší je [list.ITER –](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), což umožňuje volání funkce na každý element seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-245">The simplest is [List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="e08f4-246">Zahrnout variace [list.iter2 –](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), které umožňuje provádět operace s elementy dva seznamy [list.iteri –](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), což je jako `List.iter` s tím rozdílem, že index jednotlivých prvků se předá jako argumentem této funkce, která je volána pro každý prvek a [list.iteri2 –](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), který je kombinací funkce `List.iter2` a `List.iteri`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-246">Variations include [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), which enables you to perform an operation on elements of two lists, [List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="e08f4-247">Následující příklad kódu ukazuje tyto funkce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-247">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="e08f4-248">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-248">The output is as follows:</span></span>

```
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="e08f4-249">Jiné často používané funkce, která transformuje seznamu elementů je [list.map –](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), který můžete použít funkci pro každý prvek seznamu a všechny výsledky do nového seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-249">Another frequently used function that transforms list elements is [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="e08f4-250">[List.map2 –](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) a [list.map3 –](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) jsou variace, které trvat více seznamů.</span><span class="sxs-lookup"><span data-stu-id="e08f4-250">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) and [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) are variations that take multiple lists.</span></span> <span data-ttu-id="e08f4-251">Můžete také použít [list.MAPI –](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) a [list.mapi2 –](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), pokud kromě elementu, musí být předán index jednotlivých prvků funkce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-251">You can also use [List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) and [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="e08f4-252">Jediným rozdílem mezi `List.mapi2` a `List.mapi` je, že `List.mapi2` pracuje se dvěma seznamy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-252">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="e08f4-253">Následující příklad ilustruje [list.map –](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span><span class="sxs-lookup"><span data-stu-id="e08f4-253">The following example illustrates [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="e08f4-254">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-254">The output is as follows:</span></span>

```
[2; 3; 4]
```

<span data-ttu-id="e08f4-255">Následující příklad ukazuje použití `List.map2`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-255">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="e08f4-256">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-256">The output is as follows:</span></span>

```
[5; 7; 9]
```

<span data-ttu-id="e08f4-257">Následující příklad ukazuje použití `List.map3`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-257">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="e08f4-258">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-258">The output is as follows:</span></span>

```
[7; 10; 13]
```

<span data-ttu-id="e08f4-259">Následující příklad ukazuje použití `List.mapi`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-259">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="e08f4-260">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-260">The output is as follows:</span></span>

```
[1; 3; 5]
```

<span data-ttu-id="e08f4-261">Následující příklad ukazuje použití `List.mapi2`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-261">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="e08f4-262">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-262">The output is as follows:</span></span>

```
[0; 7; 18]
```

<span data-ttu-id="e08f4-263">[List.Collect –](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) jako `List.map`kromě toho, že každý prvek vytváří seznamu a všechny tyto seznamy jsou zřetězeny do konečné seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-263">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="e08f4-264">V následujícím kódu generuje každý element seznamu tří čísel.</span><span class="sxs-lookup"><span data-stu-id="e08f4-264">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="e08f4-265">Všechny se shromažďují do jediného seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-265">These are all collected into one list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="e08f4-266">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-266">The output is as follows:</span></span>

```
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="e08f4-267">Můžete také použít [list.Filter –](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), který přebírá podmínce logické a vytvoří nový seznam, který se skládá jenom z elementů, které splňují danou podmínku.</span><span class="sxs-lookup"><span data-stu-id="e08f4-267">You can also use [List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="e08f4-268">V rozevíracím seznamu je `[2; 4; 6]`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-268">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="e08f4-269">V kombinaci mapy a filtr [list.Choose –](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) vám umožňuje transformovat a vybrat elementy ve stejnou dobu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-269">A combination of map and filter, [List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="e08f4-270">`List.choose`funkci, která vrátí možnost každý prvek seznamu a vrátí nový seznam výsledky pro elementy při funkce vrátí hodnotu možnost se vztahuje `Some`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-270">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="e08f4-271">Následující kód ukazuje použití `List.choose` vyberte převedených na velká písmena slova mimo seznam slov.</span><span class="sxs-lookup"><span data-stu-id="e08f4-271">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="e08f4-272">Výstup vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e08f4-272">The output is as follows:</span></span>

```
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="e08f4-273">Pracující na více seznamů</span><span class="sxs-lookup"><span data-stu-id="e08f4-273">Operating on Multiple Lists</span></span>
<span data-ttu-id="e08f4-274">Seznamy je možné připojit společně.</span><span class="sxs-lookup"><span data-stu-id="e08f4-274">Lists can be joined together.</span></span> <span data-ttu-id="e08f4-275">Chcete-li připojit dva seznamy do jednoho, použijte [list.Append –](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span><span class="sxs-lookup"><span data-stu-id="e08f4-275">To join two lists into one, use [List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span></span> <span data-ttu-id="e08f4-276">Chcete-li připojit k více než dva seznamy, použijte [list.Concat –](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span><span class="sxs-lookup"><span data-stu-id="e08f4-276">To join more than two lists, use [List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet26.fs)]
    
### <a name="fold-and-scan-operations"></a><span data-ttu-id="e08f4-277">Operace kontroly a skládání</span><span class="sxs-lookup"><span data-stu-id="e08f4-277">Fold and Scan Operations</span></span>
<span data-ttu-id="e08f4-278">Některé operace výpisu zahrnovat vzájemné závislosti mezi všechny elementy seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-278">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="e08f4-279">Operace násobek a kontroly jsou jako `List.iter` a `List.map` v tom vyvolání funkce pro každý element, ale tyto operace poskytnout další parametr s názvem *akumulátorová* , přenáší informace Výpočet.</span><span class="sxs-lookup"><span data-stu-id="e08f4-279">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="e08f4-280">Použití `List.fold` provedení výpočtů v seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-280">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="e08f4-281">Následující příklad kódu ukazuje použití [list.fold –](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) provádět různé operace.</span><span class="sxs-lookup"><span data-stu-id="e08f4-281">The following code example demonstrates the use of [List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) to perform various operations.</span></span>

<span data-ttu-id="e08f4-282">Je seznam vyčerpán; je zásobník `acc` je hodnota, která se předají jako výpočet pokračuje.</span><span class="sxs-lookup"><span data-stu-id="e08f4-282">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="e08f4-283">První argument trvá je zásobník a element seznamu a vrátí dočasné výsledek výpočtu pro daný element seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-283">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="e08f4-284">Druhý argument je počáteční hodnota je zásobník.</span><span class="sxs-lookup"><span data-stu-id="e08f4-284">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="e08f4-285">Verze tyto funkce, které mají číslice v názvu funkce fungovat na více než jeden seznam.</span><span class="sxs-lookup"><span data-stu-id="e08f4-285">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="e08f4-286">Například [list.fold2 –](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) provede výpočty dva seznamy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-286">For example, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) performs computations on two lists.</span></span>

<span data-ttu-id="e08f4-287">Následující příklad ukazuje použití `List.fold2`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-287">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="e08f4-288">`List.fold`a [list.Scan –](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) se liší v tom, že `List.fold` vrátí poslední hodnotu speciálním parametrem, ale `List.scan` vrátí seznam pomocných hodnot (spolu s konečná hodnota) navíc parametru.</span><span class="sxs-lookup"><span data-stu-id="e08f4-288">`List.fold` and [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="e08f4-289">Každá z těchto funkcí zpětného variace, například zahrnuje [list.foldback –](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), který se liší v pořadí, ve které je seznam vyčerpán a pořadí argumentů.</span><span class="sxs-lookup"><span data-stu-id="e08f4-289">Each of these functions includes a reverse variation, for example, [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="e08f4-290">Navíc `List.fold` a `List.foldBack` mají varianty, [list.fold2 –](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) a [list.foldback2 –](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), které přebírají dva seznamy stejné délky.</span><span class="sxs-lookup"><span data-stu-id="e08f4-290">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) and [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), that take two lists of equal length.</span></span> <span data-ttu-id="e08f4-291">Funkce, která spustí pro každý element můžete použít odpovídající elementy oba seznamy k provedení několika akcí.</span><span class="sxs-lookup"><span data-stu-id="e08f4-291">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="e08f4-292">Element typy dva seznamy může být jiné, jako v následujícím příkladu, ve kterém jeden seznam obsahuje objemy transakcí pro účet bank a další seznam obsahuje typ transakce: uložení nebo stažení.</span><span class="sxs-lookup"><span data-stu-id="e08f4-292">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="e08f4-293">Výpočet jako sumarizační `List.fold` a `List.foldBack` mají stejný účinek, protože výsledek nezávisí v řádu traversal.</span><span class="sxs-lookup"><span data-stu-id="e08f4-293">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="e08f4-294">V následujícím příkladu `List.foldBack` se používá k přidání elementů v seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-294">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="e08f4-295">Následující příklad vrátí příkladu bankovní účet.</span><span class="sxs-lookup"><span data-stu-id="e08f4-295">The following example returns to the bank account example.</span></span> <span data-ttu-id="e08f4-296">Tentokrát je přidání nového typu transakce: výpočtu vás zajímají.</span><span class="sxs-lookup"><span data-stu-id="e08f4-296">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="e08f4-297">Konečný zůstatek teď závisí v řádu transakce.</span><span class="sxs-lookup"><span data-stu-id="e08f4-297">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="e08f4-298">Funkce [list.reduce –](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) je něco jako `List.fold` a `List.scan`kromě toho, že místo předávání kolem samostatné akumulátoru, `List.reduce` trvá funkci, která má dva argumenty typu prvku místo jenom jeden a jeden z těchto argumentů funguje jako je zásobník, což znamená, ukládá zprostředkující výsledek výpočet.</span><span class="sxs-lookup"><span data-stu-id="e08f4-298">The function [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="e08f4-299">`List.reduce`spustí na provoz na prvních dvou seznam prvků a potom pomocí výsledek operace spolu s další prvek.</span><span class="sxs-lookup"><span data-stu-id="e08f4-299">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="e08f4-300">Protože samostatné akumulátorová, který má vlastní typ není `List.reduce` lze místě `List.fold` pouze když je zásobník a typ elementu mají stejného typu.</span><span class="sxs-lookup"><span data-stu-id="e08f4-300">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="e08f4-301">Následující kód ukazuje použití `List.reduce`.</span><span class="sxs-lookup"><span data-stu-id="e08f4-301">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="e08f4-302">`List.reduce`vyvolá výjimku, pokud zadaný seznam obsahuje žádné elementy.</span><span class="sxs-lookup"><span data-stu-id="e08f4-302">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="e08f4-303">V následujícím kódu první volání výrazu lambda získá argumenty, 2 a 4 a vrátí hodnotu 6, a další volání je zadané argumenty 6 a 10, tak, aby výsledkem 16.</span><span class="sxs-lookup"><span data-stu-id="e08f4-303">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet33.fs)]
    
### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="e08f4-304">Převod mezi seznamy a další typy kolekcí</span><span class="sxs-lookup"><span data-stu-id="e08f4-304">Converting Between Lists and Other Collection Types</span></span>
<span data-ttu-id="e08f4-305">`List` Modul poskytuje funkce pro převod do a z pořadí a pole.</span><span class="sxs-lookup"><span data-stu-id="e08f4-305">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="e08f4-306">Chcete-li převést do nebo z sekvenci, použijte [list.toseq –](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) nebo [list.ofseq –](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span><span class="sxs-lookup"><span data-stu-id="e08f4-306">To convert to or from a sequence, use [List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) or [List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span></span> <span data-ttu-id="e08f4-307">Chcete-li převést do nebo z pole, použijte [list.ToArray –](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) nebo [list.ofarray –](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span><span class="sxs-lookup"><span data-stu-id="e08f4-307">To convert to or from an array, use [List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) or [List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span></span>


### <a name="additional-operations"></a><span data-ttu-id="e08f4-308">Další operace</span><span class="sxs-lookup"><span data-stu-id="e08f4-308">Additional Operations</span></span>
<span data-ttu-id="e08f4-309">Informace o dalších operacích v seznamech najdete v tématu v referenčním tématu knihovny [Collections.list – modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="e08f4-309">For information about additional operations on lists, see the library reference topic [Collections.List Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span></span>


## <a name="see-also"></a><span data-ttu-id="e08f4-310">Viz také</span><span class="sxs-lookup"><span data-stu-id="e08f4-310">See Also</span></span>
[<span data-ttu-id="e08f4-311">Referenční dokumentace jazyka F #</span><span class="sxs-lookup"><span data-stu-id="e08f4-311">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="e08f4-312">Typy F #</span><span class="sxs-lookup"><span data-stu-id="e08f4-312">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="e08f4-313">Pořadí</span><span class="sxs-lookup"><span data-stu-id="e08f4-313">Sequences</span></span>](sequences.md)

[<span data-ttu-id="e08f4-314">Pole</span><span class="sxs-lookup"><span data-stu-id="e08f4-314">Arrays</span></span>](arrays.md)

[<span data-ttu-id="e08f4-315">Možnosti</span><span class="sxs-lookup"><span data-stu-id="e08f4-315">Options</span></span>](options.md)