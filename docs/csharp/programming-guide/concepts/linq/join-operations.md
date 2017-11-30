---
title: "Připojení k operace (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 158d035985dae0d1c1daf0f276a9df7b913f2263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="join-operations-c"></a><span data-ttu-id="ff56b-102">Připojení k operace (C#)</span><span class="sxs-lookup"><span data-stu-id="ff56b-102">Join Operations (C#)</span></span>
<span data-ttu-id="ff56b-103">A *spojení* dvou zdrojů dat je přidružení objektů v jeden zdroj dat s objekty, které sdílejí společný atribut v jiného zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="ff56b-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="ff56b-104">Připojení je důležité operace v dotazech, které cílí zdroje dat, jejichž vzájemné vztahy nelze přejít přímo.</span><span class="sxs-lookup"><span data-stu-id="ff56b-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="ff56b-105">V objektově orientované programování to může znamenat korelace mezi objekty, které není modelován, jako zpětně směr jednosměrný vztah.</span><span class="sxs-lookup"><span data-stu-id="ff56b-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="ff56b-106">Je například jednosměrný vztah zákazníků třídy, která má vlastnost typu města, ale třída města nemá vlastnost, která je kolekce objektů zákazníka.</span><span class="sxs-lookup"><span data-stu-id="ff56b-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="ff56b-107">Pokud máte seznam objektů města a chcete najít všechny zákazníky v každé město, můžete je najít použít operace spojení.</span><span class="sxs-lookup"><span data-stu-id="ff56b-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="ff56b-108">Připojení k metody uvedené v rámci LINQ <xref:System.Linq.Enumerable.Join%2A> a <xref:System.Linq.Enumerable.GroupJoin%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff56b-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="ff56b-109">Tyto metody provedení equijoins nebo spojení, které odpovídají dvou zdrojů dat podle rovnosti jejich klíče.</span><span class="sxs-lookup"><span data-stu-id="ff56b-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="ff56b-110">(Pro porovnání, Transact-SQL podporuje připojení operátory než "je rovno", například "je menší než" operátor.) V podmínkách relační databáze <xref:System.Linq.Enumerable.Join%2A> implementuje vnitřní spojení, typ spojení ve které se vrátí pouze ty objekty, které mají odpovídající v datové sadě.</span><span class="sxs-lookup"><span data-stu-id="ff56b-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="ff56b-111"><xref:System.Linq.Enumerable.GroupJoin%2A> Metoda má ekvivalent v podmínkách relační databázi, ale implementuje nadmnožinou vnitřní spojení a levé vnější spojení.</span><span class="sxs-lookup"><span data-stu-id="ff56b-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="ff56b-112">Levé vnější spojení je spojení, která vrací každý prvek první zdroje dat (levém), i když nemá žádné korelační elementy v datovém zdroji.</span><span class="sxs-lookup"><span data-stu-id="ff56b-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="ff56b-113">Následující obrázek znázorňuje koncepční zobrazení dvě sady a elementů v rámci těchto sad, které jsou součástí vnitřní spojení a levé vnější spojení.</span><span class="sxs-lookup"><span data-stu-id="ff56b-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 <span data-ttu-id="ff56b-114">![Dvě překrývající se kruhy zobrazující vnitřní &#47; vnější. ] (../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span><span class="sxs-lookup"><span data-stu-id="ff56b-114">![Two overlapping circles showing inner&#47;outer.](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff56b-115">Metody</span><span class="sxs-lookup"><span data-stu-id="ff56b-115">Methods</span></span>  
  
|<span data-ttu-id="ff56b-116">Název metody</span><span class="sxs-lookup"><span data-stu-id="ff56b-116">Method Name</span></span>|<span data-ttu-id="ff56b-117">Popis</span><span class="sxs-lookup"><span data-stu-id="ff56b-117">Description</span></span>|<span data-ttu-id="ff56b-118">Syntaxe výrazu dotazu jazyka C#</span><span class="sxs-lookup"><span data-stu-id="ff56b-118">C# Query Expression Syntax</span></span>|<span data-ttu-id="ff56b-119">Další informace</span><span class="sxs-lookup"><span data-stu-id="ff56b-119">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ff56b-120">Join</span><span class="sxs-lookup"><span data-stu-id="ff56b-120">Join</span></span>|<span data-ttu-id="ff56b-121">Spojí dva pořadí podle funkce selektoru klíče a extrahuje dvojice hodnot.</span><span class="sxs-lookup"><span data-stu-id="ff56b-121">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ff56b-122">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="ff56b-122">GroupJoin</span></span>|<span data-ttu-id="ff56b-123">Spojí dva pořadí na základě funkce selektoru klíče a skupin výsledné shody pro jednotlivé elementy.</span><span class="sxs-lookup"><span data-stu-id="ff56b-123">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="ff56b-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="ff56b-124">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="ff56b-125">Přehled standardních operátorů dotazu (C#)</span><span class="sxs-lookup"><span data-stu-id="ff56b-125">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="ff56b-126">Anonymní typy</span><span class="sxs-lookup"><span data-stu-id="ff56b-126">Anonymous Types</span></span>](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="ff56b-127">Formulovali spojení a dotazy smíšený produkt</span><span class="sxs-lookup"><span data-stu-id="ff56b-127">Formulate Joins and Cross-Product Queries</span></span>](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b)  
 [<span data-ttu-id="ff56b-128">JOIN – klauzule</span><span class="sxs-lookup"><span data-stu-id="ff56b-128">join clause</span></span>](../../../../csharp/language-reference/keywords/join-clause.md)  
 [<span data-ttu-id="ff56b-129">Postupy: spojení pomocí složených klíčů</span><span class="sxs-lookup"><span data-stu-id="ff56b-129">How to: Join by Using Composite Keys</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)  
 [<span data-ttu-id="ff56b-130">Postupy: spojení obsahu z Nepodobných souborů (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ff56b-130">How to: Join Content from Dissimilar Files (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)  
 [<span data-ttu-id="ff56b-131">Postupy: řazení výsledků Klauzule Join</span><span class="sxs-lookup"><span data-stu-id="ff56b-131">How to: Order the Results of a Join Clause</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)  
 [<span data-ttu-id="ff56b-132">Postupy: provádění vlastních operací spojování</span><span class="sxs-lookup"><span data-stu-id="ff56b-132">How to: Perform Custom Join Operations</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)  
 [<span data-ttu-id="ff56b-133">Postupy: provádění seskupených spojení</span><span class="sxs-lookup"><span data-stu-id="ff56b-133">How to: Perform Grouped Joins</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)  
 [<span data-ttu-id="ff56b-134">Postupy: provádění vnitřních spojení</span><span class="sxs-lookup"><span data-stu-id="ff56b-134">How to: Perform Inner Joins</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)  
 [<span data-ttu-id="ff56b-135">Postup: provedení levých vnějších spojení</span><span class="sxs-lookup"><span data-stu-id="ff56b-135">How to: Perform Left Outer Joins</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)  
 [<span data-ttu-id="ff56b-136">Postupy: vyplňování kolekcí objektů z více zdrojů (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ff56b-136">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)