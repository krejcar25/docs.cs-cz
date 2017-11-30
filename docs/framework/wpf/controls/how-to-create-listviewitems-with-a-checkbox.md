---
title: "Postupy: Vytváření ListViewItems pomocí CheckBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6ebb3671dcc65d690fde5d4796c9034553eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="cf037-102">Postupy: Vytváření ListViewItems pomocí CheckBox</span><span class="sxs-lookup"><span data-stu-id="cf037-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="cf037-103">Tento příklad ukazuje, jak zobrazit sloupec <xref:System.Windows.Controls.CheckBox> ovládacích prvků do <xref:System.Windows.Controls.ListView> ovládací prvek, který používá <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="cf037-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf037-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="cf037-104">Example</span></span>  
 <span data-ttu-id="cf037-105">Chcete-li vytvořit sloupec, který obsahuje <xref:System.Windows.Controls.CheckBox> ovládacích prvků do <xref:System.Windows.Controls.ListView>, vytvoření <xref:System.Windows.DataTemplate> obsahující <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="cf037-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="cf037-106">Nastavte <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> z <xref:System.Windows.Controls.GridViewColumn> k <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="cf037-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="cf037-107">Následující příklad ukazuje <xref:System.Windows.DataTemplate> obsahující <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="cf037-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="cf037-108">V příkladu váže <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> vlastnost <xref:System.Windows.Controls.CheckBox> k <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> hodnota vlastnosti <xref:System.Windows.Controls.ListViewItem> který ji obsahuje.</span><span class="sxs-lookup"><span data-stu-id="cf037-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="cf037-109">Proto když <xref:System.Windows.Controls.ListViewItem> obsahující <xref:System.Windows.Controls.CheckBox> je vybraná, <xref:System.Windows.Controls.CheckBox> je zaškrtnuta možnost.</span><span class="sxs-lookup"><span data-stu-id="cf037-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="cf037-110">Následující příklad ukazuje, jak vytvořit sloupec <xref:System.Windows.Controls.CheckBox> ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="cf037-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="cf037-111">Chcete-li sloupec v příkladu je nastavena <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> vlastnost <xref:System.Windows.Controls.GridViewColumn> k <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="cf037-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="cf037-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="cf037-112">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="cf037-113">ListView – přehled</span><span class="sxs-lookup"><span data-stu-id="cf037-113">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="cf037-114">Postupy: témata</span><span class="sxs-lookup"><span data-stu-id="cf037-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="cf037-115">Rutina GridView – přehled</span><span class="sxs-lookup"><span data-stu-id="cf037-115">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)