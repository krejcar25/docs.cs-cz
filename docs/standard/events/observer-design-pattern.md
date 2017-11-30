---
title: "Návrhový vzor Pozorovatel"
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
helpviewer_keywords:
- IObserver(Of T) interface
- IObservable<T> interface
- IObserver<T> interface
- IObservable(Of T) interface
- observer design pattern [.NET Framework]
ms.assetid: 3680171f-f522-453c-aa4a-54f755a78f88
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 83663a28ac7ae19848552583f2ec39a5e96c7fdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="observer-design-pattern"></a><span data-ttu-id="edbdd-102">Návrhový vzor Pozorovatel</span><span class="sxs-lookup"><span data-stu-id="edbdd-102">Observer Design Pattern</span></span>
<span data-ttu-id="edbdd-103">Návrhový vzor pozorovatel umožňuje odběratele k registraci nebo dostávat oznámení od zprostředkovatele.</span><span class="sxs-lookup"><span data-stu-id="edbdd-103">The observer design pattern enables a subscriber to register with and receive notifications from a provider.</span></span> <span data-ttu-id="edbdd-104">Je vhodná pro každý scénář, který vyžaduje nabízená oznámení.</span><span class="sxs-lookup"><span data-stu-id="edbdd-104">It is suitable for any scenario that requires push-based notification.</span></span> <span data-ttu-id="edbdd-105">Definuje vzoru *zprostředkovatele* (také označované jako *subjektu* nebo *lze zobrazit*) a nula, jednu nebo více *pozorovatelů*.</span><span class="sxs-lookup"><span data-stu-id="edbdd-105">The pattern defines a *provider* (also known as a *subject* or an *observable*) and zero, one, or more *observers*.</span></span> <span data-ttu-id="edbdd-106">Pozorovatelů zaregistrovat u zprostředkovatele a vždy, když předdefinovanou podmínku, události nebo změna stavu dojde, zprostředkovatel automaticky oznámí všechny pozorovatelů pomocí volání jeden své metody.</span><span class="sxs-lookup"><span data-stu-id="edbdd-106">Observers register with the provider, and whenever a predefined condition, event, or state change occurs, the provider automatically notifies all observers by calling one of their methods.</span></span> <span data-ttu-id="edbdd-107">Při volání této metody zprostředkovatele můžete také poskytnout aktuální informace o stavu pozorovatelů.</span><span class="sxs-lookup"><span data-stu-id="edbdd-107">In this method call, the provider can also provide current state information to observers.</span></span> <span data-ttu-id="edbdd-108">V rozhraní .NET Framework, je použít návrhový vzor pozorovatel implementací obecná <xref:System.IObservable%601?displayProperty=nameWithType> a <xref:System.IObserver%601?displayProperty=nameWithType> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="edbdd-108">In the .NET Framework, the observer design pattern is applied by implementing the generic <xref:System.IObservable%601?displayProperty=nameWithType> and <xref:System.IObserver%601?displayProperty=nameWithType> interfaces.</span></span> <span data-ttu-id="edbdd-109">Parametr obecného typu představuje typ, který poskytuje informace o oznámení.</span><span class="sxs-lookup"><span data-stu-id="edbdd-109">The generic type parameter represents the type that provides notification information.</span></span>  
  
## <a name="applying-the-pattern"></a><span data-ttu-id="edbdd-110">Použití vzoru</span><span class="sxs-lookup"><span data-stu-id="edbdd-110">Applying the Pattern</span></span>  
 <span data-ttu-id="edbdd-111">Návrhový vzor pozorovatel je vhodná pro distribuované nabízená oznámení, protože podporuje čistou oddělení mezi dva různé součásti nebo aplikačními vrstvami, jako je například vrstvu (obchodní logiku) zdroj dat a uživatelské rozhraní (zobrazení) vrstvě.</span><span class="sxs-lookup"><span data-stu-id="edbdd-111">The observer design pattern is suitable for distributed push-based notifications, because it supports a clean separation between two different components or application layers, such as a data source (business logic) layer and a user interface (display) layer.</span></span> <span data-ttu-id="edbdd-112">Vzor se dá implementovat pokaždé, když poskytovatele zpětná volání použije k poskytování jeho klienty s aktuální informace.</span><span class="sxs-lookup"><span data-stu-id="edbdd-112">The pattern can be implemented whenever a provider uses callbacks to supply its clients with current information.</span></span>  
  
 <span data-ttu-id="edbdd-113">Implementace vzoru vyžaduje zadání následující:</span><span class="sxs-lookup"><span data-stu-id="edbdd-113">Implementing the pattern requires that you provide the following:</span></span>  
  
-   <span data-ttu-id="edbdd-114">Zprostředkovatele nebo předmětu, což je objekt, který odesílá oznámení pozorovatele.</span><span class="sxs-lookup"><span data-stu-id="edbdd-114">A provider or subject, which is the object that sends notifications to observers.</span></span> <span data-ttu-id="edbdd-115">Zprostředkovatel je třídu nebo strukturu, která implementuje <xref:System.IObservable%601> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="edbdd-115">A provider is a class or structure that implements the <xref:System.IObservable%601> interface.</span></span> <span data-ttu-id="edbdd-116">Zprostředkovatel musí implementovat jednu metodu, <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>, která je volána metodou pozorovatelů, které chcete dostávat oznámení od zprostředkovatele.</span><span class="sxs-lookup"><span data-stu-id="edbdd-116">The provider must implement a single method, <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>, which is called by observers that wish to receive notifications from the provider.</span></span>  
  
-   <span data-ttu-id="edbdd-117">Pozorovatel, což je objekt, který obdrží oznámení ze zprostředkovatele.</span><span class="sxs-lookup"><span data-stu-id="edbdd-117">An observer, which is an object that receives notifications from a provider.</span></span> <span data-ttu-id="edbdd-118">Pozorovatel je třídu nebo strukturu, která implementuje <xref:System.IObserver%601> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="edbdd-118">An observer is a class or structure that implements the <xref:System.IObserver%601> interface.</span></span> <span data-ttu-id="edbdd-119">Pozorovatel musí implementovat tři metody, které se nazývají zprostředkovatelem:</span><span class="sxs-lookup"><span data-stu-id="edbdd-119">The observer must implement three methods, all of which are called by the provider:</span></span>  
  
    -   <span data-ttu-id="edbdd-120"><xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, který poskytuje pozorovatel s aktuální nebo nové informace.</span><span class="sxs-lookup"><span data-stu-id="edbdd-120"><xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, which supplies the observer with new or current information.</span></span>  
  
    -   <span data-ttu-id="edbdd-121"><xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, která informuje pozorovatel, který došlo k chybě.</span><span class="sxs-lookup"><span data-stu-id="edbdd-121"><xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, which informs the observer that an error has occurred.</span></span>  
  
    -   <span data-ttu-id="edbdd-122"><xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, což naznačuje, že zprostředkovatel bylo dokončeno odesílání oznámení.</span><span class="sxs-lookup"><span data-stu-id="edbdd-122"><xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, which indicates that the provider has finished sending notifications.</span></span>  
  
-   <span data-ttu-id="edbdd-123">Mechanismus, který umožňuje poskytovateli ke sledování pozorovatelů.</span><span class="sxs-lookup"><span data-stu-id="edbdd-123">A mechanism that allows the provider to keep track of observers.</span></span> <span data-ttu-id="edbdd-124">Obvykle používá zprostředkovatel objekt kontejneru, například <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> objektu k udržení odkazů na <xref:System.IObserver%601> implementace, které odebírá oznámení.</span><span class="sxs-lookup"><span data-stu-id="edbdd-124">Typically, the provider uses a container object, such as a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> object, to hold references to the <xref:System.IObserver%601> implementations that have subscribed to notifications.</span></span> <span data-ttu-id="edbdd-125">Použití kontejner úložiště pro tento účel umožňuje zprostředkovatele pro zpracování nula na neomezený počet pozorovatelů.</span><span class="sxs-lookup"><span data-stu-id="edbdd-125">Using a storage container for this purpose enables the provider to handle zero to an unlimited number of observers.</span></span> <span data-ttu-id="edbdd-126">Pořadí, ve kterém pozorovatelů obdrží oznámení není definován; Zprostředkovatel je můžete použít libovolnou metodu pro určení pořadí.</span><span class="sxs-lookup"><span data-stu-id="edbdd-126">The order in which observers receive notifications is not defined; the provider is free to use any method to determine the order.</span></span>  
  
-   <span data-ttu-id="edbdd-127"><xref:System.IDisposable> Implementace, která umožňuje poskytovateli odeberte pozorovatelů po dokončení oznámení.</span><span class="sxs-lookup"><span data-stu-id="edbdd-127">An <xref:System.IDisposable> implementation that enables the provider to remove observers when notification is complete.</span></span> <span data-ttu-id="edbdd-128">Pozorovatelů zobrazí odkaz na <xref:System.IDisposable> implementace z <xref:System.IObservable%601.Subscribe%2A> metoda, takže můžete také zavolat <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> metoda k odhlášení odběru před zprostředkovatele dokončila odesílání oznámení.</span><span class="sxs-lookup"><span data-stu-id="edbdd-128">Observers receive a reference to the <xref:System.IDisposable> implementation from the <xref:System.IObservable%601.Subscribe%2A> method, so they can also call the <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> method to unsubscribe before the provider has finished sending notifications.</span></span>  
  
-   <span data-ttu-id="edbdd-129">Objekt, který obsahuje data, která odešle zprostředkovatel jeho pozorovatelů.</span><span class="sxs-lookup"><span data-stu-id="edbdd-129">An object that contains the data that the provider sends to its observers.</span></span> <span data-ttu-id="edbdd-130">Typ tohoto objektu odpovídá parametr obecného typu <xref:System.IObservable%601> a <xref:System.IObserver%601> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="edbdd-130">The type of this object corresponds to the generic type parameter of the <xref:System.IObservable%601> and <xref:System.IObserver%601> interfaces.</span></span> <span data-ttu-id="edbdd-131">I když tento objekt může být stejný jako <xref:System.IObservable%601> implementace nejčastěji je samostatný typu.</span><span class="sxs-lookup"><span data-stu-id="edbdd-131">Although this object can be the same as the <xref:System.IObservable%601> implementation, most commonly it is a separate type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edbdd-132">Kromě implementace návrhový vzor pozorovatel, vás může zajímat zkoumat knihovny, které jsou vytvořené pomocí <xref:System.IObservable%601> a <xref:System.IObserver%601> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="edbdd-132">In addition to implementing the observer design pattern, you may be interested in exploring libraries that are built using the <xref:System.IObservable%601> and <xref:System.IObserver%601> interfaces.</span></span> <span data-ttu-id="edbdd-133">Například [reaktivní rozšíření pro platformu .NET (Rx)](http://go.microsoft.com/fwlink/?LinkId=186345) obsahují sadu metod rozšíření a operátory standardní pořadí LINQ pro podporu asynchronní programování.</span><span class="sxs-lookup"><span data-stu-id="edbdd-133">For example, [Reactive Extensions for .NET (Rx)](http://go.microsoft.com/fwlink/?LinkId=186345) consist of a set of extension methods and LINQ standard sequence operators to support asynchronous programming.</span></span>  
  
## <a name="implementing-the-pattern"></a><span data-ttu-id="edbdd-134">Implementace vzoru</span><span class="sxs-lookup"><span data-stu-id="edbdd-134">Implementing the Pattern</span></span>  
 <span data-ttu-id="edbdd-135">Následující příklad používá návrhový vzor pozorovatel k implementaci informace systému letiště sobě deklarace identity.</span><span class="sxs-lookup"><span data-stu-id="edbdd-135">The following example uses the observer design pattern to implement an airport baggage claim information system.</span></span> <span data-ttu-id="edbdd-136">A `BaggageInfo` třída poskytuje informace o které letů a karusely, kde je k dispozici pro vyzvednutí sobě z každý let.</span><span class="sxs-lookup"><span data-stu-id="edbdd-136">A `BaggageInfo` class provides information about arriving flights and the carousels where baggage from each flight is available for pickup.</span></span> <span data-ttu-id="edbdd-137">Zobrazí se v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="edbdd-137">It is shown in the following example.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/provider.cs#1)]
 [!code-vb[Conceptual.ObserverDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/provider.vb#1)]  
  
 <span data-ttu-id="edbdd-138">A `BaggageHandler` třída je odpovědná za přijímá informace, o které letů a sobě deklarací karusely.</span><span class="sxs-lookup"><span data-stu-id="edbdd-138">A `BaggageHandler` class is responsible for receiving information about arriving flights and baggage claim carousels.</span></span> <span data-ttu-id="edbdd-139">Interně udržuje dvě kolekce:</span><span class="sxs-lookup"><span data-stu-id="edbdd-139">Internally, it maintains two collections:</span></span>  
  
-   <span data-ttu-id="edbdd-140">`observers`-Kolekci klientů, kteří je budou přijímat aktualizované informace.</span><span class="sxs-lookup"><span data-stu-id="edbdd-140">`observers` - A collection of clients that will receive updated information.</span></span>  
  
-   <span data-ttu-id="edbdd-141">`flights`-Kolekce letů a jejich přiřazené karusely.</span><span class="sxs-lookup"><span data-stu-id="edbdd-141">`flights` - A collection of flights and their assigned carousels.</span></span>  
  
 <span data-ttu-id="edbdd-142">Obě kolekce jsou reprezentované pomocí obecného <xref:System.Collections.Generic.List%601> objekty, které jsou vytvářeny instance v `BaggageHandler` konstruktoru třídy.</span><span class="sxs-lookup"><span data-stu-id="edbdd-142">Both collections are represented by generic <xref:System.Collections.Generic.List%601> objects that are instantiated in the `BaggageHandler` class constructor.</span></span> <span data-ttu-id="edbdd-143">Zdrojový kód `BaggageHandler` třída je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="edbdd-143">The source code for the `BaggageHandler` class is shown in the following example.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/provider.cs#2)]
 [!code-vb[Conceptual.ObserverDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/provider.vb#2)]  
  
 <span data-ttu-id="edbdd-144">Volání klientů, které chcete přijímat aktualizované informace `BaggageHandler.Subscribe` metoda.</span><span class="sxs-lookup"><span data-stu-id="edbdd-144">Clients that wish to receive updated information call the `BaggageHandler.Subscribe` method.</span></span> <span data-ttu-id="edbdd-145">Pokud klient nebyl dříve přihlásit k odběru oznámení, odkaz na klienta <xref:System.IObserver%601> implementace je přidán do `observers` kolekce.</span><span class="sxs-lookup"><span data-stu-id="edbdd-145">If the client has not previously subscribed to notifications, a reference to the client's <xref:System.IObserver%601> implementation is added to the `observers` collection.</span></span>  
  
 <span data-ttu-id="edbdd-146">Přetížené `BaggageHandler.BaggageStatus` nelze volat metodu že sobě z letu odpojení, nebo už odpojení.</span><span class="sxs-lookup"><span data-stu-id="edbdd-146">The overloaded `BaggageHandler.BaggageStatus` method can be called to indicate that baggage from a flight either is being unloaded or is no longer being unloaded.</span></span> <span data-ttu-id="edbdd-147">V prvním případě metodu je předán číslo letu, ze kterého pochází letu letiště a karuselu kde sobě odpojení.</span><span class="sxs-lookup"><span data-stu-id="edbdd-147">In the first case, the method is passed a flight number, the airport from which the flight originated, and the carousel where baggage is being unloaded.</span></span> <span data-ttu-id="edbdd-148">V druhém případě je předán metodu jenom číslo letu.</span><span class="sxs-lookup"><span data-stu-id="edbdd-148">In the second case, the method is passed only a flight number.</span></span> <span data-ttu-id="edbdd-149">Pro sobě, který je odpojeno, metoda kontroly jestli `BaggageInfo` informace předaný metodě existuje v `flights` kolekce.</span><span class="sxs-lookup"><span data-stu-id="edbdd-149">For baggage that is being unloaded, the method checks whether the `BaggageInfo` information passed to the method exists in the `flights` collection.</span></span> <span data-ttu-id="edbdd-150">Pokud ne, metoda přidá informace a volá každý pozorovatel `OnNext` metoda.</span><span class="sxs-lookup"><span data-stu-id="edbdd-150">If it does not, the method adds the information and calls each observer's `OnNext` method.</span></span> <span data-ttu-id="edbdd-151">Metoda pro lety, jejichž sobě už odpojení, zkontroluje, zda informace na této cestě jsou uloženy v `flights` kolekce.</span><span class="sxs-lookup"><span data-stu-id="edbdd-151">For flights whose baggage is no longer being unloaded, the method checks whether information on that flight is stored in the `flights` collection.</span></span> <span data-ttu-id="edbdd-152">Pokud se jedná, volá metodu každý pozorovatel `OnNext` metoda a odebere `BaggageInfo` objektu z `flights` kolekce.</span><span class="sxs-lookup"><span data-stu-id="edbdd-152">If it is, the method calls each observer's `OnNext` method and removes the `BaggageInfo` object from the `flights` collection.</span></span>  
  
 <span data-ttu-id="edbdd-153">Když má dostali poslední letu dne a zpracovala jeho sobě `BaggageHandler.LastBaggageClaimed` metoda je volána.</span><span class="sxs-lookup"><span data-stu-id="edbdd-153">When the last flight of the day has landed and its baggage has been processed, the `BaggageHandler.LastBaggageClaimed` method is called.</span></span> <span data-ttu-id="edbdd-154">Tato metoda volá každý pozorovatel `OnCompleted` metoda indikující, že byly dokončeny všechny oznámení a pak zruší `observers` kolekce.</span><span class="sxs-lookup"><span data-stu-id="edbdd-154">This method calls each observer's `OnCompleted` method to indicate that all notifications have completed, and then clears the `observers` collection.</span></span>  
  
 <span data-ttu-id="edbdd-155">Poskytovatele <xref:System.IObservable%601.Subscribe%2A> metoda vrátí <xref:System.IDisposable> implementace, která umožňuje pozorovatelů zastavit přijímání oznámení před <xref:System.IObserver%601.OnCompleted%2A> metoda je volána.</span><span class="sxs-lookup"><span data-stu-id="edbdd-155">The provider's <xref:System.IObservable%601.Subscribe%2A> method returns an <xref:System.IDisposable> implementation that enables observers to stop receiving notifications before the <xref:System.IObserver%601.OnCompleted%2A> method is called.</span></span> <span data-ttu-id="edbdd-156">Zdrojový kód pro tuto `Unsubscriber(Of BaggageInfo)` třída je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="edbdd-156">The source code for this `Unsubscriber(Of BaggageInfo)` class is shown in the following example.</span></span> <span data-ttu-id="edbdd-157">Když je vytvořena instance třídy v `BaggageHandler.Subscribe` metoda, je předán odkaz na `observers` kolekce a odkaz na pozorovatel, který je přidán do kolekce.</span><span class="sxs-lookup"><span data-stu-id="edbdd-157">When the class is instantiated in the `BaggageHandler.Subscribe` method, it is passed a reference to the `observers` collection and a reference to the observer that is added to the collection.</span></span> <span data-ttu-id="edbdd-158">Tyto odkazy jsou přiřazeny k lokální proměnné.</span><span class="sxs-lookup"><span data-stu-id="edbdd-158">These references are assigned to local variables.</span></span> <span data-ttu-id="edbdd-159">Když objektu `Dispose` metoda je volána, zkontroluje, zda stále existuje pozorovatel v `observers` kolekce a pokud ano, odebere pozorovatele.</span><span class="sxs-lookup"><span data-stu-id="edbdd-159">When the object's `Dispose` method is called, it checks whether the observer still exists in the `observers` collection, and, if it does, removes the observer.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/provider.cs#3)]
 [!code-vb[Conceptual.ObserverDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/provider.vb#3)]  
  
 <span data-ttu-id="edbdd-160">Následující příklad uvádí <xref:System.IObserver%601> implementace s názvem `ArrivalsMonitor`, což je základní třídu, která zobrazuje informace o sobě deklaraci identity.</span><span class="sxs-lookup"><span data-stu-id="edbdd-160">The following example provides an <xref:System.IObserver%601> implementation named `ArrivalsMonitor`, which is a base class that displays baggage claim information.</span></span> <span data-ttu-id="edbdd-161">Název města, původní je abecedně, zobrazují informace.</span><span class="sxs-lookup"><span data-stu-id="edbdd-161">The information is displayed alphabetically, by the name of the originating city.</span></span> <span data-ttu-id="edbdd-162">Metody `ArrivalsMonitor` jsou označeny jako `overridable` (v jazyce Visual Basic) nebo `virtual` (v jazyku C#), takže je můžete všechny přepsat odvozenou třídou.</span><span class="sxs-lookup"><span data-stu-id="edbdd-162">The methods of `ArrivalsMonitor` are marked as `overridable` (in Visual Basic) or `virtual` (in C#), so they can all be overridden by a derived class.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/observer.cs#4)]
 [!code-vb[Conceptual.ObserverDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/observer.vb#4)]  
  
 <span data-ttu-id="edbdd-163">`ArrivalsMonitor` Třída zahrnuje `Subscribe` a `Unsubscribe` metody.</span><span class="sxs-lookup"><span data-stu-id="edbdd-163">The `ArrivalsMonitor` class includes the `Subscribe` and `Unsubscribe` methods.</span></span> <span data-ttu-id="edbdd-164">`Subscribe` Metoda umožňuje třídě Uložit <xref:System.IDisposable> implementace vrácený volání <xref:System.IObservable%601.Subscribe%2A> soukromé proměnné.</span><span class="sxs-lookup"><span data-stu-id="edbdd-164">The `Subscribe` method enables the class to save the <xref:System.IDisposable> implementation returned by the call to <xref:System.IObservable%601.Subscribe%2A> to a private variable.</span></span> <span data-ttu-id="edbdd-165">`Unsubscribe` Metoda umožňuje třídě zrušit odběr oznámení voláním poskytovatele <xref:System.IDisposable.Dispose%2A> implementace.</span><span class="sxs-lookup"><span data-stu-id="edbdd-165">The `Unsubscribe` method enables the class to unsubscribe from notifications by calling the provider's <xref:System.IDisposable.Dispose%2A> implementation.</span></span> <span data-ttu-id="edbdd-166">`ArrivalsMonitor`také poskytuje implementace <xref:System.IObserver%601.OnNext%2A>, <xref:System.IObserver%601.OnError%2A>, a <xref:System.IObserver%601.OnCompleted%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="edbdd-166">`ArrivalsMonitor` also provides implementations of the <xref:System.IObserver%601.OnNext%2A>, <xref:System.IObserver%601.OnError%2A>, and <xref:System.IObserver%601.OnCompleted%2A> methods.</span></span> <span data-ttu-id="edbdd-167">Pouze <xref:System.IObserver%601.OnNext%2A> implementace obsahuje významné množství kódu.</span><span class="sxs-lookup"><span data-stu-id="edbdd-167">Only the <xref:System.IObserver%601.OnNext%2A> implementation contains a significant amount of code.</span></span> <span data-ttu-id="edbdd-168">Metoda funguje s privátní, seřazené, obecného <xref:System.Collections.Generic.List%601> objekt, který uchovává informace o letištích původu, pro které lety a karusely, na kterých je k dispozici jejich sobě.</span><span class="sxs-lookup"><span data-stu-id="edbdd-168">The method works with a private, sorted, generic <xref:System.Collections.Generic.List%601> object that maintains information about the airports of origin for arriving flights and the carousels on which their baggage is available.</span></span> <span data-ttu-id="edbdd-169">Pokud `BaggageHandler` třída sestavy nové příchodem letu, <xref:System.IObserver%601.OnNext%2A> implementace metod přidá do seznamu informace o této cestě.</span><span class="sxs-lookup"><span data-stu-id="edbdd-169">If the `BaggageHandler` class reports a new flight arrival, the <xref:System.IObserver%601.OnNext%2A> method implementation adds information about that flight to the list.</span></span> <span data-ttu-id="edbdd-170">Pokud `BaggageHandler` třída hlásí, že letu na sobě byl odpojen, <xref:System.IObserver%601.OnNext%2A> metoda odebere ze seznamu tento let.</span><span class="sxs-lookup"><span data-stu-id="edbdd-170">If the `BaggageHandler` class reports that the flight's baggage has been unloaded, the <xref:System.IObserver%601.OnNext%2A> method removes that flight from the list.</span></span> <span data-ttu-id="edbdd-171">Vždy, když dojde ke změně, seznam seřazen a zobrazení v konzole.</span><span class="sxs-lookup"><span data-stu-id="edbdd-171">Whenever a change is made, the list is sorted and displayed to the console.</span></span>  
  
 <span data-ttu-id="edbdd-172">Následující příklad obsahuje vstupní bod aplikace, který vytvoří instanci `BaggageHandler` třídy a také dvě instance `ArrivalsMonitor` třídy a používá `BaggageHandler.BaggageStatus` metoda přidávat a odebírat informace o které lety.</span><span class="sxs-lookup"><span data-stu-id="edbdd-172">The following example contains the application entry point that instantiates the `BaggageHandler` class as well as two instances of the `ArrivalsMonitor` class, and uses the `BaggageHandler.BaggageStatus` method to add and remove information about arriving flights.</span></span> <span data-ttu-id="edbdd-173">V každém případě pozorovatelů přijímat aktualizace a správně zobrazit informace o sobě deklaraci identity.</span><span class="sxs-lookup"><span data-stu-id="edbdd-173">In each case, the observers receive updates and correctly display baggage claim information.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/program.cs#5)]
 [!code-vb[Conceptual.ObserverDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/module1.vb#5)]  
  
## <a name="related-topics"></a><span data-ttu-id="edbdd-174">Související témata</span><span class="sxs-lookup"><span data-stu-id="edbdd-174">Related Topics</span></span>  
  
|<span data-ttu-id="edbdd-175">Název</span><span class="sxs-lookup"><span data-stu-id="edbdd-175">Title</span></span>|<span data-ttu-id="edbdd-176">Popis</span><span class="sxs-lookup"><span data-stu-id="edbdd-176">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="edbdd-177">Pozorovatel osvědčené postupy pro návrhový vzor</span><span class="sxs-lookup"><span data-stu-id="edbdd-177">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)|<span data-ttu-id="edbdd-178">Popisuje osvědčené postupy při vývoji aplikace, které implementují návrhový vzor pozorovatel přijmout.</span><span class="sxs-lookup"><span data-stu-id="edbdd-178">Describes best practices to adopt when developing applications that implement the observer design pattern.</span></span>|  
|[<span data-ttu-id="edbdd-179">Postupy: implementace poskytovatele</span><span class="sxs-lookup"><span data-stu-id="edbdd-179">How to: Implement a Provider</span></span>](../../../docs/standard/events/how-to-implement-a-provider.md)|<span data-ttu-id="edbdd-180">Poskytuje podrobné implementaci zprostředkovatele pro teplotě monitorování aplikace.</span><span class="sxs-lookup"><span data-stu-id="edbdd-180">Provides a step-by-step implementation of a provider for a temperature monitoring application.</span></span>|  
|[<span data-ttu-id="edbdd-181">Postupy: implementace pozorovatele</span><span class="sxs-lookup"><span data-stu-id="edbdd-181">How to: Implement an Observer</span></span>](../../../docs/standard/events/how-to-implement-an-observer.md)|<span data-ttu-id="edbdd-182">Poskytuje podrobné implementace pozorovatele pro teplotě monitorování aplikace.</span><span class="sxs-lookup"><span data-stu-id="edbdd-182">Provides a step-by-step implementation of an observer for a temperature monitoring application.</span></span>|