---
title: "Postupy: Zablokování sloupců v ovládacím prvku Windows Forms DataGridView pomocí Návrháře"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a97899d544dcc0d9f9ad59cbb34a01da76ef5fe5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="7dfb1-102">Postupy: Zablokování sloupců v ovládacím prvku Windows Forms DataGridView pomocí Návrháře</span><span class="sxs-lookup"><span data-stu-id="7dfb1-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="7dfb1-103">Když uživatelé zobrazit data zobrazená v systému Windows Forms <xref:System.Windows.Forms.DataGridView> ovládací prvek, někdy potřebují k odkazování na jeden sloupec nebo sadu sloupců často.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="7dfb1-104">Například když zobrazíte informace o zákazníkovi, který obsahuje mnoho sloupců tabulky, je vhodné pro zobrazit jméno zákazníka za všech okolností při povolování ostatních sloupců posun mimo oblast viditelné.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="7dfb1-105">K dosažení toto chování, můžete zmrazení sloupců v ovládacím prvku.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="7dfb1-106">Po ukotvení sloupec se všechny sloupce na levé straně, (nebo záhlavím vpravo ve skriptech jazyk zprava doleva) jsou také pozastaveny.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="7dfb1-107">Ukotvené sloupce, takže zůstávají na svém místě, při lze posunout všech ostatních sloupců.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="7dfb1-108">Pokud je povoleno změny pořadí sloupců, ukotvené sloupce jsou považovány za skupinu liší od neukotvené sloupce.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="7dfb1-109">Uživatelé mohou změnit umístění sloupce buď skupiny, ale sloupec nemůže přesunout z jedné skupiny na druhý.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="7dfb1-110">Následující postup vyžaduje **aplikace Windows** projekt pomocí formuláře obsahující <xref:System.Windows.Forms.DataGridView> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="7dfb1-111">Informace o nastavení tohoto projektu najdete v tématu [postupy: vytvoření projektu aplikace Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) a [postupy: Přidání ovládacích prvků do formulářů Windows](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7dfb1-111">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dfb1-112">Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7dfb1-113">Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7dfb1-114">Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="7dfb1-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="7dfb1-115">Chcete-li ukotvit sloupec pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="7dfb1-115">To freeze a column using the designer</span></span>  
  
1.  <span data-ttu-id="7dfb1-116">Klikněte na inteligentní značky glyfy (![inteligentní značky glyfy](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) v pravém horním rohu <xref:System.Windows.Forms.DataGridView> řízení a potom vyberte **upravit sloupce**.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-116">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="7dfb1-117">Vyberte sloupce z **vybrané sloupce** seznamu.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-117">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="7dfb1-118">V **vlastnosti sloupce** mřížky, nastavte <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> vlastnost `true`.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-118">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7dfb1-119">Můžete také ukotvit sloupec při přidávání výběrem **zmrazené** pole **přidat sloupec** dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="7dfb1-119">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfb1-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="7dfb1-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="7dfb1-121">Postupy: přidávání a odebírání sloupců v systému Windows Forms DataGridView – ovládací prvek pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="7dfb1-121">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="7dfb1-122">Postupy: povolení změny pořadí sloupců v prvku Windows Forms DataGridView pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="7dfb1-122">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="7dfb1-123">Postupy: zobrazení textu zprava doleva ve Windows Forms pro globalizaci</span><span class="sxs-lookup"><span data-stu-id="7dfb1-123">How to: Display Right-to-Left Text in Windows Forms for Globalization</span></span>](http://msdn.microsoft.com/en-us/f0663385-2354-4c65-8676-706422283b14)  
 [<span data-ttu-id="7dfb1-124">Postupy: vytvoření projektu aplikace Windows</span><span class="sxs-lookup"><span data-stu-id="7dfb1-124">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="7dfb1-125">Postupy: Přidání ovládacích prvků do formulářů Windows</span><span class="sxs-lookup"><span data-stu-id="7dfb1-125">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)