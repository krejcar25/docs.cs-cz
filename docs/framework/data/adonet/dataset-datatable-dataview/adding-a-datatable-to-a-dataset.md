---
title: "Přidání DataTable do datové sady"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f70292794866530de5b7abf7dac1edd09d300c94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="56f57-102">Přidání DataTable do datové sady</span><span class="sxs-lookup"><span data-stu-id="56f57-102">Adding a DataTable to a DataSet</span></span>
<span data-ttu-id="56f57-103">ADO.NET umožňuje vytvářet <xref:System.Data.DataTable> objekty a přidat je do existujícího <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="56f57-103">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="56f57-104">Můžete nastavit omezení informace <xref:System.Data.DataTable> pomocí <xref:System.Data.DataTable.PrimaryKey%2A> a <xref:System.Data.DataColumn.Unique%2A> vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="56f57-104">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56f57-105">Příklad</span><span class="sxs-lookup"><span data-stu-id="56f57-105">Example</span></span>  
 <span data-ttu-id="56f57-106">Následující příklad vytvoří <xref:System.Data.DataSet>, přidá nový <xref:System.Data.DataTable> do objektu <xref:System.Data.DataSet>a potom přidá tři <xref:System.Data.DataColumn> objekty, které se v tabulce.</span><span class="sxs-lookup"><span data-stu-id="56f57-106">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="56f57-107">Nakonec kód nastaví jeden sloupec jako sloupec primárního klíče.</span><span class="sxs-lookup"><span data-stu-id="56f57-107">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="56f57-108">Rozlišování velkých a malých písmen</span><span class="sxs-lookup"><span data-stu-id="56f57-108">Case Sensitivity</span></span>  
 <span data-ttu-id="56f57-109">Dvě nebo více tabulek nebo vztahy se stejným názvem, ale jiné velká a malá písmena, může existovat v <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="56f57-109">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="56f57-110">V takových případech odkazy podle názvu tabulky a relace je malá a velká písmena.</span><span class="sxs-lookup"><span data-stu-id="56f57-110">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="56f57-111">Například pokud <xref:System.Data.DataSet> **datovou sadu** obsahuje tabulky **tabulky1** a **tabulky1**, by odkazujete **tabulky1** podle názvu jako **dataSet.Tables["Table1"]**, a **tabulky1** jako **dataSet.Tables["table1"]**.</span><span class="sxs-lookup"><span data-stu-id="56f57-111">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="56f57-112">Pokus o jednu z tabulek jako odkaz na **dataSet.Tables["TABLE1"]** by generovat výjimku.</span><span class="sxs-lookup"><span data-stu-id="56f57-112">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="56f57-113">Chování rozlišování neplatí, pokud pouze jednu tabulku nebo relaci má určitý název.</span><span class="sxs-lookup"><span data-stu-id="56f57-113">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="56f57-114">Například pokud <xref:System.Data.DataSet> je k dispozici pouze **tabulky1**, můžete odkazovat pomocí **dataSet.Tables["TABLE1"]**.</span><span class="sxs-lookup"><span data-stu-id="56f57-114">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56f57-115"><xref:System.Data.DataSet.CaseSensitive%2A> Vlastnost <xref:System.Data.DataSet> nemá vliv na toto chování.</span><span class="sxs-lookup"><span data-stu-id="56f57-115">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="56f57-116"><xref:System.Data.DataSet.CaseSensitive%2A> Vlastnost se vztahuje na data v <xref:System.Data.DataSet> a ovlivňuje řazení, hledání, filtrování, vynucení omezení a tak dále.</span><span class="sxs-lookup"><span data-stu-id="56f57-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="56f57-117">Podpora Namespace</span><span class="sxs-lookup"><span data-stu-id="56f57-117">Namespace Support</span></span>  
 <span data-ttu-id="56f57-118">Ve verzích ADO.NET starších než 2.0 dvě tabulky nelze mít stejný název, i v případě, že byly v různých oborech názvů.</span><span class="sxs-lookup"><span data-stu-id="56f57-118">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="56f57-119">Toto omezení byla odebrána v ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="56f57-119">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="56f57-120">A <xref:System.Data.DataSet> může obsahovat dvě tabulky, které mají stejnou <xref:System.Data.DataTable.TableName%2A> hodnotu vlastnosti, ale jiné <xref:System.Data.DataTable.Namespace%2A> hodnot vlastností.</span><span class="sxs-lookup"><span data-stu-id="56f57-120">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f57-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="56f57-121">See Also</span></span>  
 [<span data-ttu-id="56f57-122">Datové sady, DataTables a DataView</span><span class="sxs-lookup"><span data-stu-id="56f57-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="56f57-123">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="56f57-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)