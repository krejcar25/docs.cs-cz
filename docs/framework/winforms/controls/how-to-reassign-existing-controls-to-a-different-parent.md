---
title: "Postupy: Přiřazení existujících ovládacích prvků jinému nadřazenému prvku"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8a120d1d80f40353eb7e0c3feb26c224175cc72
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="fd4f5-102">Postupy: Přiřazení existujících ovládacích prvků jinému nadřazenému prvku</span><span class="sxs-lookup"><span data-stu-id="fd4f5-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="fd4f5-103">Ovládací prvky, které existují můžete přiřadit ve formuláři do ovládacího prvku nový kontejner.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-103">You can assign controls that exist on your form to a new container control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd4f5-104">Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fd4f5-105">Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fd4f5-106">Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="fd4f5-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="fd4f5-107">K přiřazení existujících ovládacích prvků jinému nadřazenému prvku</span><span class="sxs-lookup"><span data-stu-id="fd4f5-107">To reassign existing controls to a different parent</span></span>  
  
1.  <span data-ttu-id="fd4f5-108">Přetáhněte tři <xref:System.Windows.Forms.Button> z ovládací prvky **sada nástrojů** do formuláře.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-108">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>  
  
     <span data-ttu-id="fd4f5-109">Umístit je blízko sebe, ale nechte je nezarovnané.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-109">Position them near to each other, but leave them unaligned.</span></span>  
  
2.  <span data-ttu-id="fd4f5-110">V **sada nástrojů**, klikněte na tlačítko <xref:System.Windows.Forms.FlowLayoutPanel> ikonu ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-110">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>  
  
     <span data-ttu-id="fd4f5-111">Není přetáhněte ikonu do formuláře.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-111">Do not drag the icon onto the form.</span></span>  
  
3.  <span data-ttu-id="fd4f5-112">Přesunutí ukazatele myši blízko tří <xref:System.Windows.Forms.Button> ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-112">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
     <span data-ttu-id="fd4f5-113">Ukazatel se změní na záměrný kříž s <xref:System.Windows.Forms.FlowLayoutPanel> řízení ikonu připojen.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-113">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>  
  
4.  <span data-ttu-id="fd4f5-114">Klikněte na tlačítko a podržte tlačítko myši.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-114">Click and hold the mouse button.</span></span>  
  
5.  <span data-ttu-id="fd4f5-115">Přetáhněte ukazatel myši k vykreslení obrys <xref:System.Windows.Forms.FlowLayoutPanel> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-115">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6.  <span data-ttu-id="fd4f5-116">Kreslení obrys kolem tří <xref:System.Windows.Forms.Button> ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-116">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
7.  <span data-ttu-id="fd4f5-117">Uvolnění tlačítka myši.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-117">Release the mouse button.</span></span>  
  
     <span data-ttu-id="fd4f5-118">Tří <xref:System.Windows.Forms.Button> ovládací prvky jsou vloženy do <xref:System.Windows.Forms.FlowLayoutPanel> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-118">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4f5-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="fd4f5-119">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="fd4f5-120">Uspořádání ovládacích prvků ve formulářích Windows</span><span class="sxs-lookup"><span data-stu-id="fd4f5-120">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="fd4f5-121">Návod: Uspořádání ovládacích prvků na formuláři Windows s použitím ovládacího prvku TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="fd4f5-121">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="fd4f5-122">Návod: Uspořádání ovládacích prvků ve Windows Forms pomocí zarovnávacích čar</span><span class="sxs-lookup"><span data-stu-id="fd4f5-122">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)