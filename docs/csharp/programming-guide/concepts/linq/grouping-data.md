---
title: "Seskupování dat (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4aef8d10eaffb384fe919ffa6a1e742cb837f540
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="grouping-data-c"></a><span data-ttu-id="d72df-102">Seskupování dat (C#)</span><span class="sxs-lookup"><span data-stu-id="d72df-102">Grouping Data (C#)</span></span>
<span data-ttu-id="d72df-103">Seskupení odkazuje na operaci ukládání dat do skupin tak, aby elementy v každé skupině sdílejí společný atribut.</span><span class="sxs-lookup"><span data-stu-id="d72df-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="d72df-104">Následující obrázek znázorňuje výsledky seskupování posloupnost znaků.</span><span class="sxs-lookup"><span data-stu-id="d72df-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="d72df-105">Klíč pro každou skupinu je znak.</span><span class="sxs-lookup"><span data-stu-id="d72df-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="d72df-106">![Operace seskupení LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="d72df-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="d72df-107">V následující části jsou uvedené metody operátor standardní dotazů, které seskupují datové prvky.</span><span class="sxs-lookup"><span data-stu-id="d72df-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d72df-108">Metody</span><span class="sxs-lookup"><span data-stu-id="d72df-108">Methods</span></span>  
  
|<span data-ttu-id="d72df-109">Název metody</span><span class="sxs-lookup"><span data-stu-id="d72df-109">Method Name</span></span>|<span data-ttu-id="d72df-110">Popis</span><span class="sxs-lookup"><span data-stu-id="d72df-110">Description</span></span>|<span data-ttu-id="d72df-111">Syntaxe výrazu dotazu jazyka C#</span><span class="sxs-lookup"><span data-stu-id="d72df-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="d72df-112">Další informace</span><span class="sxs-lookup"><span data-stu-id="d72df-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="d72df-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="d72df-113">GroupBy</span></span>|<span data-ttu-id="d72df-114">Prvky skupiny, které sdílejí společný atribut.</span><span class="sxs-lookup"><span data-stu-id="d72df-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="d72df-115">Každá skupina je reprezentována <xref:System.Linq.IGrouping%602> objektu.</span><span class="sxs-lookup"><span data-stu-id="d72df-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="d72df-116">-nebo-</span><span class="sxs-lookup"><span data-stu-id="d72df-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d72df-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="d72df-117">ToLookup</span></span>|<span data-ttu-id="d72df-118">Vloží elementy do <xref:System.Linq.Lookup%602> (slovník 1 n) podle funkce selektoru klíče.</span><span class="sxs-lookup"><span data-stu-id="d72df-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="d72df-119">Nelze použít.</span><span class="sxs-lookup"><span data-stu-id="d72df-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="d72df-120">Příklad syntaxe výrazu dotazu</span><span class="sxs-lookup"><span data-stu-id="d72df-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="d72df-121">Následující příklad kódu používá `group by` klauzule na celá čísla skupinu v seznamu podle toho, zda jsou popisných.</span><span class="sxs-lookup"><span data-stu-id="d72df-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="d72df-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="d72df-122">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="d72df-123">Přehled standardních operátorů dotazu (C#)</span><span class="sxs-lookup"><span data-stu-id="d72df-123">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="d72df-124">Group – klauzule</span><span class="sxs-lookup"><span data-stu-id="d72df-124">group clause</span></span>](../../../../csharp/language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="d72df-125">Postupy: vytvoření vnořené skupiny</span><span class="sxs-lookup"><span data-stu-id="d72df-125">How to: Create a Nested Group</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)  
 [<span data-ttu-id="d72df-126">Postupy: seskupování souborů podle přípony (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d72df-126">How to: Group Files by Extension (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 [<span data-ttu-id="d72df-127">Postupy: seskupení výsledků dotazu</span><span class="sxs-lookup"><span data-stu-id="d72df-127">How to: Group Query Results</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)  
 [<span data-ttu-id="d72df-128">Postupy: provádění poddotazů na skupinách</span><span class="sxs-lookup"><span data-stu-id="d72df-128">How to: Perform a Subquery on a Grouping Operation</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)  
 [<span data-ttu-id="d72df-129">Postupy: rozdělení souboru na mnoho souborů pomocí skupin (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d72df-129">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)