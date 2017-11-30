---
title: "Dotazování typové datové sady"
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
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd78b4f47d7f48d7b4cbacdf53140758a05b7869
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="querying-typed-datasets"></a>Dotazování typové datové sady
Pokud schéma <xref:System.Data.DataSet> je známý v době návrhu aplikace, doporučujeme použít typem <xref:System.Data.DataSet> při použití [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Představuje zadaný <xref:System.Data.DataSet> je třída, která je odvozena z <xref:System.Data.DataSet>. Jako takový dědí všechny metody, události a vlastnosti <xref:System.Data.DataSet>. Kromě toho typové <xref:System.Data.DataSet> poskytuje silného typu metody, události a vlastnosti. To znamená, že máte přístup tabulky a sloupce, podle názvu, namísto použití metody založené na kolekcích. Díky tomu dotazy jednodušší a srozumitelnější. Další informace najdete v tématu [typové datové sady](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]také podporuje dotazování přes představuje zadaný <xref:System.Data.DataSet>. S zadaný <xref:System.Data.DataSet>, není nutné používat obecná <xref:System.Data.DataRowExtensions.Field%2A> metoda nebo <xref:System.Data.DataRowExtensions.SetField%2A> metoda pro přístup k datům sloupce.  Názvy vlastností jsou k dispozici v době kompilace, protože je součástí informací o typu <xref:System.Data.DataSet>. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]poskytuje přístup k hodnotám sloupce jako správného typu, tak, aby chyby neshoda typu jsou zachyceny při kompilaci kódu místo v době běhu.  
  
 Před zahájením dotazování představuje zadaný <xref:System.Data.DataSet>, musíte vygenerovat třídy pomocí návrháře DataSet v [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  Další informace najdete v tématu [vytvořit a nakonfigurovat datové sady](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje dotaz přes představuje zadaný <xref:System.Data.DataSet>:  
  
```csharp  
var query = from o in orders  
            where o.OnlineOrderFlag == true  
            select new { o.SalesOrderID,  
                         o.OrderDate,  
                         o.SalesOrderNumber };  
  
foreach(var order in query)   
{  
    Console.WriteLine("{0}\t{1:d}\t{2}",   
order.SalesOrderID,   
order.OrderDate,   
order.SalesOrderNumber);  
}  
```  
  
```vb  
Dim orders = ds.Tables("SalesOrderHeader")  
  
Dim query = _  
       From o In orders _  
       Where o.OnlineOrderFlag = True _  
       Select New {SalesOrderID := o.SalesOrderID, _  
                   OrderDate := o.OrderDate, _  
                   SalesOrderNumber := o.SalesOrderNumber}  
  
For Each Dim onlineOrder In query  
 Console.WriteLine("{0}\t{1:d}\t{2}", _  
 onlineOrder.SalesOrderID, _  
 onlineOrder.OrderDate, _  
 onlineOrder.SalesOrderNumber)  
Next  
```  
  
## <a name="see-also"></a>Viz také  
 [Dotazování datové sady](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Dotazy křížové tabulky](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [Dotazy na jedné tabulky](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)