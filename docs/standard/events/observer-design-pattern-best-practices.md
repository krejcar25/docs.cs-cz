---
title: "Doporučené postupy pro návrhový vzor Pozorovatel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- observer design pattern [.NET Framework], best practices
- best practices [.NET Framework], observer design pattern
ms.assetid: c834760f-ddd4-417f-abb7-a059679d5b8c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0edba44efcaa46812f535b39364c2f5e4e3a1afe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="observer-design-pattern-best-practices"></a><span data-ttu-id="bf200-102">Doporučené postupy pro návrhový vzor Pozorovatel</span><span class="sxs-lookup"><span data-stu-id="bf200-102">Observer Design Pattern Best Practices</span></span>
<span data-ttu-id="bf200-103">Návrhový vzor pozorovatel je v rozhraní .NET Framework, implementované jako sada rozhraní.</span><span class="sxs-lookup"><span data-stu-id="bf200-103">In the .NET Framework, the observer design pattern is implemented as a set of interfaces.</span></span> <span data-ttu-id="bf200-104"><xref:System.IObservable%601?displayProperty=nameWithType> Rozhraní představuje poskytovatele dat, který je také zajišťuje <xref:System.IDisposable> implementace, která umožňuje pozorovatelů zrušit odběr oznámení.</span><span class="sxs-lookup"><span data-stu-id="bf200-104">The <xref:System.IObservable%601?displayProperty=nameWithType> interface represents the data provider, which is also responsible for providing an <xref:System.IDisposable> implementation that lets observers unsubscribe from notifications.</span></span> <span data-ttu-id="bf200-105"><xref:System.IObserver%601?displayProperty=nameWithType> Rozhraní představuje pozorovatele.</span><span class="sxs-lookup"><span data-stu-id="bf200-105">The <xref:System.IObserver%601?displayProperty=nameWithType> interface represents the observer.</span></span> <span data-ttu-id="bf200-106">Toto téma popisuje osvědčené postupy, které vývojáři postupujte při implementaci návrhový vzor pozorovatel pomocí těchto rozhraní.</span><span class="sxs-lookup"><span data-stu-id="bf200-106">This topic describes the best practices that developers should follow when implementing the observer design pattern using these interfaces.</span></span>  
  
## <a name="threading"></a><span data-ttu-id="bf200-107">Dělení na vlákna</span><span class="sxs-lookup"><span data-stu-id="bf200-107">Threading</span></span>  
 <span data-ttu-id="bf200-108">Obvykle se implementuje poskytovatele <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> metoda přidáním konkrétní pozorovatel k seznamu odběratelů, která je reprezentována některé objektu kolekce a implementuje <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> metoda odebráním konkrétní pozorovatel ze seznamu odběratele.</span><span class="sxs-lookup"><span data-stu-id="bf200-108">Typically, a provider implements the <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method by adding a particular observer to a subscriber list that is represented by some collection object, and it implements the <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> method by removing a particular observer from the subscriber list.</span></span> <span data-ttu-id="bf200-109">Pozorovatel můžete kdykoli volání těchto metod.</span><span class="sxs-lookup"><span data-stu-id="bf200-109">An observer can call these methods at any time.</span></span> <span data-ttu-id="bf200-110">Kromě toho, protože kontrakt poskytovatele/pozorovatel neurčuje který zodpovídá za po odhlášení musí být <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> metoda zpětného volání, zprostředkovatele a pozorovatel obě pokusit stejného člena odebrat ze seznamu.</span><span class="sxs-lookup"><span data-stu-id="bf200-110">In addition, because the provider/observer contract does not specify who is responsible for unsubscribing after the <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> callback method, the provider and observer may both try to remove the same member from the list.</span></span> <span data-ttu-id="bf200-111">Z důvodu této možnosti jak <xref:System.IObservable%601.Subscribe%2A> a <xref:System.IDisposable.Dispose%2A> metody by měly být bezpečné pro přístup z více vláken.</span><span class="sxs-lookup"><span data-stu-id="bf200-111">Because of this possibility, both the <xref:System.IObservable%601.Subscribe%2A> and <xref:System.IDisposable.Dispose%2A> methods should be thread-safe.</span></span> <span data-ttu-id="bf200-112">Obvykle to zahrnuje použití [souběžných kolekce](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md) nebo zámek.</span><span class="sxs-lookup"><span data-stu-id="bf200-112">Typically, this involves using a [concurrent collection](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md) or a lock.</span></span> <span data-ttu-id="bf200-113">Implementace, které nejsou bezpečné pro přístup z více vláken musí explicitně dokumentů, které nejsou.</span><span class="sxs-lookup"><span data-stu-id="bf200-113">Implementations that are not thread-safe should explicitly document that they are not.</span></span>  
  
 <span data-ttu-id="bf200-114">Žádné další záruky nutné zadávat ve vrstvě nad poskytovatele/pozorovatel kontrakt.</span><span class="sxs-lookup"><span data-stu-id="bf200-114">Any additional guarantees have to be specified in a layer on top of the provider/observer contract.</span></span> <span data-ttu-id="bf200-115">Implementátory by měly volat jasně, když ukládají další požadavky, aby nedocházelo k záměně uživatele o smlouvě pozorovatel.</span><span class="sxs-lookup"><span data-stu-id="bf200-115">Implementers should clearly call out when they impose additional requirements to avoid user confusion about the observer contract.</span></span>  
  
## <a name="handling-exceptions"></a><span data-ttu-id="bf200-116">Zpracování výjimek</span><span class="sxs-lookup"><span data-stu-id="bf200-116">Handling Exceptions</span></span>  
 <span data-ttu-id="bf200-117">Z důvodu volné párování mezi zprostředkovatele dat a pozorovatele výjimky v návrhovém vzoru pozorovatel měla být informační.</span><span class="sxs-lookup"><span data-stu-id="bf200-117">Because of the loose coupling between a data provider and an observer, exceptions in the observer design pattern are intended to be informational.</span></span> <span data-ttu-id="bf200-118">To má vliv jak zprostředkovatelé a pozorovatelů zpracování výjimek v návrhovém vzoru pozorovatel.</span><span class="sxs-lookup"><span data-stu-id="bf200-118">This affects how providers and observers handle exceptions in the observer design pattern.</span></span>  
  
### <a name="the-provider----calling-the-onerror-method"></a><span data-ttu-id="bf200-119">Poskytovatel--Volání OnError – metoda</span><span class="sxs-lookup"><span data-stu-id="bf200-119">The Provider -- Calling the OnError Method</span></span>  
 <span data-ttu-id="bf200-120"><xref:System.IObserver%601.OnError%2A> Metoda je určena jako informační zpráva k pozorovatelů, podobně jako <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="bf200-120">The <xref:System.IObserver%601.OnError%2A> method is intended as an informational message to observers, much like the <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bf200-121">Ale <xref:System.IObserver%601.OnNext%2A> metoda je určená k poskytnutí pozorovatele s aktuální nebo aktualizovaná data, zatímco <xref:System.IObserver%601.OnError%2A> metoda slouží k označení, že je zprostředkovatel nepodařilo poskytnout platná data.</span><span class="sxs-lookup"><span data-stu-id="bf200-121">However, the <xref:System.IObserver%601.OnNext%2A> method is designed to provide an observer with current or updated data, whereas the <xref:System.IObserver%601.OnError%2A> method is designed to indicate that the provider is unable to provide valid data.</span></span>  
  
 <span data-ttu-id="bf200-122">Zprostředkovatel postupujte tyto osvědčené postupy při zpracování výjimek a volání <xref:System.IObserver%601.OnError%2A> metoda:</span><span class="sxs-lookup"><span data-stu-id="bf200-122">The provider should follow these best practices when handling exceptions and calling the <xref:System.IObserver%601.OnError%2A> method:</span></span>  
  
-   <span data-ttu-id="bf200-123">Zprostředkovatel musí zpracovávat své vlastní výjimky, pokud má žádné zvláštní požadavky.</span><span class="sxs-lookup"><span data-stu-id="bf200-123">The provider must handle its own exceptions if it has any specific requirements.</span></span>  
  
-   <span data-ttu-id="bf200-124">Zprostředkovatel by neměl očekávat nebo vyžadovat, aby pozorovatelů zpracování výjimek žádným způsobem konkrétní.</span><span class="sxs-lookup"><span data-stu-id="bf200-124">The provider should not expect or require that observers handle exceptions in any particular way.</span></span>  
  
-   <span data-ttu-id="bf200-125">Zprostředkovatel by měly volat <xref:System.IObserver%601.OnError%2A> metoda při zpracování výjimka, která ohrožuje jeho schopnost poskytovat aktualizace.</span><span class="sxs-lookup"><span data-stu-id="bf200-125">The provider should call the <xref:System.IObserver%601.OnError%2A> method when it handles an exception that compromises its ability to provide updates.</span></span> <span data-ttu-id="bf200-126">Informace o takové výjimky mohou být předána do pozorovatel.</span><span class="sxs-lookup"><span data-stu-id="bf200-126">Information on such exceptions can be passed to the observer.</span></span> <span data-ttu-id="bf200-127">V ostatních případech je třeba oznamovat pozorovatelů výjimku.</span><span class="sxs-lookup"><span data-stu-id="bf200-127">In other cases, there is no need to notify observers of an exception.</span></span>  
  
 <span data-ttu-id="bf200-128">Po volání zprostředkovatele <xref:System.IObserver%601.OnError%2A> nebo <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> metoda, měla by existovat žádná další oznámení a zprostředkovatele můžete zrušit jeho pozorovatelů.</span><span class="sxs-lookup"><span data-stu-id="bf200-128">Once the provider calls the <xref:System.IObserver%601.OnError%2A> or <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> method, there should be no further notifications, and the provider can unsubscribe its observers.</span></span> <span data-ttu-id="bf200-129">Však pozorovatelů můžete taky kdykoli sami, včetně i před a po přijetí <xref:System.IObserver%601.OnError%2A> nebo <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> oznámení.</span><span class="sxs-lookup"><span data-stu-id="bf200-129">However, the observers can also unsubscribe themselves at any time, including both before and after they receive an <xref:System.IObserver%601.OnError%2A> or <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> notification.</span></span> <span data-ttu-id="bf200-130">Návrhový vzor pozorovatel není určují, zda zprostředkovatel nebo pozorovatel je zodpovědná za odhlášením; Proto je možné, že oba pokusit k odhlášení odběru.</span><span class="sxs-lookup"><span data-stu-id="bf200-130">The observer design pattern does not dictate whether the provider or the observer is responsible for unsubscribing; therefore, there is a possibility that both may attempt to unsubscribe.</span></span> <span data-ttu-id="bf200-131">Obvykle když pozorovatelů odhlásit, jsou odebrány z kolekce odběratele.</span><span class="sxs-lookup"><span data-stu-id="bf200-131">Typically, when observers unsubscribe, they are removed from a subscribers collection.</span></span> <span data-ttu-id="bf200-132">V aplikaci jednovláknové <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementace se ujistěte, že je odkaz na objekt platný a že objekt je členem kolekce odběratele před pokusem o jeho odebrání.</span><span class="sxs-lookup"><span data-stu-id="bf200-132">In a single-threaded application, the <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation should ensure that an object reference is valid and that the object is a member of the subscribers collection before attempting to remove it.</span></span> <span data-ttu-id="bf200-133">V aplikaci s více vlákny, kolekce bezpečné pro přístup z více vláken objektu, například <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> objektu, by měla být použita.</span><span class="sxs-lookup"><span data-stu-id="bf200-133">In a multithreaded application, a thread-safe collection object, such as a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> object, should be used.</span></span>  
  
### <a name="the-observer----implementing-the-onerror-method"></a><span data-ttu-id="bf200-134">Pozorovatel – Implementace OnError – metoda</span><span class="sxs-lookup"><span data-stu-id="bf200-134">The Observer -- Implementing the OnError Method</span></span>  
 <span data-ttu-id="bf200-135">Když pozorovatele obdrží oznámení o chybě od poskytovatele, pozorovatel měli považovat za výjimku informační a neměli nutné provádět žádnou zvláštní akci.</span><span class="sxs-lookup"><span data-stu-id="bf200-135">When an observer receives an error notification from a provider, the observer should treat the exception as informational and should not be required to take any particular action.</span></span>  
  
 <span data-ttu-id="bf200-136">Pozorovatel postupujte při odpovědi na tyto osvědčené postupy <xref:System.IObserver%601.OnError%2A> volání metody od zprostředkovatele:</span><span class="sxs-lookup"><span data-stu-id="bf200-136">The observer should follow these best practices when responding to an <xref:System.IObserver%601.OnError%2A> method call from a provider:</span></span>  
  
-   <span data-ttu-id="bf200-137">Pozorovatel nesmí vyvolat výjimky z jeho implementace rozhraní, jako <xref:System.IObserver%601.OnNext%2A> nebo <xref:System.IObserver%601.OnError%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf200-137">The observer should not throw exceptions from its interface implementations, such as <xref:System.IObserver%601.OnNext%2A> or <xref:System.IObserver%601.OnError%2A>.</span></span> <span data-ttu-id="bf200-138">Ale pokud pozorovatel generování výjimek, by měl očekávat tyto přejděte neošetřené výjimky.</span><span class="sxs-lookup"><span data-stu-id="bf200-138">However, if the observer does throw exceptions, it should expect these exceptions to go unhandled.</span></span>  
  
-   <span data-ttu-id="bf200-139">Pro zachování zásobníku volání, pozorovatele, který chce throw <xref:System.Exception> objekt, který byl předán jeho <xref:System.IObserver%601.OnError%2A> metoda má obtékat výjimka před vyvoláním ho.</span><span class="sxs-lookup"><span data-stu-id="bf200-139">To preserve the call stack, an observer that wishes to throw an <xref:System.Exception> object that was passed to its <xref:System.IObserver%601.OnError%2A> method should wrap the exception before throwing it.</span></span> <span data-ttu-id="bf200-140">Objekt standardní výjimky by měla použít pro tento účel.</span><span class="sxs-lookup"><span data-stu-id="bf200-140">A standard exception object should be used for this purpose.</span></span>  
  
## <a name="additional-best-practices"></a><span data-ttu-id="bf200-141">Další doporučené postupy</span><span class="sxs-lookup"><span data-stu-id="bf200-141">Additional Best Practices</span></span>  
 <span data-ttu-id="bf200-142">Probíhá pokus o zrušení registrace v <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> metoda může mít za následek odkaz s hodnotou null.</span><span class="sxs-lookup"><span data-stu-id="bf200-142">Attempting to unregister in the <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method may result in a null reference.</span></span> <span data-ttu-id="bf200-143">Proto doporučujeme, abyste tento postup.</span><span class="sxs-lookup"><span data-stu-id="bf200-143">Therefore, we recommend that you avoid this practice.</span></span>  
  
 <span data-ttu-id="bf200-144">Přestože je možné připojit k více poskytovatelů pozorovatele, doporučené vzor je pro připojení <xref:System.IObserver%601> instance, která má jenom jeden <xref:System.IObservable%601> instance.</span><span class="sxs-lookup"><span data-stu-id="bf200-144">Although it is possible to attach an observer to multiple providers, the recommended pattern is to attach an <xref:System.IObserver%601> instance to only one <xref:System.IObservable%601> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf200-145">Viz také</span><span class="sxs-lookup"><span data-stu-id="bf200-145">See Also</span></span>  
 [<span data-ttu-id="bf200-146">Návrhový vzor pozorovatel</span><span class="sxs-lookup"><span data-stu-id="bf200-146">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="bf200-147">Postupy: implementace pozorovatele</span><span class="sxs-lookup"><span data-stu-id="bf200-147">How to: Implement an Observer</span></span>](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [<span data-ttu-id="bf200-148">Postupy: implementace poskytovatele</span><span class="sxs-lookup"><span data-stu-id="bf200-148">How to: Implement a Provider</span></span>](../../../docs/standard/events/how-to-implement-a-provider.md)