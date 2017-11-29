---
title: "Postupy: Vrstvení objektů ve formulářích Windows"
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
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bda4cb3641ff890646614af35d38ff13621cc16b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="33dd6-102">Postupy: Vrstvení objektů ve formulářích Windows</span><span class="sxs-lookup"><span data-stu-id="33dd6-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="33dd6-103">Při vytváření složitých uživatelského rozhraní nebo pracovat s více formuláře rozhraní (MDI) dokumentu, často můžete vrstvy ovládacích prvků a podřízených formulářů, chcete-li vytvořit složitější uživatelská rozhraní (UI).</span><span class="sxs-lookup"><span data-stu-id="33dd6-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="33dd6-104">Přesunutí a uchovávání informací o ovládací prvky a systému windows v rámci skupiny, můžete upravit pořadí vykreslování.</span><span class="sxs-lookup"><span data-stu-id="33dd6-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="33dd6-105">*Pořadí Z-order* je vizuální rozvržení ovládací prvky ve formuláři podél osy z formuláře (hloubku).</span><span class="sxs-lookup"><span data-stu-id="33dd6-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="33dd6-106">V horní části pořadí z-order okno překrývá všechny ostatní systémy windows.</span><span class="sxs-lookup"><span data-stu-id="33dd6-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="33dd6-107">Všechny ostatní systémy windows překrývat okna v dolní části pořadí.</span><span class="sxs-lookup"><span data-stu-id="33dd6-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33dd6-108">Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.</span><span class="sxs-lookup"><span data-stu-id="33dd6-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="33dd6-109">Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky.</span><span class="sxs-lookup"><span data-stu-id="33dd6-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="33dd6-110">Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="33dd6-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="33dd6-111">K ovládacím prvkům vrstvy v době návrhu</span><span class="sxs-lookup"><span data-stu-id="33dd6-111">To layer controls at design time</span></span>  
  
1.  <span data-ttu-id="33dd6-112">Vyberte ovládací prvek, který chcete vrstvy.</span><span class="sxs-lookup"><span data-stu-id="33dd6-112">Select a control that you want to layer.</span></span>  
  
2.  <span data-ttu-id="33dd6-113">Na **formátu** nabídky, přejděte na příkaz **pořadí**a potom klikněte na **přenést dopředu** nebo **odeslat zpět**.</span><span class="sxs-lookup"><span data-stu-id="33dd6-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="33dd6-114">Chcete-li vrstvy ovládacích prvků prostřednictvím kódu programu</span><span class="sxs-lookup"><span data-stu-id="33dd6-114">To layer controls programmatically</span></span>  
  
-   <span data-ttu-id="33dd6-115">Použití <xref:System.Windows.Forms.Control.BringToFront%2A> a <xref:System.Windows.Forms.Control.SendToBack%2A> metody pro manipulaci s pořadí vykreslování ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="33dd6-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="33dd6-116">Například pokud <xref:System.Windows.Forms.TextBox> řízení, `txtFirstName`, je pod jinou řízení a chcete mít v horní části, použijte následující kód:</span><span class="sxs-lookup"><span data-stu-id="33dd6-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="33dd6-117">Windows Forms podporuje *kontejnerů ovládacích prvků*.</span><span class="sxs-lookup"><span data-stu-id="33dd6-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="33dd6-118">Uzavření ovládacího prvku zahrnuje umístění řadu ovládacích prvků v rámci nadřazeného ovládacího prvku, například počtu <xref:System.Windows.Forms.RadioButton> ovládací prvky v rámci <xref:System.Windows.Forms.GroupBox> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="33dd6-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="33dd6-119">Potom můžete vrstvy ovládací prvky v rámci nadřazeného ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="33dd6-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="33dd6-120">Ovládací prvky taky přesunutím skupinový rámeček přesunete, protože se nacházejí v jeho.</span><span class="sxs-lookup"><span data-stu-id="33dd6-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33dd6-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="33dd6-121">See Also</span></span>  
 [<span data-ttu-id="33dd6-122">Ovládací prvky Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33dd6-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="33dd6-123">Uspořádání ovládacích prvků ve formulářích Windows</span><span class="sxs-lookup"><span data-stu-id="33dd6-123">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="33dd6-124">Popisování jednotlivých Windows Forms – ovládací prvky a zajišťování zástupců pro tyto</span><span class="sxs-lookup"><span data-stu-id="33dd6-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="33dd6-125">Ovládací prvky používané ve formulářích Windows</span><span class="sxs-lookup"><span data-stu-id="33dd6-125">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="33dd6-126">Windows Forms – ovládací prvky podle funkce</span><span class="sxs-lookup"><span data-stu-id="33dd6-126">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)