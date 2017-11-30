---
title: "Oblasti v rozhraní GDI+"
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
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0525e7b58353909d41e5367aa52a17aa56bcd77c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="regions-in-gdi"></a><span data-ttu-id="729e5-102">Oblasti v rozhraní GDI+</span><span class="sxs-lookup"><span data-stu-id="729e5-102">Regions in GDI+</span></span>
<span data-ttu-id="729e5-103">Oblast je část v oblasti výstupní zařízení.</span><span class="sxs-lookup"><span data-stu-id="729e5-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="729e5-104">Oblasti může být jednoduchý (jeden rámeček) nebo komplexní (kombinaci mnohoúhelníky a uzavřené křivky).</span><span class="sxs-lookup"><span data-stu-id="729e5-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="729e5-105">Následující obrázek znázorňuje dvou oblastí: jeden zkonstruován z obdélníku a dalších vytvořený z cesty.</span><span class="sxs-lookup"><span data-stu-id="729e5-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="729e5-106">![Oblasti](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="729e5-106">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="729e5-107">Použití oblastí</span><span class="sxs-lookup"><span data-stu-id="729e5-107">Using Regions</span></span>  
 <span data-ttu-id="729e5-108">Oblasti se často používají pro výstřižek a testování průchodu.</span><span class="sxs-lookup"><span data-stu-id="729e5-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="729e5-109">Výstřižek zahrnuje omezení kreslení v určité oblasti zobrazované oblasti, obvykle část, kterou je třeba aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="729e5-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="729e5-110">Testování přístupů zahrnuje kontroly k určení, zda kurzor se nachází v určité oblasti obrazovky při stisknutí tlačítka myši.</span><span class="sxs-lookup"><span data-stu-id="729e5-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="729e5-111">Můžete vytvořit oblasti, obdélníku nebo cestu.</span><span class="sxs-lookup"><span data-stu-id="729e5-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="729e5-112">Můžete také vytvořit komplexní oblasti kombinací existující oblasti.</span><span class="sxs-lookup"><span data-stu-id="729e5-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="729e5-113"><xref:System.Drawing.Region> Třída poskytuje následující metody pro kombinování oblastí: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, a <xref:System.Drawing.Region.Complement%2A>.</span><span class="sxs-lookup"><span data-stu-id="729e5-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="729e5-114">Průnik dvou oblastí je sada všech bodů, které patří do obou oblastí.</span><span class="sxs-lookup"><span data-stu-id="729e5-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="729e5-115">Sjednocení je sada všech bodů patřící do jeden nebo druhý nebo obou oblastí.</span><span class="sxs-lookup"><span data-stu-id="729e5-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="729e5-116">Doplňkovým oblasti je sada všech bodů, které nejsou v oblasti.</span><span class="sxs-lookup"><span data-stu-id="729e5-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="729e5-117">Následující obrázek znázorňuje průsečíkem a sjednocení dvou oblastí vidět na předchozím obrázku.</span><span class="sxs-lookup"><span data-stu-id="729e5-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="729e5-118">![Oblasti](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="729e5-118">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="729e5-119"><xref:System.Drawing.Region.Xor%2A> Metoda, použije na pár oblastí, vytváří oblasti, která obsahuje všechny body, které patří do jedné oblasti nebo dalších, ale ne obojí.</span><span class="sxs-lookup"><span data-stu-id="729e5-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="729e5-120"><xref:System.Drawing.Region.Exclude%2A> Metoda, použije na pár oblastí, vytváří oblasti, která obsahuje všechny body v první oblasti, které nejsou v druhé oblasti.</span><span class="sxs-lookup"><span data-stu-id="729e5-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="729e5-121">Následující obrázek znázorňuje oblastí, které vyplývají z <xref:System.Drawing.Region.Xor%2A> a <xref:System.Drawing.Region.Exclude%2A> metody dvou oblastí zobrazí na začátku tohoto tématu.</span><span class="sxs-lookup"><span data-stu-id="729e5-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="729e5-122">![Oblasti](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="729e5-122">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="729e5-123">K vyplnění oblasti, budete potřebovat <xref:System.Drawing.Graphics> objekt, <xref:System.Drawing.Brush> objekt a <xref:System.Drawing.Region> objektu.</span><span class="sxs-lookup"><span data-stu-id="729e5-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="729e5-124"><xref:System.Drawing.Graphics> Objekt poskytuje <xref:System.Drawing.Graphics.FillRegion%2A> metody a <xref:System.Drawing.Brush> objekt uloží atributy výplně, jako je například barvu nebo vzorek.</span><span class="sxs-lookup"><span data-stu-id="729e5-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="729e5-125">Následující příklad doplní oblast plnou barvou.</span><span class="sxs-lookup"><span data-stu-id="729e5-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="729e5-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="729e5-126">See Also</span></span>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="729e5-127">Čar, křivek a obrazců</span><span class="sxs-lookup"><span data-stu-id="729e5-127">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="729e5-128">Použití oblastí</span><span class="sxs-lookup"><span data-stu-id="729e5-128">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)