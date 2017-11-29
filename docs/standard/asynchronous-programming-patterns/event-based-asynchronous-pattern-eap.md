---
title: "Asynchronní vzor založený na událostech (EAP)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b5f242b9586c4ea3b045daf8f10b84127b81085
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="eeb84-102">Asynchronní vzor založený na událostech (EAP)</span><span class="sxs-lookup"><span data-stu-id="eeb84-102">Event-based Asynchronous Pattern (EAP)</span></span>
<span data-ttu-id="eeb84-103">Existuje několik způsobů, jak vystavit asynchronní funkce kódu klienta.</span><span class="sxs-lookup"><span data-stu-id="eeb84-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="eeb84-104">Asynchronní vzor založený na událostech stanovuje jedním ze způsobů pro třídy nabídne asynchronní chování.</span><span class="sxs-lookup"><span data-stu-id="eeb84-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eeb84-105">Od verze [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Task Parallel Library poskytuje nový model pro asynchronní a paralelní programování.</span><span class="sxs-lookup"><span data-stu-id="eeb84-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="eeb84-106">Další informace najdete v tématu [paralelní programování](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="eeb84-106">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eeb84-107">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="eeb84-107">In This Section</span></span>  
 [<span data-ttu-id="eeb84-108">Přehled asynchronních vzorů založených na událostech</span><span class="sxs-lookup"><span data-stu-id="eeb84-108">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="eeb84-109">Popisuje, jak asynchronní vzor založený na událostech zpřístupní výhod vícevláknové aplikace při skrytí mnoho složitých problémů vyplývajících z více vláken návrhu.</span><span class="sxs-lookup"><span data-stu-id="eeb84-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="eeb84-110">Implementace asynchronního vzoru založeného na událostech</span><span class="sxs-lookup"><span data-stu-id="eeb84-110">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="eeb84-111">Popisuje standardizovaného způsobu balíček třídy, která má asynchronní funkce.</span><span class="sxs-lookup"><span data-stu-id="eeb84-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="eeb84-112">Osvědčené postupy pro implementaci asynchronního vzoru založeného na událostech</span><span class="sxs-lookup"><span data-stu-id="eeb84-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="eeb84-113">Popisuje požadavky na vystavení asynchronní funkce podle asynchronní vzor založený na událostech.</span><span class="sxs-lookup"><span data-stu-id="eeb84-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="eeb84-114">Rozhodování, kdy implementovat asynchronní vzor založený na událostech</span><span class="sxs-lookup"><span data-stu-id="eeb84-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="eeb84-115">Popisuje, jak určit, kdy by měl vybrat implementovat asynchronní vzor místo na základě událostí <xref:System.IAsyncResult> vzor.</span><span class="sxs-lookup"><span data-stu-id="eeb84-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="eeb84-116">Návod: Implementace komponenty, která podporuje asynchronní vzor založený na událostech</span><span class="sxs-lookup"><span data-stu-id="eeb84-116">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="eeb84-117">Ukazuje, jak vytvořit komponentu, která implementuje asynchronní vzor založený na událostech.</span><span class="sxs-lookup"><span data-stu-id="eeb84-117">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="eeb84-118">Je implementována pomocí pomocné třídy z <xref:System.ComponentModel?displayProperty=nameWithType> obor názvů, které zajišťuje, že součást funguje správně v rámci modelu všechny aplikace.</span><span class="sxs-lookup"><span data-stu-id="eeb84-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="eeb84-119">Postupy: použití komponent, které podporují asynchronní vzor založený na událostech</span><span class="sxs-lookup"><span data-stu-id="eeb84-119">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="eeb84-120">Popisuje způsob použití komponenty, která podporuje asynchronní vzor založený na událostech.</span><span class="sxs-lookup"><span data-stu-id="eeb84-120">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eeb84-121">Odkaz</span><span class="sxs-lookup"><span data-stu-id="eeb84-121">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="eeb84-122">Popisuje <xref:System.ComponentModel.AsyncOperation> třídy a obsahuje odkazy na všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="eeb84-122">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="eeb84-123">Popisuje <xref:System.ComponentModel.AsyncOperationManager> třídy a obsahuje odkazy na všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="eeb84-123">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="eeb84-124">Popisuje <xref:System.ComponentModel.BackgroundWorker> součásti a obsahuje odkazy na všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="eeb84-124">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eeb84-125">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="eeb84-125">Related Sections</span></span>  
 [<span data-ttu-id="eeb84-126">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="eeb84-126">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="eeb84-127">Popisuje programovací model pro paralelní a asynchronní operace.</span><span class="sxs-lookup"><span data-stu-id="eeb84-127">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="eeb84-128">Dělení na vlákna</span><span class="sxs-lookup"><span data-stu-id="eeb84-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="eeb84-129">Popisuje multithreading funkce v rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eeb84-129">Describes multithreading features in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="eeb84-130">Dělení na vlákna</span><span class="sxs-lookup"><span data-stu-id="eeb84-130">Threading</span></span>](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 <span data-ttu-id="eeb84-131">Popisuje funkce více vláken v jazycích C# a Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="eeb84-131">Describes multithreading features in the C# and Visual Basic languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb84-132">Viz také</span><span class="sxs-lookup"><span data-stu-id="eeb84-132">See Also</span></span>  
 [<span data-ttu-id="eeb84-133">Dělení na spravovaná vlákna osvědčené postupy</span><span class="sxs-lookup"><span data-stu-id="eeb84-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="eeb84-134">Události</span><span class="sxs-lookup"><span data-stu-id="eeb84-134">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="eeb84-135">Více vláken v součásti</span><span class="sxs-lookup"><span data-stu-id="eeb84-135">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="eeb84-136">Asynchronní vzory návrhu programování</span><span class="sxs-lookup"><span data-stu-id="eeb84-136">Asynchronous Programming Design Patterns</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)