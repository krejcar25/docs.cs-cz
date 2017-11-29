---
title: "Postupy: Ukotvování ovládacích prvků ve Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c6f7cc527c7409ffecab2ac67386d0f819cce3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="a3910-102">Postupy: Ukotvování ovládacích prvků ve Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3910-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="a3910-103">Při návrhu formuláře, který uživatel může změnit velikost za běhu, ovládací prvky na formuláři by měla velikost a změnit umístění správně.</span><span class="sxs-lookup"><span data-stu-id="a3910-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="a3910-104">Změna velikosti ovládacích prvků dynamicky pomocí formuláře, můžete použít <xref:System.Windows.Forms.Control.Anchor%2A> vlastnosti ovládacích prvků Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a3910-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="a3910-105"><xref:System.Windows.Forms.Control.Anchor%2A> Vlastnost definuje pozice ukotvení pro ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="a3910-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="a3910-106">Když je ukotven ovládacího prvku na formulář a formulář se změnila velikost, ovládacího prvku udržuje vzdálenost mezi ovládacího prvku a pozice ukotvení.</span><span class="sxs-lookup"><span data-stu-id="a3910-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="a3910-107">Pokud máte například <xref:System.Windows.Forms.TextBox> ovládací prvek, který je ukotven k levé, pravé a dolního okraje formuláře, při změně velikosti formuláře <xref:System.Windows.Forms.TextBox> vodorovně řízení změní velikost tak, aby udržuje stejnou vzdálenost od pravé a levé straně formuláře.</span><span class="sxs-lookup"><span data-stu-id="a3910-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="a3910-108">Kromě toho ovládacího prvku umisťuje samotné svisle tak, aby jeho umístění je vždy stejnou vzdálenost od dolní části formuláře.</span><span class="sxs-lookup"><span data-stu-id="a3910-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="a3910-109">Pokud není ukotven ovládacího prvku a formuláře, dojde ke změně pozice ovládacího prvku vůči okrajům formuláře.</span><span class="sxs-lookup"><span data-stu-id="a3910-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="a3910-110"><xref:System.Windows.Forms.Control.Anchor%2A> Vlastnost komunikuje s <xref:System.Windows.Forms.Control.AutoSize%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="a3910-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="a3910-111">Další informace najdete v tématu [přehled vlastnosti AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a3910-111">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3910-112">Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.</span><span class="sxs-lookup"><span data-stu-id="a3910-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a3910-113">Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky.</span><span class="sxs-lookup"><span data-stu-id="a3910-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a3910-114">Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a3910-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="a3910-115">Ukotvení ovládacího prvku ve formuláři</span><span class="sxs-lookup"><span data-stu-id="a3910-115">To anchor a control on a form</span></span>  
  
1.  <span data-ttu-id="a3910-116">Vyberte ovládací prvek, který chcete ukotvení.</span><span class="sxs-lookup"><span data-stu-id="a3910-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a3910-117">Stisknutím klávesy CTRL, klepnutím na každý ovládací prvek a vyberte ji a potom následující zbytek tohoto postupu můžete více ovládacích prvků ukotvení současně.</span><span class="sxs-lookup"><span data-stu-id="a3910-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2.  <span data-ttu-id="a3910-118">V **vlastnosti** okně klikněte na šipku napravo <xref:System.Windows.Forms.Control.Anchor%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="a3910-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="a3910-119">Zobrazí se editoru, který ukazuje na křížek.</span><span class="sxs-lookup"><span data-stu-id="a3910-119">An editor is displayed that shows a cross.</span></span>  
  
3.  <span data-ttu-id="a3910-120">Pokud chcete nastavit anchor, klikněte na tlačítko levému hornímu, pravé nebo dolní části křížek.</span><span class="sxs-lookup"><span data-stu-id="a3910-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="a3910-121">Ovládací prvky jsou ukotven k horní a levé ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="a3910-121">Controls are anchored to the top and left by default.</span></span>  
  
4.  <span data-ttu-id="a3910-122">Zrušte straně ovládací prvek, který není ukotven, klikněte na tlačítko této arm křížek.</span><span class="sxs-lookup"><span data-stu-id="a3910-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5.  <span data-ttu-id="a3910-123">Zavřete <xref:System.Windows.Forms.Control.Anchor%2A> vlastnost editor, klikněte <xref:System.Windows.Forms.Control.Anchor%2A> znovu název vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="a3910-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="a3910-124">Při svého formuláře se zobrazí v době běhu, změní velikost zůstat umístěného ve stejné vzdálenosti od levého okraje formuláře ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a3910-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="a3910-125">Vzdálenost od levého okraje ukotvené vždy nezmění definovaným vzdálenost, když je ovládací prvek umístěn v Návrháři formulářů.</span><span class="sxs-lookup"><span data-stu-id="a3910-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3910-126">Některé ovládací prvky, jako například <xref:System.Windows.Forms.ComboBox> řídit, omezení pro jejich výšku.</span><span class="sxs-lookup"><span data-stu-id="a3910-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="a3910-127">Ukotvení ovládacího prvku k dolnímu okraji jeho formuláře nebo kontejner nemůže vynutit překročení limitu výška ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a3910-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="a3910-128">Musí být zděděné ovládací prvky `Protected` mohli být pevnou.</span><span class="sxs-lookup"><span data-stu-id="a3910-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="a3910-129">Chcete-li změnit úroveň přístupu tohoto ovládacího prvku, nastavte jeho `Modifiers` vlastnost **vlastnosti** okno.</span><span class="sxs-lookup"><span data-stu-id="a3910-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3910-130">Viz také</span><span class="sxs-lookup"><span data-stu-id="a3910-130">See Also</span></span>  
 [<span data-ttu-id="a3910-131">Ovládací prvky Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3910-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="a3910-132">Uspořádání ovládacích prvků ve formulářích Windows</span><span class="sxs-lookup"><span data-stu-id="a3910-132">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="a3910-133">Přehled vlastnosti AutoSize</span><span class="sxs-lookup"><span data-stu-id="a3910-133">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="a3910-134">Postupy: Ukotvování ovládacích prvků ve Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3910-134">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [<span data-ttu-id="a3910-135">Návod: Uspořádání ovládacích prvků na formuláři Windows s použitím ovládacího prvku FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a3910-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="a3910-136">Návod: Uspořádání ovládacích prvků na formuláři Windows s použitím ovládacího prvku TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a3910-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="a3910-137">Návod: Rozvrhování Windows Forms – ovládací prvky s odsazením, okraji a s vlastností AutoSize</span><span class="sxs-lookup"><span data-stu-id="a3910-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)