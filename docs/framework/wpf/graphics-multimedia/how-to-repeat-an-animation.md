---
title: "Postupy: Opakování animace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d2f942771e01c2b7fae989f73779672edb8ba2f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="1d95e-102">Postupy: Opakování animace</span><span class="sxs-lookup"><span data-stu-id="1d95e-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="1d95e-103">Tento příklad ukazuje způsob použití <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> vlastnost <xref:System.Windows.Media.Animation.Timeline> aby bylo možné řídit chování opakování animace.</span><span class="sxs-lookup"><span data-stu-id="1d95e-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d95e-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="1d95e-104">Example</span></span>  
 <span data-ttu-id="1d95e-105"><xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Vlastnost <xref:System.Windows.Media.Animation.Timeline> Určuje, kolikrát opakuje jeho jednoduché trvání animace.</span><span class="sxs-lookup"><span data-stu-id="1d95e-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="1d95e-106">Pomocí <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, můžete určit, že <xref:System.Windows.Media.Animation.Timeline> opakuje pro stanovený počet (počet iterací) nebo pro zadané časové období.</span><span class="sxs-lookup"><span data-stu-id="1d95e-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="1d95e-107">V obou případech animace projde tolik spustí začátku do konce, které je nutné, aby vyplnil celou dobu trvání na požadovaný počet.</span><span class="sxs-lookup"><span data-stu-id="1d95e-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="1d95e-108">Ve výchozím nastavení mají časové osy počet opakování 1.0, což znamená, že přehrání jednou a neopakuje.</span><span class="sxs-lookup"><span data-stu-id="1d95e-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="1d95e-109">Ale pokud nastavíte <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> vlastnost <xref:System.Windows.Media.Animation.Timeline> k <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, časovou osu opakuje bez omezení.</span><span class="sxs-lookup"><span data-stu-id="1d95e-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="1d95e-110">Následující příklad ukazuje způsob použití <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> vlastnost pro řízení chování opakování animace.</span><span class="sxs-lookup"><span data-stu-id="1d95e-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="1d95e-111">V příkladu animuje <xref:System.Windows.FrameworkElement.Width%2A> vlastnost pět obdélníků se každý rámeček pomocí jiného typu opakování chování.</span><span class="sxs-lookup"><span data-stu-id="1d95e-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="1d95e-112">Kompletní příklad, najdete v části [ukázka chování časování animace](http://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="1d95e-112">For the complete sample, see [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d95e-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="1d95e-113">See Also</span></span>  
 [<span data-ttu-id="1d95e-114">Při opakovaném cykly hromadit hodnoty animace</span><span class="sxs-lookup"><span data-stu-id="1d95e-114">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="1d95e-115">Zadejte, zda automaticky obrátí časové osy</span><span class="sxs-lookup"><span data-stu-id="1d95e-115">Specify Whether a Timeline Automatically Reverses</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [<span data-ttu-id="1d95e-116">Postupy: témata</span><span class="sxs-lookup"><span data-stu-id="1d95e-116">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [<span data-ttu-id="1d95e-117">Animace a časování</span><span class="sxs-lookup"><span data-stu-id="1d95e-117">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="1d95e-118">Animace – přehled</span><span class="sxs-lookup"><span data-stu-id="1d95e-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="1d95e-119">Ukázka chování časování animace</span><span class="sxs-lookup"><span data-stu-id="1d95e-119">Animation Timing Behavior Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159970)