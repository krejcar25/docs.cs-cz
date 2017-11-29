---
title: "Postupy: Zpracování více událostí pomocí vlastností událostí"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET Framework]
- multiple events [.NET Framework]
- event handling [.NET Framework], with multiple events
- events [.NET Framework], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c16918e715a93de8fdf164e75ce7be81511b71b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="687ac-102">Postupy: Zpracování více událostí pomocí vlastností událostí</span><span class="sxs-lookup"><span data-stu-id="687ac-102">How to: Handle Multiple Events Using Event Properties</span></span>
<span data-ttu-id="687ac-103">Chcete-li použít vlastnosti událostí, je třeba definovat vlastnosti událostí ve třídě, která události vyvolá, a poté nastavit delegáty pro tyto vlastnosti událostí ve třídách, které události zpracovávají.</span><span class="sxs-lookup"><span data-stu-id="687ac-103">To use event properties, you define the event properties in the class that raises the events, and then set the delegates for the event properties in classes that handle the events.</span></span> <span data-ttu-id="687ac-104">Pokud chcete implementovat několik vlastností události ve třídě, musí třída interně ukládat a udržovat delegáta definovaného pro každou jednotlivou událost.</span><span class="sxs-lookup"><span data-stu-id="687ac-104">To implement multiple event properties in a class, the class must internally store and maintain the delegate defined for each event.</span></span> <span data-ttu-id="687ac-105">Typickým přístupem je implementace delegáta kolekce, která je indexovat pomocí klíče události.</span><span class="sxs-lookup"><span data-stu-id="687ac-105">A typical approach is to implement a delegate collection that is indexed by an event key.</span></span>  
  
 <span data-ttu-id="687ac-106">Chcete-li uložit delegáty pro každou jednotlivou událost, můžete použít <xref:System.ComponentModel.EventHandlerList> třídy, nebo jsou implementovány vlastní kolekce.</span><span class="sxs-lookup"><span data-stu-id="687ac-106">To store the delegates for each event, you can use the <xref:System.ComponentModel.EventHandlerList> class, or implement your own collection.</span></span> <span data-ttu-id="687ac-107">Třída kolekce musí poskytovat metody pro nastavení, přístup a načítání delegát obslužná rutina události na základě klíče události.</span><span class="sxs-lookup"><span data-stu-id="687ac-107">The collection class must provide methods for setting, accessing, and retrieving the event handler delegate based on the event key.</span></span> <span data-ttu-id="687ac-108">Například můžete použít <xref:System.Collections.Hashtable> třídy nebo odvodit vlastní třídu z <xref:System.Collections.DictionaryBase> třídy.</span><span class="sxs-lookup"><span data-stu-id="687ac-108">For example, you could use a <xref:System.Collections.Hashtable> class, or derive a custom class from the <xref:System.Collections.DictionaryBase> class.</span></span> <span data-ttu-id="687ac-109">Podrobnosti implementace kolekce delegáta nemusíte být nezveřejní třídě.</span><span class="sxs-lookup"><span data-stu-id="687ac-109">The implementation details of the delegate collection do not need to be exposed outside your class.</span></span>  
  
 <span data-ttu-id="687ac-110">Každá vlastnost události v rámci třídy definuje přístupovou metodu přidat a odebrat metodu přistupujícího objektu.</span><span class="sxs-lookup"><span data-stu-id="687ac-110">Each event property within the class defines an add accessor method and a remove accessor method.</span></span> <span data-ttu-id="687ac-111">Přidat přistupující objekt vlastnosti události přidá do kolekce delegáta instanci vstupního delegáta.</span><span class="sxs-lookup"><span data-stu-id="687ac-111">The add accessor for an event property adds the input delegate instance to the delegate collection.</span></span> <span data-ttu-id="687ac-112">Odebrat přistupující objekt vlastnosti události odebere instanci vstupního delegáta z kolekce delegáta.</span><span class="sxs-lookup"><span data-stu-id="687ac-112">The remove accessor for an event property removes the input delegate instance from the delegate collection.</span></span> <span data-ttu-id="687ac-113">Přístupové objekty událostí vlastnosti pomocí předdefinované klíče vlastnosti události k přidání a odebrání instance z kolekce delegáta.</span><span class="sxs-lookup"><span data-stu-id="687ac-113">The event property accessors use the predefined key for the event property to add and remove instances from the delegate collection.</span></span>  
  
### <a name="to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="687ac-114">Pro zpracování více událostí pomocí vlastností událostí</span><span class="sxs-lookup"><span data-stu-id="687ac-114">To handle multiple events using event properties</span></span>  
  
1.  <span data-ttu-id="687ac-115">Definujte kolekci delegátů v rámci třídy, která vyvolává události.</span><span class="sxs-lookup"><span data-stu-id="687ac-115">Define a delegate collection within the class that raises the events.</span></span>  
  
2.  <span data-ttu-id="687ac-116">Definujte klíč pro každou jednotlivou událost.</span><span class="sxs-lookup"><span data-stu-id="687ac-116">Define a key for each event.</span></span>  
  
3.  <span data-ttu-id="687ac-117">Definujte vlastnosti události ve třídě, která vyvolává události.</span><span class="sxs-lookup"><span data-stu-id="687ac-117">Define the event properties in the class that raises the events.</span></span>  
  
4.  <span data-ttu-id="687ac-118">Použití delegáta kolekce k implementaci přidat a odebrat přístupových metod vlastností události.</span><span class="sxs-lookup"><span data-stu-id="687ac-118">Use the delegate collection to implement the add and remove accessor methods for the event properties.</span></span>  
  
5.  <span data-ttu-id="687ac-119">Veřejné vlastnosti události použijte k přidání a odebrání delegátů obslužných rutin událostí v třídách, které zpracovávají události.</span><span class="sxs-lookup"><span data-stu-id="687ac-119">Use the public event properties to add and remove event handler delegates in the classes that handle the events.</span></span>  
  
## <a name="example"></a><span data-ttu-id="687ac-120">Příklad</span><span class="sxs-lookup"><span data-stu-id="687ac-120">Example</span></span>  
 <span data-ttu-id="687ac-121">Následující příklad jazyka C# implementuje vlastnosti události `MouseDown` a `MouseUp`, použije <xref:System.ComponentModel.EventHandlerList> k uložení delegáta každé události.</span><span class="sxs-lookup"><span data-stu-id="687ac-121">The following C# example implements the event properties `MouseDown` and `MouseUp`, using an <xref:System.ComponentModel.EventHandlerList> to store each event's delegate.</span></span> <span data-ttu-id="687ac-122">Klíčová slova konstrukce vlastnosti události jsou tučně.</span><span class="sxs-lookup"><span data-stu-id="687ac-122">The keywords of the event property constructs are in bold type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="687ac-123">Vlastnosti události nejsou podporovány v [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="687ac-123">Event properties are not supported in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)].</span></span>  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="687ac-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="687ac-124">See Also</span></span>  
 <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>  
 [<span data-ttu-id="687ac-125">Události</span><span class="sxs-lookup"><span data-stu-id="687ac-125">Events</span></span>](../../../docs/standard/events/index.md)  
 <xref:System.Web.UI.Control.Events%2A>  
 [<span data-ttu-id="687ac-126">Postupy: deklarování vlastních událostí pro konzervaci paměti</span><span class="sxs-lookup"><span data-stu-id="687ac-126">How to: Declare Custom Events To Conserve Memory</span></span>](~/docs/visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)