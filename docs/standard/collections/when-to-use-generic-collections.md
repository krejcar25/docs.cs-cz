---
title: "Kdy použít generické kolekce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- collections [.NET Framework], generic
- generic collections [.NET Framework]
ms.assetid: e7b868b1-11fe-4ac5-bed3-de68aca47739
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6e6f23c413bbefe6a29746e2f6a1887a23dd3bfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-generic-collections"></a><span data-ttu-id="dc7d9-102">Kdy použít generické kolekce</span><span class="sxs-lookup"><span data-stu-id="dc7d9-102">When to Use Generic Collections</span></span>
<span data-ttu-id="dc7d9-103">Pomocí obecné kolekce je obecně nedoporučuje, protože získáte okamžitý výhodou bezpečnost typů bez nutnosti odvozovat od typu základní kolekce a implementace konkrétní typ členů.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-103">Using generic collections is generally recommended, because you gain the immediate benefit of type safety without having to derive from a base collection type and implement type-specific members.</span></span> <span data-ttu-id="dc7d9-104">Obecné typy kolekcí také obecně poskytují lepší výkon než odpovídající typy neobecné kolekcí (a lépe než typy, které jsou odvozeny od neobecné základní kolekci typů) při elementy z kolekce jsou typy hodnot, protože s obecnými typy není potřeba pole elementy.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-104">Generic collection types also generally perform better than the corresponding nongeneric collection types (and better than types that are derived from nongeneric base collection types) when the collection elements are value types, because with generics there is no need to box the elements.</span></span>  
  
 <span data-ttu-id="dc7d9-105">Pro programy, které se zaměřují [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] nebo novější, byste měli použít obecné třídy kolekcí v <xref:System.Collections.Concurrent> obor názvů, když je více vláken může přidávat nebo odebírat současně položky z kolekce.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-105">For programs that target the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later, you should use the generic collection classes in the <xref:System.Collections.Concurrent> namespace when multiple threads might be adding or removing items from the collection concurrently.</span></span>  
  
 <span data-ttu-id="dc7d9-106">Následující obecné typy odpovídají existujícím typům kolekcí:</span><span class="sxs-lookup"><span data-stu-id="dc7d9-106">The following generic types correspond to existing collection types:</span></span>  
  
-   <span data-ttu-id="dc7d9-107"><xref:System.Collections.Generic.List%601>je obecná třída, která odpovídá <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-107"><xref:System.Collections.Generic.List%601> is the generic class that corresponds to <xref:System.Collections.ArrayList>.</span></span>  
  
-   <span data-ttu-id="dc7d9-108"><xref:System.Collections.Generic.Dictionary%602>a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> jsou obecné třídy, které odpovídají <xref:System.Collections.Hashtable>.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-108"><xref:System.Collections.Generic.Dictionary%602> and <xref:System.Collections.Concurrent.ConcurrentDictionary%602> are the generic classes that correspond to <xref:System.Collections.Hashtable>.</span></span>  
  
-   <span data-ttu-id="dc7d9-109"><xref:System.Collections.ObjectModel.Collection%601>je obecná třída, která odpovídá <xref:System.Collections.CollectionBase>.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-109"><xref:System.Collections.ObjectModel.Collection%601> is the generic class that corresponds to <xref:System.Collections.CollectionBase>.</span></span> <span data-ttu-id="dc7d9-110"><xref:System.Collections.ObjectModel.Collection%601>lze použít jako základní třídy, ale na rozdíl od <xref:System.Collections.CollectionBase>, není abstraktní.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-110"><xref:System.Collections.ObjectModel.Collection%601> can be used as a base class, but unlike <xref:System.Collections.CollectionBase>, it is not abstract.</span></span> <span data-ttu-id="dc7d9-111">Díky tomu je jednodušší použít.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-111">This makes it much easier to use.</span></span>  
  
-   <span data-ttu-id="dc7d9-112"><xref:System.Collections.ObjectModel.ReadOnlyCollection%601>je obecná třída, která odpovídá <xref:System.Collections.ReadOnlyCollectionBase>.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-112"><xref:System.Collections.ObjectModel.ReadOnlyCollection%601> is the generic class that corresponds to <xref:System.Collections.ReadOnlyCollectionBase>.</span></span> <span data-ttu-id="dc7d9-113"><xref:System.Collections.ObjectModel.ReadOnlyCollection%601>není abstraktní a má konstruktor, který usnadňuje vystavení existující <xref:System.Collections.Generic.List%601> jako kolekce jen pro čtení.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-113"><xref:System.Collections.ObjectModel.ReadOnlyCollection%601> is not abstract, and has a constructor that makes it easy to expose an existing <xref:System.Collections.Generic.List%601> as a read-only collection.</span></span>  
  
-   <span data-ttu-id="dc7d9-114"><xref:System.Collections.Generic.Queue%601>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Generic.Stack%601>, <xref:System.Collections.Concurrent.ConcurrentStack%601>, A <xref:System.Collections.Generic.SortedList%602> obecné třídy odpovídají příslušné neobecné třídy se stejnými názvy.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-114">The <xref:System.Collections.Generic.Queue%601>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Generic.Stack%601>, <xref:System.Collections.Concurrent.ConcurrentStack%601>, and <xref:System.Collections.Generic.SortedList%602> generic classes correspond to the respective nongeneric classes with the same names.</span></span>  
  
## <a name="additional-types"></a><span data-ttu-id="dc7d9-115">Další typy</span><span class="sxs-lookup"><span data-stu-id="dc7d9-115">Additional Types</span></span>  
 <span data-ttu-id="dc7d9-116">Několik typů obecnou kolekci ještě nemá neobecné protějšky.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-116">Several generic collection types do not have nongeneric counterparts.</span></span> <span data-ttu-id="dc7d9-117">Zahrnují následující:</span><span class="sxs-lookup"><span data-stu-id="dc7d9-117">They include the following:</span></span>  
  
-   <span data-ttu-id="dc7d9-118"><xref:System.Collections.Generic.LinkedList%601>je pro obecné účely odkazovaného seznamu, který poskytuje vložení a odebrání o(1).</span><span class="sxs-lookup"><span data-stu-id="dc7d9-118"><xref:System.Collections.Generic.LinkedList%601> is a general-purpose linked list that provides O(1) insertion and removal operations.</span></span>  
  
-   <span data-ttu-id="dc7d9-119"><xref:System.Collections.Generic.SortedDictionary%602>je seřazený slovník s O (protokolu `n`) vložení a načtení operací, které je výhodná možnost pro <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-119"><xref:System.Collections.Generic.SortedDictionary%602> is a sorted dictionary with O(log `n`) insertion and retrieval operations, which makes it a useful alternative to <xref:System.Collections.Generic.SortedList%602>.</span></span>  
  
-   <span data-ttu-id="dc7d9-120"><xref:System.Collections.ObjectModel.KeyedCollection%602>je hybridní mezi seznam a slovník, který poskytuje způsob, jak ukládat objekty, které obsahují vlastní klíče.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-120"><xref:System.Collections.ObjectModel.KeyedCollection%602> is a hybrid between a list and a dictionary, which provides a way to store objects that contain their own keys.</span></span>  
  
-   <span data-ttu-id="dc7d9-121"><xref:System.Collections.Concurrent.BlockingCollection%601>implementuje třídu kolekce s funkcí ohraničování a blokování.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-121"><xref:System.Collections.Concurrent.BlockingCollection%601> implements a collection class with bounding and blocking functionality.</span></span>  
  
-   <span data-ttu-id="dc7d9-122"><xref:System.Collections.Concurrent.ConcurrentBag%601>poskytuje rychlé vložení a odebrání neuspořádaný elementů.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-122"><xref:System.Collections.Concurrent.ConcurrentBag%601> provides fast insertion and removal of unordered elements.</span></span>  
  
## <a name="linq-to-objects"></a><span data-ttu-id="dc7d9-123">LINQ na objekty</span><span class="sxs-lookup"><span data-stu-id="dc7d9-123">LINQ to Objects</span></span>  
 <span data-ttu-id="dc7d9-124">LINQ na objekty funkce umožňuje používat dotazy LINQ pro přístup k objektům v paměti, dokud implementuje typ objektu <xref:System.Collections.IEnumerable?displayProperty=nameWithType> nebo <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-124">The LINQ to Objects feature enables you to use LINQ queries to access in-memory objects as long as the object type implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="dc7d9-125">Dotazy LINQ poskytují společný vzorek pro přístup k datům; Obvykle se jedná o více stručná a čitelná než standardní `foreach` cyklu; a zadejte filtrování, řazení a seskupování schopností.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-125">LINQ queries provide a common pattern for accessing data; are typically more concise and readable than standard `foreach` loops; and provide filtering, ordering and grouping capabilities.</span></span> <span data-ttu-id="dc7d9-126">Výkon lze zvýšit rovněž dotazů LINQ.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-126">LINQ queries can also improve performance.</span></span> <span data-ttu-id="dc7d9-127">Další informace najdete v tématu [LINQ na objekty](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9) a [paralelní LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="dc7d9-127">For more information, see [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9) and [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="additional-functionality"></a><span data-ttu-id="dc7d9-128">Další funkce</span><span class="sxs-lookup"><span data-stu-id="dc7d9-128">Additional Functionality</span></span>  
 <span data-ttu-id="dc7d9-129">Některé obecné typy mají funkce, které se nenachází ve typy neobecné kolekcí.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-129">Some of the generic types have functionality that is not found in the nongeneric collection types.</span></span> <span data-ttu-id="dc7d9-130">Například <xref:System.Collections.Generic.List%601> třídy, která odpovídá neobecné <xref:System.Collections.ArrayList> třídu, má několik metod, které přijímají obecní delegáti, jako <xref:System.Predicate%601> delegáta, který vám umožní určit metody pro hledání v seznamu, <xref:System.Action%601>delegáta, který představuje metody, které působí na každý prvek v seznamu a <xref:System.Converter%602> delegáta, který umožňuje definovat převody mezi typy.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-130">For example, the <xref:System.Collections.Generic.List%601> class, which corresponds to the nongeneric <xref:System.Collections.ArrayList> class, has a number of methods that accept generic delegates, such as the <xref:System.Predicate%601> delegate that allows you to specify methods for searching the list, the <xref:System.Action%601> delegate that represents methods that act on each element of the list, and the <xref:System.Converter%602> delegate that lets you define conversions between types.</span></span>  
  
 <span data-ttu-id="dc7d9-131"><xref:System.Collections.Generic.List%601> Třída umožňuje zadat vlastní <xref:System.Collections.Generic.IComparer%601> implementace obecné rozhraní pro řazení a hledání v seznamu.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-131">The <xref:System.Collections.Generic.List%601> class allows you to specify your own <xref:System.Collections.Generic.IComparer%601> generic interface implementations for sorting and searching the list.</span></span> <span data-ttu-id="dc7d9-132"><xref:System.Collections.Generic.SortedDictionary%602> a <xref:System.Collections.Generic.SortedList%602> třídy také mají tuto možnost.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-132">The <xref:System.Collections.Generic.SortedDictionary%602> and <xref:System.Collections.Generic.SortedList%602> classes also have this capability.</span></span> <span data-ttu-id="dc7d9-133">Kromě toho tyto třídy umožňují určit komparátory při vytvoření kolekce.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-133">In addition, these classes let you specify comparers when the collection is created.</span></span> <span data-ttu-id="dc7d9-134">Podobně <xref:System.Collections.Generic.Dictionary%602> a <xref:System.Collections.ObjectModel.KeyedCollection%602> třídy umožňují určit vlastní komparátory rovnosti.</span><span class="sxs-lookup"><span data-stu-id="dc7d9-134">In similar fashion, the <xref:System.Collections.Generic.Dictionary%602> and <xref:System.Collections.ObjectModel.KeyedCollection%602> classes let you specify your own equality comparers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc7d9-135">Viz také</span><span class="sxs-lookup"><span data-stu-id="dc7d9-135">See Also</span></span>  
 [<span data-ttu-id="dc7d9-136">Kolekce a datové struktury</span><span class="sxs-lookup"><span data-stu-id="dc7d9-136">Collections and Data Structures</span></span>](../../../docs/standard/collections/index.md)  
 [<span data-ttu-id="dc7d9-137">Běžně používané typy kolekcí</span><span class="sxs-lookup"><span data-stu-id="dc7d9-137">Commonly Used Collection Types</span></span>](../../../docs/standard/collections/commonly-used-collection-types.md)  
 [<span data-ttu-id="dc7d9-138">Obecné typy</span><span class="sxs-lookup"><span data-stu-id="dc7d9-138">Generics</span></span>](../../../docs/standard/generics/index.md)