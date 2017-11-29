---
title: Metoda AcceptChanges a RejectChanges
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
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6ac64fee869ce58413e799f4217f009ef6ae91a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="a5908-102">Metoda AcceptChanges a RejectChanges</span><span class="sxs-lookup"><span data-stu-id="a5908-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="a5908-103">Po ověření správnosti změny dat v <xref:System.Data.DataTable>, může přijmout změny pomocí <xref:System.Data.DataRow.AcceptChanges%2A> metodu <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, nebo <xref:System.Data.DataSet>, který bude nastaven **aktuální** řádek hodnoty, které mají být **původní** hodnoty a nastaví **RowState** vlastnost **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="a5908-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="a5908-104">Přijetí nebo odmítnutí změny vymaže se žádné **RowError** informace a nastaví **HasErrors** vlastnost **false**.</span><span class="sxs-lookup"><span data-stu-id="a5908-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="a5908-105">Přijetí nebo odmítnutí změny může ovlivnit také aktualizace dat v datovém zdroji.</span><span class="sxs-lookup"><span data-stu-id="a5908-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="a5908-106">Další informace najdete v tématu [aktualizace zdroje dat s DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="a5908-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="a5908-107">Pokud existují omezení cizího klíče na **DataTable**, změny přijetí nebo odmítnutí pomocí **metoda AcceptChanges** a **RejectChanges** rozšířeny podřízené řádky  **DataRow** podle požadavků **ForeignKeyConstraint.AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="a5908-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="a5908-108">Další informace najdete v tématu [DataTable omezení](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="a5908-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="a5908-109">Následující příklad kontroluje řádků s chybami, řeší chyby, kde je to možné a odmítne řádky, kde chyba nelze přeložit.</span><span class="sxs-lookup"><span data-stu-id="a5908-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="a5908-110">Všimněte si, že pro vyřešit chyby, **RowError** hodnota je nastaven na prázdný řetězec, příčinou **HasErrors** vlastnost, která má být nastavena na **false**.</span><span class="sxs-lookup"><span data-stu-id="a5908-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="a5908-111">Když všechny řádky s chybami byly vyřešeny nebo zamítnutí, **metoda AcceptChanges** nazývá tak, aby přijímal všechny změny pro celý **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="a5908-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5908-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="a5908-112">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="a5908-113">Manipulace s daty v DataTable</span><span class="sxs-lookup"><span data-stu-id="a5908-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="a5908-114">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="a5908-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)