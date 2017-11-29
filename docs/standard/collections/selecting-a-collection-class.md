---
title: "Výběr třídy kolekce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- last-in-first-out collections
- first-in-first-out collections
- collections [.NET Framework], selecting collection class
- indexed collections
- Collections classes
- grouping data in collections, selecting collection class
ms.assetid: ba049f9a-ce87-4cc4-b319-3f75c8ddac8a
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64b50839a5500b671a4bd5dd92eec2f0db9787a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="selecting-a-collection-class"></a><span data-ttu-id="b83b5-102">Výběr třídy kolekce</span><span class="sxs-lookup"><span data-stu-id="b83b5-102">Selecting a Collection Class</span></span>
<span data-ttu-id="b83b5-103">Ujistěte se, že pečlivě zvolte třídě kolekce.</span><span class="sxs-lookup"><span data-stu-id="b83b5-103">Be sure to choose your collection class carefully.</span></span> <span data-ttu-id="b83b5-104">Pomocí nesprávného typu může omezit použití kolekce.</span><span class="sxs-lookup"><span data-stu-id="b83b5-104">Using the wrong type can restrict your use of the collection.</span></span> <span data-ttu-id="b83b5-105">Obecně platí, nepoužívejte typy v <xref:System.Collections> obor názvů Pokud jsou konkrétně cílení na rozhraní .NET Framework verze 1.1.</span><span class="sxs-lookup"><span data-stu-id="b83b5-105">In general, avoid using the types in the <xref:System.Collections> namespace unless you are specifically targeting .NET Framework version 1.1.</span></span> <span data-ttu-id="b83b5-106">Obecné a souběžné verze kolekcí jsou upřednostňované z důvodu jejich vyšší bezpečnost typů a dalších vylepšení.</span><span class="sxs-lookup"><span data-stu-id="b83b5-106">The generic and concurrent versions of the collections are to be preferred because of their greater type safety and other improvements.</span></span>  
  
 <span data-ttu-id="b83b5-107">Zvažte následující otázky:</span><span class="sxs-lookup"><span data-stu-id="b83b5-107">Consider the following questions:</span></span>  
  
-   <span data-ttu-id="b83b5-108">Potřebujete seznam sekvenční, kde element obvykle odstraněn po načtení jeho hodnoty?</span><span class="sxs-lookup"><span data-stu-id="b83b5-108">Do you need a sequential list where the element is typically discarded after its value is retrieved?</span></span>  
  
    -   <span data-ttu-id="b83b5-109">Pokud ano, zvažte použití <xref:System.Collections.Queue> třídy nebo <xref:System.Collections.Generic.Queue%601> obecné třídy, pokud potřebujete first in, chování použity.</span><span class="sxs-lookup"><span data-stu-id="b83b5-109">If yes, consider using the <xref:System.Collections.Queue> class or the <xref:System.Collections.Generic.Queue%601> generic class if you need first-in, first-out (FIFO) behavior.</span></span> <span data-ttu-id="b83b5-110">Zvažte použití <xref:System.Collections.Stack> třídy nebo <xref:System.Collections.Generic.Stack%601> obecné třídy, pokud potřebujete last-in, první ven (LIFO) chování.</span><span class="sxs-lookup"><span data-stu-id="b83b5-110">Consider using the <xref:System.Collections.Stack> class or the <xref:System.Collections.Generic.Stack%601> generic class if you need last-in, first-out (LIFO) behavior.</span></span> <span data-ttu-id="b83b5-111">Pro bezpečný přístup z více vláken, použijte souběžné verze <xref:System.Collections.Concurrent.ConcurrentQueue%601> a <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="b83b5-111">For safe access from multiple threads, use the concurrent versions <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
    -   <span data-ttu-id="b83b5-112">Pokud ne, zvažte použití jiné kolekce.</span><span class="sxs-lookup"><span data-stu-id="b83b5-112">If not, consider using the other collections.</span></span>  
  
-   <span data-ttu-id="b83b5-113">Potřebujete přístup k elementům v určitém pořadí, jako je například FIFO, LIFO, nebo náhodné?</span><span class="sxs-lookup"><span data-stu-id="b83b5-113">Do you need to access the elements in a certain order, such as FIFO, LIFO, or random?</span></span>  
  
    -   <span data-ttu-id="b83b5-114"><xref:System.Collections.Queue> Třídy a <xref:System.Collections.Generic.Queue%601> nebo <xref:System.Collections.Concurrent.ConcurrentQueue%601> obecná třída nabízí přístup FIFO.</span><span class="sxs-lookup"><span data-stu-id="b83b5-114">The <xref:System.Collections.Queue> class and the <xref:System.Collections.Generic.Queue%601> or <xref:System.Collections.Concurrent.ConcurrentQueue%601> generic class offer FIFO access.</span></span> <span data-ttu-id="b83b5-115">Další informace najdete v tématu [kdy použít kolekci s bezpečnými vlákny](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).</span><span class="sxs-lookup"><span data-stu-id="b83b5-115">For more information, see [When to Use a Thread-Safe Collection](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).</span></span>  
  
    -   <span data-ttu-id="b83b5-116"><xref:System.Collections.Stack> Třídy a <xref:System.Collections.Generic.Stack%601> nebo <xref:System.Collections.Concurrent.ConcurrentStack%601> obecná třída nabízí přístup LIFO.</span><span class="sxs-lookup"><span data-stu-id="b83b5-116">The <xref:System.Collections.Stack> class and the <xref:System.Collections.Generic.Stack%601> or <xref:System.Collections.Concurrent.ConcurrentStack%601> generic class offer LIFO access.</span></span> <span data-ttu-id="b83b5-117">Další informace najdete v tématu [kdy použít kolekci s bezpečnými vlákny](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).</span><span class="sxs-lookup"><span data-stu-id="b83b5-117">For more information, see [When to Use a Thread-Safe Collection](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).</span></span>  
  
    -   <span data-ttu-id="b83b5-118"><xref:System.Collections.Generic.LinkedList%601> Obecná třída umožňuje sekvenční přístup ze začátku na konec nebo z tail do hlavičky.</span><span class="sxs-lookup"><span data-stu-id="b83b5-118">The <xref:System.Collections.Generic.LinkedList%601> generic class allows sequential access either from the head to the tail, or from the tail to the head.</span></span>  
  
-   <span data-ttu-id="b83b5-119">Potřebujete přístup každý prvek index?</span><span class="sxs-lookup"><span data-stu-id="b83b5-119">Do you need to access each element by index?</span></span>  
  
    -   <span data-ttu-id="b83b5-120"><xref:System.Collections.ArrayList> a <xref:System.Collections.Specialized.StringCollection> třídy a <xref:System.Collections.Generic.List%601> – obecná třída nabídka přístup k jejich elementů podle index elementu založený na nule.</span><span class="sxs-lookup"><span data-stu-id="b83b5-120">The <xref:System.Collections.ArrayList> and <xref:System.Collections.Specialized.StringCollection> classes and the <xref:System.Collections.Generic.List%601> generic class offer access to their elements by the zero-based index of the element.</span></span>  
  
    -   <span data-ttu-id="b83b5-121"><xref:System.Collections.Hashtable>, <xref:System.Collections.SortedList>, <xref:System.Collections.Specialized.ListDictionary>, A <xref:System.Collections.Specialized.StringDictionary> třídy a <xref:System.Collections.Generic.Dictionary%602> a <xref:System.Collections.Generic.SortedDictionary%602> obecné třídy nabízí přístup k jejich elementům pomocí klíče elementu.</span><span class="sxs-lookup"><span data-stu-id="b83b5-121">The <xref:System.Collections.Hashtable>, <xref:System.Collections.SortedList>, <xref:System.Collections.Specialized.ListDictionary>, and <xref:System.Collections.Specialized.StringDictionary> classes, and the <xref:System.Collections.Generic.Dictionary%602> and <xref:System.Collections.Generic.SortedDictionary%602> generic classes offer access to their elements by the key of the element.</span></span>  
  
    -   <span data-ttu-id="b83b5-122"><xref:System.Collections.Specialized.NameObjectCollectionBase> a <xref:System.Collections.Specialized.NameValueCollection> třídy a <xref:System.Collections.ObjectModel.KeyedCollection%602> a <xref:System.Collections.Generic.SortedList%602> obecné třídy nabízí přístup k jejich elementů buď index založený na nule nebo klíč elementu.</span><span class="sxs-lookup"><span data-stu-id="b83b5-122">The <xref:System.Collections.Specialized.NameObjectCollectionBase> and <xref:System.Collections.Specialized.NameValueCollection> classes, and the <xref:System.Collections.ObjectModel.KeyedCollection%602> and <xref:System.Collections.Generic.SortedList%602> generic classes offer access to their elements by either the zero-based index or the key of the element.</span></span>  
  
-   <span data-ttu-id="b83b5-123">Každý prvek bude obsahovat jednu hodnotu, kombinace jeden klíč a jednu hodnotu, nebo kombinací jeden klíč a více hodnot?</span><span class="sxs-lookup"><span data-stu-id="b83b5-123">Will each element contain one value, a combination of one key and one value, or a combination of one key and multiple values?</span></span>  
  
    -   <span data-ttu-id="b83b5-124">Jednu hodnotu: použijte některou z kolekce, na základě <xref:System.Collections.IList> rozhraní nebo <xref:System.Collections.Generic.IList%601> obecné rozhraní.</span><span class="sxs-lookup"><span data-stu-id="b83b5-124">One value: Use any of the collections based on the <xref:System.Collections.IList> interface or the <xref:System.Collections.Generic.IList%601> generic interface.</span></span>  
  
    -   <span data-ttu-id="b83b5-125">Jeden klíč a jednu hodnotu: použijte některou z kolekce, na základě <xref:System.Collections.IDictionary> rozhraní nebo <xref:System.Collections.Generic.IDictionary%602> obecné rozhraní.</span><span class="sxs-lookup"><span data-stu-id="b83b5-125">One key and one value: Use any of the collections based on the <xref:System.Collections.IDictionary> interface or the <xref:System.Collections.Generic.IDictionary%602> generic interface.</span></span>  
  
    -   <span data-ttu-id="b83b5-126">Jednu hodnotu s vloženým klíčem: použití <xref:System.Collections.ObjectModel.KeyedCollection%602> obecná třída.</span><span class="sxs-lookup"><span data-stu-id="b83b5-126">One value with embedded key: Use the <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class.</span></span>  
  
    -   <span data-ttu-id="b83b5-127">Jeden klíč a více hodnot: použití <xref:System.Collections.Specialized.NameValueCollection> třídy.</span><span class="sxs-lookup"><span data-stu-id="b83b5-127">One key and multiple values: Use the <xref:System.Collections.Specialized.NameValueCollection> class.</span></span>  
  
-   <span data-ttu-id="b83b5-128">Je třeba seřadit prvky jinak, než jak byly zadány?</span><span class="sxs-lookup"><span data-stu-id="b83b5-128">Do you need to sort the elements differently from how they were entered?</span></span>  
  
    -   <span data-ttu-id="b83b5-129"><xref:System.Collections.Hashtable> Třída seřadí její prvky podle jejich hash.</span><span class="sxs-lookup"><span data-stu-id="b83b5-129">The <xref:System.Collections.Hashtable> class sorts its elements by their hash codes.</span></span>  
  
    -   <span data-ttu-id="b83b5-130"><xref:System.Collections.SortedList> Třídy a <xref:System.Collections.Generic.SortedDictionary%602> a <xref:System.Collections.Generic.SortedList%602> obecné třídy řadit jejich elementy pomocí klíče, na základě implementace <xref:System.Collections.IComparer> rozhraní a <xref:System.Collections.Generic.IComparer%601> obecné rozhraní.</span><span class="sxs-lookup"><span data-stu-id="b83b5-130">The <xref:System.Collections.SortedList> class and the <xref:System.Collections.Generic.SortedDictionary%602> and <xref:System.Collections.Generic.SortedList%602> generic classes sort their elements by the key, based on implementations of the <xref:System.Collections.IComparer> interface and the <xref:System.Collections.Generic.IComparer%601> generic interface.</span></span>  
  
    -   <span data-ttu-id="b83b5-131"><xref:System.Collections.ArrayList>poskytuje <xref:System.Collections.ArrayList.Sort%2A> metody, která použije <xref:System.Collections.IComparer> implementace jako parametr.</span><span class="sxs-lookup"><span data-stu-id="b83b5-131"><xref:System.Collections.ArrayList> provides a <xref:System.Collections.ArrayList.Sort%2A> method that takes an <xref:System.Collections.IComparer> implementation as a parameter.</span></span> <span data-ttu-id="b83b5-132">Jeho obecný protějšek <xref:System.Collections.Generic.List%601> obecná třída poskytuje <xref:System.Collections.Generic.List%601.Sort%2A> metoda, která přebírá implementaci <xref:System.Collections.Generic.IComparer%601> obecné rozhraní jako parametr.</span><span class="sxs-lookup"><span data-stu-id="b83b5-132">Its generic counterpart, the <xref:System.Collections.Generic.List%601> generic class, provides a <xref:System.Collections.Generic.List%601.Sort%2A> method that takes an implementation of the <xref:System.Collections.Generic.IComparer%601> generic interface as a parameter.</span></span>  
  
-   <span data-ttu-id="b83b5-133">Potřebujete rychle vyhledávat a načítat informace?</span><span class="sxs-lookup"><span data-stu-id="b83b5-133">Do you need fast searches and retrieval of information?</span></span>  
  
    -   <span data-ttu-id="b83b5-134"><xref:System.Collections.Specialized.ListDictionary>je rychlejší než <xref:System.Collections.Hashtable> pro kolekce malé (10 položek nebo méně).</span><span class="sxs-lookup"><span data-stu-id="b83b5-134"><xref:System.Collections.Specialized.ListDictionary> is faster than <xref:System.Collections.Hashtable> for small collections (10 items or fewer).</span></span> <span data-ttu-id="b83b5-135"><xref:System.Collections.Generic.Dictionary%602> Obecná třída poskytuje rychlejší vyhledávání, než <xref:System.Collections.Generic.SortedDictionary%602> obecná třída.</span><span class="sxs-lookup"><span data-stu-id="b83b5-135">The <xref:System.Collections.Generic.Dictionary%602> generic class provides faster lookup than the <xref:System.Collections.Generic.SortedDictionary%602> generic class.</span></span> <span data-ttu-id="b83b5-136">Vícevláknová implementace je <xref:System.Collections.Concurrent.ConcurrentDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="b83b5-136">The multi-threaded implementation is <xref:System.Collections.Concurrent.ConcurrentDictionary%602>.</span></span> <span data-ttu-id="b83b5-137"><xref:System.Collections.Concurrent.ConcurrentBag%601>poskytuje rychlé vícevláknové vkládání pro neuspořádaný data.</span><span class="sxs-lookup"><span data-stu-id="b83b5-137"><xref:System.Collections.Concurrent.ConcurrentBag%601> provides fast multi-threaded insertion for unordered data.</span></span> <span data-ttu-id="b83b5-138">Další informace o obou vícevláknových typech najdete v tématu [kdy použít kolekci s bezpečnými vlákny](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).</span><span class="sxs-lookup"><span data-stu-id="b83b5-138">For more information about both multi-threaded types, see [When to Use a Thread-Safe Collection](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).</span></span>  
  
-   <span data-ttu-id="b83b5-139">Potřebujete kolekce, které přijímají pouze řetězce?</span><span class="sxs-lookup"><span data-stu-id="b83b5-139">Do you need collections that accept only strings?</span></span>  
  
    -   <span data-ttu-id="b83b5-140"><xref:System.Collections.Specialized.StringCollection>(na základě <xref:System.Collections.IList>) a <xref:System.Collections.Specialized.StringDictionary> (na základě <xref:System.Collections.IDictionary>) jsou v <xref:System.Collections.Specialized> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="b83b5-140"><xref:System.Collections.Specialized.StringCollection> (based on <xref:System.Collections.IList>) and <xref:System.Collections.Specialized.StringDictionary> (based on <xref:System.Collections.IDictionary>) are in the <xref:System.Collections.Specialized> namespace.</span></span>  
  
    -   <span data-ttu-id="b83b5-141">Kromě toho můžete použít jakékoli třídy obecnou kolekci v <xref:System.Collections.Generic> oboru názvů jako silného typu řetězec kolekce tak, že zadáte <xref:System.String> třídy pro jejich argumenty obecného typu.</span><span class="sxs-lookup"><span data-stu-id="b83b5-141">In addition, you can use any of the generic collection classes in the <xref:System.Collections.Generic> namespace as strongly typed string collections by specifying the <xref:System.String> class for their generic type arguments.</span></span>  
  
## <a name="linq-to-objects-and-plinq"></a><span data-ttu-id="b83b5-142">LINQ na objekty a PLINQ</span><span class="sxs-lookup"><span data-stu-id="b83b5-142">LINQ to Objects and PLINQ</span></span>  
 <span data-ttu-id="b83b5-143">LINQ na objekty umožňuje vývojářům používat dotazy LINQ pro přístup k objektům v paměti, dokud typ objektu implementuje <xref:System.Collections.IEnumerable> nebo <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="b83b5-143">LINQ to Objects enables developers to use LINQ queries to access in-memory objects as long as the object type implements <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="b83b5-144">Dotazy LINQ poskytují společný vzorek pro přístup k datům, jsou obvykle více stručná a čitelná než standardní `foreach` v cyklu a poskytují filtrování, řazení a seskupování schopností.</span><span class="sxs-lookup"><span data-stu-id="b83b5-144">LINQ queries provide a common pattern for accessing data, are typically more concise and readable than standard `foreach` loops, and provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="b83b5-145">Další informace najdete v tématu [LINQ na objekty](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9).</span><span class="sxs-lookup"><span data-stu-id="b83b5-145">For more information, see [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9).</span></span>  
  
 <span data-ttu-id="b83b5-146">PLINQ poskytuje paralelní provádění LINQ na objekty, které nabízejí rychlejší spuštění dotazu v mnoha scénářích efektivněji využívat počítačů s více jádry.</span><span class="sxs-lookup"><span data-stu-id="b83b5-146">PLINQ provides a parallel implementation of LINQ to Objects that can offer faster query execution in many scenarios, through more efficient use of multi-core computers.</span></span> <span data-ttu-id="b83b5-147">Další informace najdete v tématu [paralelní LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="b83b5-147">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b83b5-148">Viz také</span><span class="sxs-lookup"><span data-stu-id="b83b5-148">See Also</span></span>  
 <xref:System.Collections>  
 <xref:System.Collections.Specialized>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="b83b5-149">Kolekce bezpečné pro přístup z více vláken</span><span class="sxs-lookup"><span data-stu-id="b83b5-149">Thread-Safe Collections</span></span>](../../../docs/standard/collections/thread-safe/index.md)