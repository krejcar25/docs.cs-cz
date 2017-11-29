---
title: "Úvod k ovládacím prvkům Čára a Tvar (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e691d57c6de640c83556937eeddedf89e79b6846
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a><span data-ttu-id="a59da-102">Úvod k ovládacím prvkům Čára a Tvar (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="a59da-102">Introduction to the Line and Shape Controls (Visual Studio)</span></span>
<span data-ttu-id="a59da-103">Ovládací prvky jazyka Visual Basic Power Pack Line a Shape jsou sadu tři grafické ovládacích prvků, které vám umožní kreslení čar a obrazců ve formulářích a kontejnerech.</span><span class="sxs-lookup"><span data-stu-id="a59da-103">The Visual Basic Power Packs Line and Shape controls are a set of three graphical controls that enable you to draw lines and shapes on forms and containers.</span></span> <span data-ttu-id="a59da-104"><xref:Microsoft.VisualBasic.PowerPacks.LineShape> Řízení slouží k vykreslení vodorovné, svislé a diagonálních čáry.</span><span class="sxs-lookup"><span data-stu-id="a59da-104">The <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control is used to draw horizontal, vertical, and diagonal lines.</span></span> <span data-ttu-id="a59da-105"><xref:Microsoft.VisualBasic.PowerPacks.OvalShape> Řízení slouží k vykreslení kružnice a elipsy a <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> řízení slouží k vykreslení obdélníků a čtverce.</span><span class="sxs-lookup"><span data-stu-id="a59da-105">The <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> control is used to draw circles and ovals, and the <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control is used to draw rectangles and squares.</span></span>  
  
## <a name="line-and-shape-controls"></a><span data-ttu-id="a59da-106">Čára a Tvar – ovládací prvky</span><span class="sxs-lookup"><span data-stu-id="a59da-106">Line and Shape Controls</span></span>  
 <span data-ttu-id="a59da-107">Line a Shape – ovládací prvky pro zapouzdření řadu grafiky metody, které jsou součástí <xref:System.Drawing> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="a59da-107">Line and Shape controls encapsulate many of the graphics methods that are contained in the <xref:System.Drawing> namespace.</span></span> <span data-ttu-id="a59da-108">To umožňuje kreslení čar a tvarů bez nutnosti vytváření grafických objektů, pera a štětce v jediném kroku.</span><span class="sxs-lookup"><span data-stu-id="a59da-108">This enables you to draw lines and shapes in a single step without having to create graphics objects, pens, and brushes.</span></span> <span data-ttu-id="a59da-109">Složité grafické technologie například přechodu výplně lze provést pouze pomocí nastavení některé vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="a59da-109">Complex graphics techniques such as gradient fills can be accomplished by just setting some properties.</span></span>  
  
 <span data-ttu-id="a59da-110">I když je také možné kreslení čar a obrazců pomocí metod grafiky, má několik výhod pro používání ovládacích prvků, čára a tvar:</span><span class="sxs-lookup"><span data-stu-id="a59da-110">Although it is also possible to draw lines and shapes by using graphics methods, there are several advantages to using the Line and Shape controls:</span></span>  
  
-   <span data-ttu-id="a59da-111">Grafické metody lze volat pouze za běhu.</span><span class="sxs-lookup"><span data-stu-id="a59da-111">Graphics methods can be called only at run time.</span></span> <span data-ttu-id="a59da-112">Line a Shape – ovládací prvky můžete přidat do formuláře v době návrhu.</span><span class="sxs-lookup"><span data-stu-id="a59da-112">Line and Shape controls can be added to a form at design time.</span></span> <span data-ttu-id="a59da-113">Díky tomu můžete zobrazit, jak vypadají a umístit je přesně; také mohou být přidány za běhu.</span><span class="sxs-lookup"><span data-stu-id="a59da-113">This enables you to see what they look like and to position them exactly; they can also be added at run time.</span></span>  
  
-   <span data-ttu-id="a59da-114">Line a Shape – ovládací prvky jsou volitelný za běhu, jako poskytují události <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> a <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>.</span><span class="sxs-lookup"><span data-stu-id="a59da-114">Line and Shape controls are selectable at run time, providing events such as <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> and <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>.</span></span> <span data-ttu-id="a59da-115">Výstupy z grafických metod nelze vybrat a neposkytují události.</span><span class="sxs-lookup"><span data-stu-id="a59da-115">The outputs of graphics methods are not selectable and do not provide events.</span></span>  
  
-   <span data-ttu-id="a59da-116">Ovládací prvky Line a Shape poskytují <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> a <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> metody, které vám umožňují řídit pořadí vykreslování v době návrhu a v době běhu.</span><span class="sxs-lookup"><span data-stu-id="a59da-116">Line and Shape controls provide <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> and <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> methods that enable you to control their z-order at design time and at run time.</span></span> <span data-ttu-id="a59da-117">Pořadí vykreslování grafických metody lze řídit jenom změnou jejich pořadí spouštění v době běhu.</span><span class="sxs-lookup"><span data-stu-id="a59da-117">The z-order of graphics methods can be controlled only by changing their order of execution at run time.</span></span>  
  
-   <span data-ttu-id="a59da-118">Line a Shape – ovládací prvky jsou bez oken ovládací prvky; Tyto nemají žádné popisovače okna a proto používat méně systémových prostředků.</span><span class="sxs-lookup"><span data-stu-id="a59da-118">Line and Shape controls are windowless controls; they have no window handles and therefore use less system resources.</span></span>  
  
### <a name="object-model"></a><span data-ttu-id="a59da-119">Objektový Model</span><span class="sxs-lookup"><span data-stu-id="a59da-119">Object Model</span></span>  
 <span data-ttu-id="a59da-120">Line a Shape ovládací prvky jsou odvozeny od základní <xref:Microsoft.VisualBasic.PowerPacks.Shape> třídu, která definuje jejich sdílené vlastnosti, metod a události.</span><span class="sxs-lookup"><span data-stu-id="a59da-120">Line and Shape controls derive from a base <xref:Microsoft.VisualBasic.PowerPacks.Shape> class that defines their shared properties, methods, and events.</span></span>  
  
 <span data-ttu-id="a59da-121">Následující obrázek znázorňuje hierarchie objektů Line a Shape.</span><span class="sxs-lookup"><span data-stu-id="a59da-121">The following illustration shows the Line and Shape object hierarchy.</span></span>  
  
 <span data-ttu-id="a59da-122">![Diagram hierarchie objektů Line a Shape](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")</span><span class="sxs-lookup"><span data-stu-id="a59da-122">![A diagram of the Line and Shape object hierarchy](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")</span></span>  
<span data-ttu-id="a59da-123">Line a Shape hierarchie objektů</span><span class="sxs-lookup"><span data-stu-id="a59da-123">Line and Shape object hierarchy</span></span>  
  
 <span data-ttu-id="a59da-124">Odvozené <xref:Microsoft.VisualBasic.PowerPacks.LineShape> třída obsahuje vlastnosti, metod a události, které jsou jedinečné pro řádky.</span><span class="sxs-lookup"><span data-stu-id="a59da-124">The derived <xref:Microsoft.VisualBasic.PowerPacks.LineShape> class contains properties, methods, and events that are unique to lines.</span></span> <span data-ttu-id="a59da-125">Odvozené <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> třída je základní třídu pro <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> a <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; obsahuje vlastnosti, metod a události, které jsou společné pro všechny obrazce.</span><span class="sxs-lookup"><span data-stu-id="a59da-125">The derived <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> class is the base class for <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> and <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; it contains properties, methods, and events common to all shapes.</span></span> <span data-ttu-id="a59da-126">Můžete také odvodit z <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> a vytvořte vlastní `Shape` ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="a59da-126">You can also derive from <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> to create your own `Shape` controls.</span></span>  
  
 <span data-ttu-id="a59da-127"><xref:Microsoft.VisualBasic.PowerPacks.OvalShape> a <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> třídy lze použít k vykreslení kružnice, elips, obdélníků a obdélníky s zaoblenými hranami.</span><span class="sxs-lookup"><span data-stu-id="a59da-127">The <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> and <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> classes can be used to draw circles, ovals, rectangles, and rectangles with rounded corners.</span></span>  
  
 <span data-ttu-id="a59da-128">Po přidání ovládacího prvku řádku nebo tvaru do formuláře nebo kontejner, skrytý <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> je vytvořen objekt.</span><span class="sxs-lookup"><span data-stu-id="a59da-128">When a Line or Shape control is added to a form or container, an invisible <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> object is created.</span></span> <span data-ttu-id="a59da-129"><xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> Jednání jako plátno pro obrazce v rámci každé ovládacího prvku kontejneru; každá <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> má odpovídající <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> , můžete k iteraci v rámci Line a Shape – ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="a59da-129">The <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> acts as a canvas for the shapes within each container control; each <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> has a corresponding <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> that enables you to iterate through the Line and Shape controls.</span></span> <span data-ttu-id="a59da-130">Obrazce můžete přesunout z jednoho kontejneru na jiný pomocí vyjímání a vkládání nebo přetahování a vkládání.</span><span class="sxs-lookup"><span data-stu-id="a59da-130">You can move shapes from one container to another by using cut and paste or by dragging and dropping.</span></span> <span data-ttu-id="a59da-131">Když je poslední obrazec odebrán z kontejneru, <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> je také odebrána.</span><span class="sxs-lookup"><span data-stu-id="a59da-131">When the last shape is removed from a container, the <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> is removed also.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a59da-132">Ne všechny ovládací prvky kontejneru podporovat Line a Shape – ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="a59da-132">Not all container controls support the Line and Shape controls.</span></span> <span data-ttu-id="a59da-133">Nelze hostování ovládacího prvku řádku nebo tvaru na <xref:System.Windows.Forms.TableLayoutPanel> nebo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="a59da-133">You cannot host a Line or Shape control on a <xref:System.Windows.Forms.TableLayoutPanel> or a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a59da-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="a59da-134">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks>  
 [<span data-ttu-id="a59da-135">Postupy: kreslení čar pomocí ovládacího prvku LineShape</span><span class="sxs-lookup"><span data-stu-id="a59da-135">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [<span data-ttu-id="a59da-136">Postupy: kreslení obrazců pomocí OvalShape a RectangleShape</span><span class="sxs-lookup"><span data-stu-id="a59da-136">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [<span data-ttu-id="a59da-137">Postupy: povolení přecházení mezi tvary pomocí tabulátoru</span><span class="sxs-lookup"><span data-stu-id="a59da-137">How to: Enable Tabbing Between Shapes</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)