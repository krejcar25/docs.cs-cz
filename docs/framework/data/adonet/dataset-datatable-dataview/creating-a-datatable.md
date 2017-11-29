---
title: "Vytváření DataTable"
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
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 923d19e9539c6d93f3714efcdaa6fe7a5da843ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-datatable"></a><span data-ttu-id="6d0e1-102">Vytváření DataTable</span><span class="sxs-lookup"><span data-stu-id="6d0e1-102">Creating a DataTable</span></span>
<span data-ttu-id="6d0e1-103">A <xref:System.Data.DataTable>, která představuje jednu tabulku v paměti relačních dat, lze vytvořit a používat samostatně nebo je můžete použít jiné objekty rozhraní .NET Framework nejčastěji jako člen skupiny <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="6d0e1-104">Můžete vytvořit **DataTable** objekt pomocí odpovídající **DataTable** konstruktor.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="6d0e1-105">Můžete přidat jej do **datovou sadu** pomocí **přidat** metodu ho přidat do **DataTable** objektu **tabulky** kolekce.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="6d0e1-106">Můžete také vytvořit **DataTable** objekty v rámci **datovou sadu** pomocí **vyplnění** nebo **FillSchema** metody  **DataAdapter** objekt, nebo z předdefinovaných nebo vyvozen XML schématu pomocí **ReadXml**, **ReadXmlSchema**, nebo **InferXmlSchema** metody **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="6d0e1-107">Všimněte si, že po přidání **DataTable** jako člena **tabulky** kolekce jednoho **datovou sadu**, nelze ji přidat do kolekce tabulek jiných **Datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="6d0e1-108">Při prvním vytvoření **DataTable**, nemá schéma (to znamená, struktura).</span><span class="sxs-lookup"><span data-stu-id="6d0e1-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="6d0e1-109">K definování schématu tabulky, musíte vytvořit a přidat <xref:System.Data.DataColumn> objekty ke **sloupce** kolekce tabulky.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="6d0e1-110">Můžete také definovat sloupec primárního klíče tabulky a vytvořit a přidat **omezení** objekty ke **omezení** kolekce tabulky.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="6d0e1-111">Po definování schématu pro **DataTable**, můžete přidat řádky dat do tabulky přidáním **DataRow** objekty ke **řádky** kolekce tabulky.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="6d0e1-112">Není nutné zadat hodnotu <xref:System.Data.DataTable.TableName%2A> vlastnost při vytváření **DataTable**; můžete zadat vlastnost v jinou dobu, nebo můžete nechat prázdné.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="6d0e1-113">Pokud však přidáte tabulku bez **TableName** hodnotu **datovou sadu**, v tabulce bude mít přírůstkové výchozí název tabulky*N*, od verze "Tabulka" pro Table0.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d0e1-114">Doporučujeme, abyste "tabulky*N*" zásady vytváření názvů, když zadáte **TableName** hodnota, protože název je zadat může dojít ke konfliktu s existujícím názvem výchozí tabulky v **datové sady** .</span><span class="sxs-lookup"><span data-stu-id="6d0e1-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="6d0e1-115">Pokud se zadaným názvem již existuje, je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="6d0e1-116">Následující příklad vytvoří instanci **DataTable** objektu a přiřadí ji název "Zákazníci".</span><span class="sxs-lookup"><span data-stu-id="6d0e1-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="6d0e1-117">Následující příklad vytvoří instanci **DataTable** přidáním jeho **tabulky** kolekce **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="6d0e1-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d0e1-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="6d0e1-118">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [<span data-ttu-id="6d0e1-119">DataTables</span><span class="sxs-lookup"><span data-stu-id="6d0e1-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="6d0e1-120">Naplnění datové sady z modul DataAdapter</span><span class="sxs-lookup"><span data-stu-id="6d0e1-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="6d0e1-121">Načítání datové sady z XML</span><span class="sxs-lookup"><span data-stu-id="6d0e1-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="6d0e1-122">Načítání informací o schématu sady dat z XML</span><span class="sxs-lookup"><span data-stu-id="6d0e1-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="6d0e1-123">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="6d0e1-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)