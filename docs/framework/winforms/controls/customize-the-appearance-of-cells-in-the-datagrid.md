---
title: "Postupy: Přizpůsobení vzhledu buněk v ovládacím prvku Windows Forms DataGridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 545a3bff5e810f9c0a995366e7f6460930f9e936
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="cfdf9-102">Postupy: Přizpůsobení vzhledu buněk v ovládacím prvku Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="cfdf9-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cfdf9-103">Můžete přizpůsobit vzhled libovolnou buňku zpracování <xref:System.Windows.Forms.DataGridView> ovládacího prvku <xref:System.Windows.Forms.DataGridView.CellPainting> událostí.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="cfdf9-104">Můžete rozbalit <xref:System.Windows.Forms.DataGridView> ovládacího prvku <xref:System.Drawing.Graphics> z <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> vlastnost <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="cfdf9-105">Pomocí této <xref:System.Drawing.Graphics>, může ovlivnit vzhled celý <xref:System.Windows.Forms.DataGridView> řízení, ale bude obvykle má vliv pouze na vzhled buňku, která je aktuálně probíhá vykresluje.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="cfdf9-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> Vlastnost <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> umožňuje omezit na buňku, která je aktuálně probíhá vykresluje vaší Malování operací.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="cfdf9-107">V následujícím příkladu kódu, bude v buňkách v malování `ContactName` sloupce pomocí <xref:System.Windows.Forms.DataGridView> ovládacího prvku barevné schéma.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="cfdf9-108">Obsah textu jednotlivých buněk se vykresluje v <xref:System.Drawing.Color.Crimson%2A>, a inset obdélníku se vykresluje v barvu stejné jako <xref:System.Windows.Forms.DataGridView> ovládacího prvku <xref:System.Windows.Forms.DataGridView.GridColor%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfdf9-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="cfdf9-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cfdf9-110">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="cfdf9-110">Compiling the Code</span></span>  
 <span data-ttu-id="cfdf9-111">Tento příklad vyžaduje:</span><span class="sxs-lookup"><span data-stu-id="cfdf9-111">This example requires:</span></span>  
  
-   <span data-ttu-id="cfdf9-112">A <xref:System.Windows.Forms.DataGridView> ovládací prvek s názvem `dataGridView1` s `ContactName` sloupců, jako je třeba v tabulce zákazníků v ukázkové databázi Northwind.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="cfdf9-113">Odkazy na sestavení systému, System.Windows.Forms a System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="cfdf9-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfdf9-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="cfdf9-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [<span data-ttu-id="cfdf9-115">Přizpůsobení ovládacího prvku Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="cfdf9-115">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)