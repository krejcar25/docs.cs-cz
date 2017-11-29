---
title: "Omezení DataTable"
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
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fb1fd2c7aa057fcc83c82ab9d72129db2cac680e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="datatable-constraints"></a><span data-ttu-id="8d56d-102">Omezení DataTable</span><span class="sxs-lookup"><span data-stu-id="8d56d-102">DataTable Constraints</span></span>
<span data-ttu-id="8d56d-103">Omezení můžete vynutit omezení na datech v <xref:System.Data.DataTable>, aby udržení integrity dat.</span><span class="sxs-lookup"><span data-stu-id="8d56d-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="8d56d-104">Omezení je automatické pravidlo použít na sloupec nebo související sloupce, který určuje postup, když je nějakým způsobem změnit hodnotu v řádku.</span><span class="sxs-lookup"><span data-stu-id="8d56d-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="8d56d-105">Vynutí se omezení při `System.Data.DataSet.EnforceConstraints` vlastnost <xref:System.Data.DataSet> je **true**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="8d56d-106">Příklad kódu, který ukazuje, jak nastavit `EnforceConstraints` vlastnost, najdete v článku <xref:System.Data.DataSet.EnforceConstraints%2A> referenční téma.</span><span class="sxs-lookup"><span data-stu-id="8d56d-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="8d56d-107">Existují dva typy omezení v ADO.NET: <xref:System.Data.ForeignKeyConstraint> a <xref:System.Data.UniqueConstraint>.</span><span class="sxs-lookup"><span data-stu-id="8d56d-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="8d56d-108">Ve výchozím nastavení, obě omezení jsou vytvořeny automaticky při vytvoření vztahu mezi dvěma nebo více tabulek přidáním <xref:System.Data.DataRelation> k **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="8d56d-109">Toto chování však můžete zakázat zadáním **createConstraints** = **false** při vytváření vztah.</span><span class="sxs-lookup"><span data-stu-id="8d56d-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="8d56d-110">Objekt ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="8d56d-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="8d56d-111">A **vlastnosti ForeignKeyConstraint** vynucuje pravidla o tom, jak rozšířit aktualizace a odstranění pro tabulky v relaci.</span><span class="sxs-lookup"><span data-stu-id="8d56d-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="8d56d-112">Pokud hodnotu v řádku jedna tabulka je aktualizovat ani odstranit a stejné hodnoty se také používá v jednom nebo více souvisejících tabulek, například **vlastnosti ForeignKeyConstraint** Určuje, co se stane, že v související tabulky.</span><span class="sxs-lookup"><span data-stu-id="8d56d-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="8d56d-113"><xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> a <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> vlastnosti **vlastnosti ForeignKeyConstraint** definovat akce, které mají být provedeny, když se uživatel pokusí provést odstranění nebo aktualizaci řádku související tabulky.</span><span class="sxs-lookup"><span data-stu-id="8d56d-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="8d56d-114">Následující tabulka popisuje různá nastavení, které jsou k dispozici pro **DeletRule** a **UpdateRule** vlastnosti **vlastnosti ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="8d56d-115">Nastavení pravidla</span><span class="sxs-lookup"><span data-stu-id="8d56d-115">Rule setting</span></span>|<span data-ttu-id="8d56d-116">Popis</span><span class="sxs-lookup"><span data-stu-id="8d56d-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="8d56d-117">**CASCADE**</span><span class="sxs-lookup"><span data-stu-id="8d56d-117">**Cascade**</span></span>|<span data-ttu-id="8d56d-118">Odstranění nebo aktualizaci související řádky.</span><span class="sxs-lookup"><span data-stu-id="8d56d-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="8d56d-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="8d56d-119">**SetNull**</span></span>|<span data-ttu-id="8d56d-120">Nastavení hodnot v související řádky, které **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="8d56d-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="8d56d-121">**SetDefault**</span></span>|<span data-ttu-id="8d56d-122">Nastavte hodnoty v související řádky na výchozí hodnotu.</span><span class="sxs-lookup"><span data-stu-id="8d56d-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="8d56d-123">**None**</span><span class="sxs-lookup"><span data-stu-id="8d56d-123">**None**</span></span>|<span data-ttu-id="8d56d-124">Na související řádky provádět žádnou akci.</span><span class="sxs-lookup"><span data-stu-id="8d56d-124">Take no action on related rows.</span></span> <span data-ttu-id="8d56d-125">Toto nastavení je výchozí.</span><span class="sxs-lookup"><span data-stu-id="8d56d-125">This is the default.</span></span>|  
  
 <span data-ttu-id="8d56d-126">A **vlastnosti ForeignKeyConstraint** můžete omezit, a také rozšířit, změny související sloupce.</span><span class="sxs-lookup"><span data-stu-id="8d56d-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="8d56d-127">V závislosti na vlastnosti nastavit pro **vlastnosti ForeignKeyConstraint** sloupce, pokud **EnforceConstraints** vlastnost **datovou sadu** je **true**, provádění některých operací na řádek nadřazené bude mít za následek výjimku.</span><span class="sxs-lookup"><span data-stu-id="8d56d-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="8d56d-128">Například pokud **DeletRule** vlastnost **vlastnosti ForeignKeyConstraint** je **žádné**, nadřazený řádek nelze odstranit, pokud má všechny podřízené řádky.</span><span class="sxs-lookup"><span data-stu-id="8d56d-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="8d56d-129">Můžete vytvořit omezení cizího klíče mezi jednoho sloupce nebo pole sloupců pomocí **vlastnosti ForeignKeyConstraint** konstruktor.</span><span class="sxs-lookup"><span data-stu-id="8d56d-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="8d56d-130">Předat výsledná **vlastnosti ForeignKeyConstraint** do objektu **přidat** metoda v tabulce **omezení** vlastnost, která je **objektu ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="8d56d-131">Můžete také předat argumenty konstruktoru několik přetížení **přidat** metodu **objektu ConstraintCollection** k vytvoření **vlastnosti ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="8d56d-132">Při vytváření **vlastnosti ForeignKeyConstraint**, můžete předat **DeletRule** a **UpdateRule** hodnoty do konstruktoru jako argumenty, nebo můžete nastavit jako vlastnosti jako Následující příklad (kde **DeletRule** nastavena na hodnotu **žádné**).</span><span class="sxs-lookup"><span data-stu-id="8d56d-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a><span data-ttu-id="8d56d-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="8d56d-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="8d56d-134">Změny na řádky nelze přijmout pomocí **metoda AcceptChanges** metoda nebo zrušené pomocí **RejectChanges** metodu **datovou sadu**, **DataTable**, nebo **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="8d56d-135">Když **datovou sadu** obsahuje **ForeignKeyConstraints**, volajícím **metoda AcceptChanges** nebo **RejectChanges** metody vynucuje  **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="8d56d-136">**AcceptRejectRule** vlastnost **vlastnosti ForeignKeyConstraint** Určuje akci, která bude provedena na podřízených řádků při **metoda AcceptChanges** nebo  **RejectChanges** se volá na řádek nadřazené.</span><span class="sxs-lookup"><span data-stu-id="8d56d-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="8d56d-137">Následující tabulka uvádí nastavení k dispozici pro **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="8d56d-138">Nastavení pravidla</span><span class="sxs-lookup"><span data-stu-id="8d56d-138">Rule setting</span></span>|<span data-ttu-id="8d56d-139">Popis</span><span class="sxs-lookup"><span data-stu-id="8d56d-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="8d56d-140">**CASCADE**</span><span class="sxs-lookup"><span data-stu-id="8d56d-140">**Cascade**</span></span>|<span data-ttu-id="8d56d-141">Přijmout nebo odmítnout změny na podřízené řádky.</span><span class="sxs-lookup"><span data-stu-id="8d56d-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="8d56d-142">**None**</span><span class="sxs-lookup"><span data-stu-id="8d56d-142">**None**</span></span>|<span data-ttu-id="8d56d-143">V řádcích podřízené provádět žádnou akci.</span><span class="sxs-lookup"><span data-stu-id="8d56d-143">Take no action on child rows.</span></span> <span data-ttu-id="8d56d-144">Toto nastavení je výchozí.</span><span class="sxs-lookup"><span data-stu-id="8d56d-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="8d56d-145">Příklad</span><span class="sxs-lookup"><span data-stu-id="8d56d-145">Example</span></span>  
 <span data-ttu-id="8d56d-146">Následující příklad vytvoří <xref:System.Data.ForeignKeyConstraint>, nastaví některé jeho vlastnosti, včetně <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>a přidává ji k <xref:System.Data.ConstraintCollection> z <xref:System.Data.DataTable> objektu.</span><span class="sxs-lookup"><span data-stu-id="8d56d-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="8d56d-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="8d56d-147">UniqueConstraint</span></span>  
 <span data-ttu-id="8d56d-148">**UniqueConstraint** objekt, který lze přiřadit jeden sloupec nebo pole sloupců **DataTable**, zajistí, že všechna data v zadaný sloupec nebo sloupce, bude jedinečný pro každého řádku.</span><span class="sxs-lookup"><span data-stu-id="8d56d-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="8d56d-149">Jedinečné omezení sloupce nebo pole sloupců můžete vytvořit pomocí **UniqueConstraint** konstruktor.</span><span class="sxs-lookup"><span data-stu-id="8d56d-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="8d56d-150">Předat výsledná **UniqueConstraint** do objektu **přidat** metoda v tabulce **omezení** vlastnost, která je **objektu ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="8d56d-151">Můžete také předat argumenty konstruktoru několik přetížení **přidat** metodu **objektu ConstraintCollection** k vytvoření **UniqueConstraint**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="8d56d-152">Při vytváření **UniqueConstraint** pro sloupec nebo sloupce, můžete volitelně můžete určit, zda sloupec nebo sloupce, primární klíč.</span><span class="sxs-lookup"><span data-stu-id="8d56d-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="8d56d-153">Můžete také vytvořit jedinečné omezení pro sloupec nastavením **jedinečný** vlastnost sloupce, který se **true**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="8d56d-154">Můžete taky nastavení **jedinečný** vlastnost jediný sloupec pro **false** odebere všechny jedinečné omezení, která mohou existovat.</span><span class="sxs-lookup"><span data-stu-id="8d56d-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="8d56d-155">Definování sloupec nebo sloupce jako primární klíč pro tabulku automaticky vytvoří jedinečné omezení pro zadaný sloupec nebo sloupce.</span><span class="sxs-lookup"><span data-stu-id="8d56d-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="8d56d-156">Pokud odeberete sloupce z **PrimaryKey** vlastnost **DataTable**, **UniqueConstraint** se odebere.</span><span class="sxs-lookup"><span data-stu-id="8d56d-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="8d56d-157">Následující příklad vytvoří **UniqueConstraint** pro dva sloupce **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="8d56d-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d56d-158">Viz také</span><span class="sxs-lookup"><span data-stu-id="8d56d-158">See Also</span></span>  
 <xref:System.Data.DataRelation>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.ForeignKeyConstraint>  
 <xref:System.Data.UniqueConstraint>  
 [<span data-ttu-id="8d56d-159">Definice schématu DataTable</span><span class="sxs-lookup"><span data-stu-id="8d56d-159">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="8d56d-160">Datové sady, DataTables a DataView</span><span class="sxs-lookup"><span data-stu-id="8d56d-160">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="8d56d-161">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="8d56d-161">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)