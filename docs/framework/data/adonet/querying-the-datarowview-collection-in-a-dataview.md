---
title: "Dotazování na kolekci DataRowView v v zobrazení DataView"
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
ms.assetid: b9070a12-1094-44d6-bb87-a23b50bcb0af
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b17a489552e7b2bcb6044fce99e5f526b8293a25
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="querying-the-datarowview-collection-in-a-dataview"></a><span data-ttu-id="c3b8e-102">Dotazování na kolekci DataRowView v v zobrazení DataView</span><span class="sxs-lookup"><span data-stu-id="c3b8e-102">Querying the DataRowView Collection in a DataView</span></span>
<span data-ttu-id="c3b8e-103"><xref:System.Data.DataView> Zpřístupní vyčíslitelná kolekce <xref:System.Data.DataRowView> objekty.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-103">The <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="c3b8e-104"><xref:System.Data.DataRowView>představuje vlastní pohled <xref:System.Data.DataRow> a zobrazí se na konkrétní verzi této <xref:System.Data.DataRow> v ovládacím prvku.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-104"><xref:System.Data.DataRowView> represents a customized view of a <xref:System.Data.DataRow> and displays a specific version of that <xref:System.Data.DataRow> in a control.</span></span> <span data-ttu-id="c3b8e-105">Jenom jedna verze nástroje <xref:System.Data.DataRow> lze zobrazit pomocí ovládacího prvku, například <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-105">Only one version of a <xref:System.Data.DataRow> can be displayed through a control, such as a <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="c3b8e-106">Dostanete <xref:System.Data.DataRow> který je zveřejněný prostřednictvím <xref:System.Data.DataRowView> prostřednictvím <xref:System.Data.DataRowView.Row%2A> vlastnost <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-106">You can access the <xref:System.Data.DataRow> that is exposed by the <xref:System.Data.DataRowView> through the <xref:System.Data.DataRowView.Row%2A> property of the <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="c3b8e-107">Při zobrazení hodnoty pomocí <xref:System.Data.DataRowView>, <xref:System.Data.DataView.RowStateFilter%2A> vlastnost určuje, která verze řádku základní <xref:System.Data.DataRow> zpřístupněn.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-107">When you view values by using a <xref:System.Data.DataRowView>, the <xref:System.Data.DataView.RowStateFilter%2A> property determines which row version of the underlying <xref:System.Data.DataRow> is exposed.</span></span> <span data-ttu-id="c3b8e-108">Informace o přístupu k jiné řádek verze, která používá <xref:System.Data.DataRow>, najdete v části [stavy řádků a verze řádku](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="c3b8e-108">For information about accessing different row versions using a <xref:System.Data.DataRow>, see [Row States and Row Versions](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span> <span data-ttu-id="c3b8e-109">Protože kolekce <xref:System.Data.DataRowView> objekty, které jsou zveřejněné <xref:System.Data.DataView> je vyčíslitelná, můžete použít [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] dotazu nad ním.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-109">Because the collection of <xref:System.Data.DataRowView> objects exposed by the <xref:System.Data.DataView> is enumerable, you can use [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to query over it.</span></span>  
  
 <span data-ttu-id="c3b8e-110">Následující příklad dotazy `Product` tabulky produktů red stejné barvy a vytvoří tabulku z tohoto dotazu.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-110">The following example queries the `Product` table for red-colored products and creates a table from that query.</span></span> <span data-ttu-id="c3b8e-111">A <xref:System.Data.DataView> se vytvoří z tabulky a <xref:System.Data.DataView.RowStateFilter%2A> je nastavena na filtrovat odstraněné a upravených řádků.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-111">A <xref:System.Data.DataView> is created from the table and the <xref:System.Data.DataView.RowStateFilter%2A> property is set to filter on deleted and modified rows.</span></span> <span data-ttu-id="c3b8e-112"><xref:System.Data.DataView> Se pak použije jako zdroj v dotazu LINQ a <xref:System.Data.DataRowView> objekty, které byly upravit a odstranit je vázána na <xref:System.Windows.Forms.DataGridView> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-112">The <xref:System.Data.DataView> is then used as a source in a LINQ query, and the <xref:System.Data.DataRowView> objects that have been modified and deleted are bound to a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[DP DataView Samples#QueryDataView2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview2)]
 [!code-vb[DP DataView Samples#QueryDataView2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview2)]  
  
 <span data-ttu-id="c3b8e-113">Následující příklad vytvoří tabulku produktů ze zobrazení, která je vázána <xref:System.Windows.Forms.DataGridView> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-113">The following example creates a table of products from a view that is bound to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c3b8e-114"><xref:System.Data.DataView> Je dotazován na stejné barvy red produkty a seřazené výsledků je vázána na <xref:System.Windows.Forms.DataGridView> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="c3b8e-114">The <xref:System.Data.DataView> is queried for red-colored products and the ordered results are bound to a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[DP DataView Samples#QueryDataView1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview1)]
 [!code-vb[DP DataView Samples#QueryDataView1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview1)]  
  
## <a name="see-also"></a><span data-ttu-id="c3b8e-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="c3b8e-115">See Also</span></span>  
 [<span data-ttu-id="c3b8e-116">Datové vazby a LINQ na DataSet</span><span class="sxs-lookup"><span data-stu-id="c3b8e-116">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)