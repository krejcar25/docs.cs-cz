---
title: "SplitContainer – přehled ovládacího prvku (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SplitContainer
helpviewer_keywords: SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10f18c46c85ed840b6625d9ed754d1d036a80975
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="splitcontainer-control-overview-windows-forms"></a><span data-ttu-id="fda0e-102">SplitContainer – přehled ovládacího prvku (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="fda0e-102">SplitContainer Control Overview (Windows Forms)</span></span>
<span data-ttu-id="fda0e-103">Windows Forms <xref:System.Windows.Forms.SplitContainer> řízení lze považovat za složené; je dva panely oddělených mobilní panelu.</span><span class="sxs-lookup"><span data-stu-id="fda0e-103">The Windows Forms <xref:System.Windows.Forms.SplitContainer> control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="fda0e-104">Když ukazatel myši nad panelu, změní tvar, který má zobrazit, že je na panelu mobilní.</span><span class="sxs-lookup"><span data-stu-id="fda0e-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fda0e-105">V **sada nástrojů**, <xref:System.Windows.Forms.SplitContainer> řízení nahradí <xref:System.Windows.Forms.Splitter> ovládací prvek, který se někdo v předchozí verzi [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fda0e-105">In the **Toolbox**, <xref:System.Windows.Forms.SplitContainer> control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="fda0e-106"><xref:System.Windows.Forms.SplitContainer> Ovládací prvek je mnohem upřednostňované přes <xref:System.Windows.Forms.Splitter> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="fda0e-106">The <xref:System.Windows.Forms.SplitContainer> control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="fda0e-107"><xref:System.Windows.Forms.Splitter> Třída je stále součástí [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] pro kompatibilitě se stávajícími aplikacemi, ale důrazně doporučujeme používat <xref:System.Windows.Forms.SplitContainer> ovládací prvek pro nové projekty.</span><span class="sxs-lookup"><span data-stu-id="fda0e-107">The <xref:System.Windows.Forms.Splitter> class is still included in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for compatibility with existing applications, but we strongly encourage you to use the <xref:System.Windows.Forms.SplitContainer> control for new projects.</span></span>  
  
 <span data-ttu-id="fda0e-108">Pomocí <xref:System.Windows.Forms.SplitContainer> ovládací prvek, můžete vytvořit komplexní uživatelská rozhraní; často výběr jeden panelu určuje, které objekty se zobrazují panelu.</span><span class="sxs-lookup"><span data-stu-id="fda0e-108">With the <xref:System.Windows.Forms.SplitContainer> control, you can create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="fda0e-109">Toto uspořádání je velmi efektivní pro zobrazení a procházení informace.</span><span class="sxs-lookup"><span data-stu-id="fda0e-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="fda0e-110">S dvěma panelů umožňuje agregovat informace v oblastech, a panelu nebo "rozdělovače," usnadňuje uživatelům změnit velikost panely.</span><span class="sxs-lookup"><span data-stu-id="fda0e-110">Having two panels lets you aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
 <span data-ttu-id="fda0e-111">Více než jeden <xref:System.Windows.Forms.SplitContainer> řízení mohou být také vnořené, s druhou <xref:System.Windows.Forms.SplitContainer> řízení orientován vodorovně, vytvořit horní a dolní panelů.</span><span class="sxs-lookup"><span data-stu-id="fda0e-111">More than one <xref:System.Windows.Forms.SplitContainer> control can also be nested, with the second <xref:System.Windows.Forms.SplitContainer> control oriented horizontally, to create top and bottom panels.</span></span>  
  
 <span data-ttu-id="fda0e-112">Mějte na paměti, <xref:System.Windows.Forms.SplitContainer> je přístupný z klávesnice ve výchozím nastavení řízení; uživatelé stisknutím klávesy se šipkami přesunout rozdělovače, pokud <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> je nastavena na `false`.</span><span class="sxs-lookup"><span data-stu-id="fda0e-112">Be aware that the <xref:System.Windows.Forms.SplitContainer> control is keyboard-accessible by default; users can press the ARROW keys to move the splitter if the <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property is set to `false`.</span></span>  
  
 <span data-ttu-id="fda0e-113"><xref:System.Windows.Forms.SplitContainer.Orientation%2A> Vlastnost <xref:System.Windows.Forms.SplitContainer> řízení Určuje směr, rozdělovače, není z ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="fda0e-113">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span> <span data-ttu-id="fda0e-114">Proto, pokud je tato vlastnost nastavená na <xref:System.Windows.Forms.Orientation.Vertical>, běží rozdělovače shora dolů, vytváření panelů vlevo a vpravo.</span><span class="sxs-lookup"><span data-stu-id="fda0e-114">Hence, when this property is set to <xref:System.Windows.Forms.Orientation.Vertical>, the splitter runs from top to bottom, creating left and right panels.</span></span>  
  
 <span data-ttu-id="fda0e-115">Kromě toho mějte na paměti, hodnota <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> vlastnost se liší v závislosti na hodnotě <xref:System.Windows.Forms.SplitContainer.Orientation%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="fda0e-115">Additionally, be aware that the value of the <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> property varies depending on the value of the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property.</span></span> <span data-ttu-id="fda0e-116">Další informace najdete v tématu <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="fda0e-116">For more information, see <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> property.</span></span>  
  
 <span data-ttu-id="fda0e-117">Můžete taky omezit velikost a pohybu <xref:System.Windows.Forms.SplitContainer> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="fda0e-117">You can also restrict the size and movement of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="fda0e-118"><xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> Vlastnost určuje, které panel zůstane stejnou velikost po <xref:System.Windows.Forms.SplitContainer> po změně velikosti a <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> vlastnost určuje, zda rozdělovače mobilní klávesnice nebo myš.</span><span class="sxs-lookup"><span data-stu-id="fda0e-118">The <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> property determines which panel will remain the same size after the <xref:System.Windows.Forms.SplitContainer> control is resized, and the <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property determines if the splitter is movable by the keyboard or mouse.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fda0e-119">I když <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> je nastavena na `true`, rozdělovače může stále přesunout prostřednictvím kódu programu, například pomocí <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="fda0e-119">Even if the <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property is set to `true`, the splitter may still be moved programmatically; for example, by using the <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property.</span></span>  
  
 <span data-ttu-id="fda0e-120">Nakonec, jednotlivé panely <xref:System.Windows.Forms.SplitContainer> řízení má vlastnosti k určení jeho jednotlivé velikosti.</span><span class="sxs-lookup"><span data-stu-id="fda0e-120">Finally, each panel of the <xref:System.Windows.Forms.SplitContainer> control has properties to determine its individual size.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="fda0e-121">Běžně používané vlastnosti, metod a události</span><span class="sxs-lookup"><span data-stu-id="fda0e-121">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="fda0e-122">Název</span><span class="sxs-lookup"><span data-stu-id="fda0e-122">Name</span></span>|<span data-ttu-id="fda0e-123">Popis</span><span class="sxs-lookup"><span data-stu-id="fda0e-123">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="fda0e-124"><xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>Vlastnost</span><span class="sxs-lookup"><span data-stu-id="fda0e-124"><xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> property</span></span>|<span data-ttu-id="fda0e-125">Určuje, které panel zůstane stejný velikost po <xref:System.Windows.Forms.SplitContainer> po změně velikosti.</span><span class="sxs-lookup"><span data-stu-id="fda0e-125">Determines which panel will remain the same size after the <xref:System.Windows.Forms.SplitContainer> control is resized.</span></span>|  
|<span data-ttu-id="fda0e-126"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>Vlastnost</span><span class="sxs-lookup"><span data-stu-id="fda0e-126"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="fda0e-127">Určuje, zda lze přesunout rozdělovače s klávesnici nebo myš.</span><span class="sxs-lookup"><span data-stu-id="fda0e-127">Determines if the splitter can be moved with the keyboard or mouse.</span></span>|  
|<span data-ttu-id="fda0e-128"><xref:System.Windows.Forms.SplitContainer.Orientation%2A>Vlastnost</span><span class="sxs-lookup"><span data-stu-id="fda0e-128"><xref:System.Windows.Forms.SplitContainer.Orientation%2A> property</span></span>|<span data-ttu-id="fda0e-129">Určuje, pokud je rozdělovače uspořádané vodorovně nebo svisle.</span><span class="sxs-lookup"><span data-stu-id="fda0e-129">Determines if the splitter is arranged vertically or horizontally.</span></span>|  
|<span data-ttu-id="fda0e-130"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>Vlastnost</span><span class="sxs-lookup"><span data-stu-id="fda0e-130"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="fda0e-131">Určuje vzdálenost v pixelech od levého nebo horního okraje mobilní dělicí panel.</span><span class="sxs-lookup"><span data-stu-id="fda0e-131">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="fda0e-132"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>Vlastnost</span><span class="sxs-lookup"><span data-stu-id="fda0e-132"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="fda0e-133">Určuje minimální vzdálenost v pixelech, že rozdělovače lze přesunout uživatelem.</span><span class="sxs-lookup"><span data-stu-id="fda0e-133">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
|<span data-ttu-id="fda0e-134"><xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>Vlastnost</span><span class="sxs-lookup"><span data-stu-id="fda0e-134"><xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> property</span></span>|<span data-ttu-id="fda0e-135">Určuje tloušťku v pixelech rozdělovače.</span><span class="sxs-lookup"><span data-stu-id="fda0e-135">Determines the thickness, in pixels, of the splitter.</span></span>|  
|<span data-ttu-id="fda0e-136"><xref:System.Windows.Forms.SplitContainer.SplitterMoving>události</span><span class="sxs-lookup"><span data-stu-id="fda0e-136"><xref:System.Windows.Forms.SplitContainer.SplitterMoving> event</span></span>|<span data-ttu-id="fda0e-137">Nastane, když je rozdělovače přesunutí.</span><span class="sxs-lookup"><span data-stu-id="fda0e-137">Occurs when the splitter is moving.</span></span>|  
|<span data-ttu-id="fda0e-138"><xref:System.Windows.Forms.SplitContainer.SplitterMoved>události</span><span class="sxs-lookup"><span data-stu-id="fda0e-138"><xref:System.Windows.Forms.SplitContainer.SplitterMoved> event</span></span>|<span data-ttu-id="fda0e-139">Nastane, když rozdělovače přesunul.</span><span class="sxs-lookup"><span data-stu-id="fda0e-139">Occurs when the splitter has moved.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fda0e-140">Viz také</span><span class="sxs-lookup"><span data-stu-id="fda0e-140">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="fda0e-141">SplitContainer – ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="fda0e-141">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [<span data-ttu-id="fda0e-142">Ukázka ovládacího prvku SplitContainer</span><span class="sxs-lookup"><span data-stu-id="fda0e-142">SplitContainer Control Sample</span></span>](http://msdn.microsoft.com/en-us/9015fad0-7108-4d85-a83a-a72d038c4f65)