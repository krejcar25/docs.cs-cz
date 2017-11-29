---
title: "Vícevláknové aplikace (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b7015cfb-d506-4eac-b2f8-b2caaa9cc977
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 48b056172e3260952155eb40a1a393d86da78344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="multithreaded-applications-c"></a><span data-ttu-id="fb444-102">Vícevláknové aplikace (C#)</span><span class="sxs-lookup"><span data-stu-id="fb444-102">Multithreaded Applications (C#)</span></span>
<span data-ttu-id="fb444-103">Díky C# můžete vytvořit aplikace, které provádějí více úkolů ve stejnou dobu.</span><span class="sxs-lookup"><span data-stu-id="fb444-103">With C#, you can write applications that perform multiple tasks at the same time.</span></span> <span data-ttu-id="fb444-104">Úlohy s potenciálně pojme dalších úloh můžete provést v samostatných vláknech, tento proces se označuje jako *multithreading* nebo *volné dělení na vlákna*.</span><span class="sxs-lookup"><span data-stu-id="fb444-104">Tasks with the potential of holding up other tasks can execute on separate threads, a process known as *multithreading* or *free threading*.</span></span>  
  
 <span data-ttu-id="fb444-105">Aplikace, které jsou rychlejší reakce na uživatelský vstup, protože uživatelské rozhraní zůstane aktivní, jak je náročná na výkon procesoru úkoly spustí v samostatných vláknech používání více vláken.</span><span class="sxs-lookup"><span data-stu-id="fb444-105">Applications that use multithreading are more responsive to user input because the user interface stays active as processor-intensive tasks execute on separate threads.</span></span> <span data-ttu-id="fb444-106">Multithreading je také užitečné, když vytvoříte škálovatelné aplikace, protože vláken můžete přidat jako zvyšuje zatížení.</span><span class="sxs-lookup"><span data-stu-id="fb444-106">Multithreading is also useful when you create scalable applications, because you can add threads as the workload increases.</span></span>  
  
## <a name="creating-and-using-threads"></a><span data-ttu-id="fb444-107">Vytváření a používání vláken</span><span class="sxs-lookup"><span data-stu-id="fb444-107">Creating and Using Threads</span></span>  
 <span data-ttu-id="fb444-108">Pokud potřebujete větší kontrolu nad chováním aplikace vláken, můžete spravovat vláken sami.</span><span class="sxs-lookup"><span data-stu-id="fb444-108">If you need more control over the behavior of your application's threads, you can manage the threads yourself.</span></span> <span data-ttu-id="fb444-109">Ale potřeba si uvědomit, zápis správné vícevláknové aplikace může být složité: vaše aplikace může přestat reagovat nebo dojde k přechodné chybě způsobené časování.</span><span class="sxs-lookup"><span data-stu-id="fb444-109">However, realize that writing correct multithreaded applications can be difficult: Your application may stop responding or experience transient errors caused by race conditions.</span></span> <span data-ttu-id="fb444-110">Další informace najdete v tématu [vláken komponent](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span><span class="sxs-lookup"><span data-stu-id="fb444-110">For more information, see [Thread-Safe Components](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span></span>  
  
 <span data-ttu-id="fb444-111">Vytvořit nové vlákno deklarováním proměnné typu <xref:System.Threading.Thread> a volání konstruktoru, poskytuje název postupu nebo metodu, kterou chcete provést na nové vlákno.</span><span class="sxs-lookup"><span data-stu-id="fb444-111">You create a new thread by declaring a variable of type <xref:System.Threading.Thread> and calling the constructor, providing the name of the procedure or method that you want to execute on the new thread.</span></span> <span data-ttu-id="fb444-112">Následující kód představuje příklad.</span><span class="sxs-lookup"><span data-stu-id="fb444-112">The following code provides an example.</span></span>  
  
```csharp  
System.Threading.Thread newThread =  
    new System.Threading.Thread(AMethod);  
```  
  
### <a name="starting-and-stopping-threads"></a><span data-ttu-id="fb444-113">Spouštění a zastavování vláken</span><span class="sxs-lookup"><span data-stu-id="fb444-113">Starting and Stopping Threads</span></span>  
 <span data-ttu-id="fb444-114">Chcete-li spustit provádění nové vlákno, použijte <xref:System.Threading.Thread.Start%2A> metoda, jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="fb444-114">To start the execution of a new thread, use the <xref:System.Threading.Thread.Start%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Start();  
```  
  
 <span data-ttu-id="fb444-115">Chcete-li zastavit provádění vlákna, použijte <xref:System.Threading.Thread.Abort%2A> metoda, jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="fb444-115">To stop the execution of a thread, use the <xref:System.Threading.Thread.Abort%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Abort();  
```  
  
 <span data-ttu-id="fb444-116">Kromě toho, spouštění a zastavování vláken, je také možné pozastavit vláken voláním <xref:System.Threading.Thread.Sleep%2A> nebo <xref:System.Threading.Thread.Suspend%2A> metoda, obnovit pozastavenou vlákno pomocí <xref:System.Threading.Thread.Resume%2A> metoda a zrušení vlákno pomocí <xref:System.Threading.Thread.Abort%2A> – metoda</span><span class="sxs-lookup"><span data-stu-id="fb444-116">Besides starting and stopping threads, you can also pause threads by calling the <xref:System.Threading.Thread.Sleep%2A> or <xref:System.Threading.Thread.Suspend%2A> method, resume a suspended thread by using the <xref:System.Threading.Thread.Resume%2A> method, and destroy a thread by using the <xref:System.Threading.Thread.Abort%2A> method</span></span>  
  
### <a name="thread-methods"></a><span data-ttu-id="fb444-117">Metody přístup z více vláken</span><span class="sxs-lookup"><span data-stu-id="fb444-117">Thread Methods</span></span>  
 <span data-ttu-id="fb444-118">V následující tabulce jsou uvedeny některé metody, které můžete použít k řízení jednotlivých vláken.</span><span class="sxs-lookup"><span data-stu-id="fb444-118">The following table shows some of the methods that you can use to control individual threads.</span></span>  
  
|<span data-ttu-id="fb444-119">Metoda</span><span class="sxs-lookup"><span data-stu-id="fb444-119">Method</span></span>|<span data-ttu-id="fb444-120">Akce</span><span class="sxs-lookup"><span data-stu-id="fb444-120">Action</span></span>|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|<span data-ttu-id="fb444-121">Způsobí, že vlákno k spustí.</span><span class="sxs-lookup"><span data-stu-id="fb444-121">Causes a thread to start to run.</span></span>|  
|<xref:System.Threading.Thread.Sleep%2A>|<span data-ttu-id="fb444-122">Vlákna pozastaví po určitou dobu.</span><span class="sxs-lookup"><span data-stu-id="fb444-122">Pauses a thread for a specified time.</span></span>|  
|<xref:System.Threading.Thread.Suspend%2A>|<span data-ttu-id="fb444-123">Vlákna pozastaví při dosažení bod bezpečné.</span><span class="sxs-lookup"><span data-stu-id="fb444-123">Pauses a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Abort%2A>|<span data-ttu-id="fb444-124">Vlákno zastaví, když dorazí do bod bezpečné.</span><span class="sxs-lookup"><span data-stu-id="fb444-124">Stops a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Resume%2A>|<span data-ttu-id="fb444-125">Restartuje pozastavenou vlákna</span><span class="sxs-lookup"><span data-stu-id="fb444-125">Restarts a suspended thread</span></span>|  
|<xref:System.Threading.Thread.Join%2A>|<span data-ttu-id="fb444-126">Způsobí, že aktuální vlákno čekat na dokončení jiné vlákno.</span><span class="sxs-lookup"><span data-stu-id="fb444-126">Causes the current thread to wait for another thread to finish.</span></span> <span data-ttu-id="fb444-127">Pokud se používá s hodnotu časového limitu, vrátí tato metoda `True` Pokud skončí vlákno v přiděleném čase.</span><span class="sxs-lookup"><span data-stu-id="fb444-127">If used with a time-out value, this method returns `True` if the thread finishes in the allocated time.</span></span>|  
  
### <a name="safe-points"></a><span data-ttu-id="fb444-128">Bezpečné body</span><span class="sxs-lookup"><span data-stu-id="fb444-128">Safe Points</span></span>  
 <span data-ttu-id="fb444-129">Většina těchto metod jsou samovysvětlující, ale koncept *bezpečné body* může být pro vás nový.</span><span class="sxs-lookup"><span data-stu-id="fb444-129">Most of these methods are self-explanatory, but the concept of *safe points* may be new to you.</span></span> <span data-ttu-id="fb444-130">Bezpečné body jsou umístění v kódu, kde je bezpečný pro modul common language runtime provést automatické *uvolňování paměti*, proces uvolňování nepoužívané proměnné a opětovného získání paměti.</span><span class="sxs-lookup"><span data-stu-id="fb444-130">Safe points are locations in code where it is safe for the common language runtime to perform automatic *garbage collection*, the process of releasing unused variables and reclaiming memory.</span></span> <span data-ttu-id="fb444-131">Při volání <xref:System.Threading.Thread.Abort%2A> nebo <xref:System.Threading.Thread.Suspend%2A> metoda vlákno, modul common language runtime analyzuje kód a určuje umístění požadované místo pro vlákno zastavení.</span><span class="sxs-lookup"><span data-stu-id="fb444-131">When you call the <xref:System.Threading.Thread.Abort%2A> or <xref:System.Threading.Thread.Suspend%2A> method of a thread, the common language runtime analyzes the code and determines the location of an appropriate location for the thread to stop running.</span></span>  
  
### <a name="thread-properties"></a><span data-ttu-id="fb444-132">Vlastnosti vlákna</span><span class="sxs-lookup"><span data-stu-id="fb444-132">Thread Properties</span></span>  
 <span data-ttu-id="fb444-133">Vláken taky obsahovat užitečné několik vlastností, jak je znázorněno v následující tabulce:</span><span class="sxs-lookup"><span data-stu-id="fb444-133">Threads also contain several useful properties, as shown in the following table:</span></span>  
  
|<span data-ttu-id="fb444-134">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="fb444-134">Property</span></span>|<span data-ttu-id="fb444-135">Hodnota</span><span class="sxs-lookup"><span data-stu-id="fb444-135">Value</span></span>|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|<span data-ttu-id="fb444-136">Obsahuje hodnotu `True` Pokud vlákno je aktivní.</span><span class="sxs-lookup"><span data-stu-id="fb444-136">Contains the value `True` if a thread is active.</span></span>|  
|<xref:System.Threading.Thread.IsBackground%2A>|<span data-ttu-id="fb444-137">Získá nebo nastaví logickou hodnotu, která určuje, pokud je na vlákno, nebo by měly být vlákna na pozadí.</span><span class="sxs-lookup"><span data-stu-id="fb444-137">Gets or sets a Boolean that indicates if a thread is or should be a background thread.</span></span> <span data-ttu-id="fb444-138">Vlákna na pozadí jsou jako vlákna na popředí, ale vlákna na pozadí nezabrání proces zastavit.</span><span class="sxs-lookup"><span data-stu-id="fb444-138">Background threads are like foreground threads, but a background thread does not prevent a process from stopping.</span></span> <span data-ttu-id="fb444-139">Jakmile je nutné zastavit všechna vlákna na popředí, které patří do procesu, modul common language runtime ukončí proces voláním <xref:System.Threading.Thread.Abort%2A> metodu vlákna na pozadí, které jsou stále aktivní.</span><span class="sxs-lookup"><span data-stu-id="fb444-139">Once all foreground threads that belong to a process have stopped, the common language runtime ends the process by calling the <xref:System.Threading.Thread.Abort%2A> method on background threads that are still alive.</span></span>|  
|<xref:System.Threading.Thread.Name%2A>|<span data-ttu-id="fb444-140">Získá nebo nastaví název vlákna.</span><span class="sxs-lookup"><span data-stu-id="fb444-140">Gets or sets the name of a thread.</span></span> <span data-ttu-id="fb444-141">Nejčastěji používá ke zjišťování jednotlivých vláken při ladění.</span><span class="sxs-lookup"><span data-stu-id="fb444-141">Most frequently used to discover individual threads when you debug.</span></span>|  
|<xref:System.Threading.Thread.Priority%2A>|<span data-ttu-id="fb444-142">Získá nebo nastaví hodnotu, která se používá v operačním systému k určení priority plánování přístup z více vláken.</span><span class="sxs-lookup"><span data-stu-id="fb444-142">Gets or sets a value that is used by the operating system to prioritize thread scheduling.</span></span>|  
|<xref:System.Threading.Thread.ThreadState%2A>|<span data-ttu-id="fb444-143">Obsahuje hodnotu, která popisuje stavu nebo stavy, které vlákno.</span><span class="sxs-lookup"><span data-stu-id="fb444-143">Contains a value that describes a thread's state or states.</span></span>|  
  
## <a name="thread-priorities"></a><span data-ttu-id="fb444-144">Priority přístup z více vláken</span><span class="sxs-lookup"><span data-stu-id="fb444-144">Thread Priorities</span></span>  
 <span data-ttu-id="fb444-145">Každé vlákno má vlastnost priority, která určuje, jak velký či malý řez času procesoru je provést.</span><span class="sxs-lookup"><span data-stu-id="fb444-145">Every thread has a priority property that determines how big or small a slice of processor time it has to execute.</span></span> <span data-ttu-id="fb444-146">Operační systém přiděluje delší časové úseky, můžete s vysokou prioritou vlákna a kratší časových řezů na nízkou prioritu vláken.</span><span class="sxs-lookup"><span data-stu-id="fb444-146">The operating system allocates longer time slices to high-priority threads and shorter time slices to low-priority threads.</span></span> <span data-ttu-id="fb444-147">Nové vláken jsou vytvořené s hodnotou `Normal`, ale můžete změnit <xref:System.Threading.Thread.Priority%2A> vlastnost na jakoukoli hodnotu v <xref:System.Threading.ThreadPriority> výčtu.</span><span class="sxs-lookup"><span data-stu-id="fb444-147">New threads are created with the value of `Normal`, but you can change the <xref:System.Threading.Thread.Priority%2A> property to any value in the <xref:System.Threading.ThreadPriority> enumeration.</span></span>  
  
 <span data-ttu-id="fb444-148">V tématu <xref:System.Threading.ThreadPriority> podrobný popis různých priorit přístup z více vláken.</span><span class="sxs-lookup"><span data-stu-id="fb444-148">See <xref:System.Threading.ThreadPriority> for a detailed description of the various thread priorities.</span></span>  
  
## <a name="foreground-and-background-threads"></a><span data-ttu-id="fb444-149">Vlákna v popředí a v pozadí</span><span class="sxs-lookup"><span data-stu-id="fb444-149">Foreground and Background Threads</span></span>  
 <span data-ttu-id="fb444-150">A *vlákna na popředí* spustí po neomezenou dobu, zatímco *vlákna na pozadí* zastaví, jakmile poslední vlákno popředí byla zastavena.</span><span class="sxs-lookup"><span data-stu-id="fb444-150">A *foreground thread* runs indefinitely, whereas a *background thread* stops as soon as the last foreground thread has stopped.</span></span> <span data-ttu-id="fb444-151">Můžete použít <xref:System.Threading.Thread.IsBackground%2A> vlastnosti k určení, nebo změňte stav vlákna na pozadí.</span><span class="sxs-lookup"><span data-stu-id="fb444-151">You can use the <xref:System.Threading.Thread.IsBackground%2A> property to determine or change the background status of a thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb444-152">Viz také</span><span class="sxs-lookup"><span data-stu-id="fb444-152">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="fb444-153">Synchronizace vláken (C#)</span><span class="sxs-lookup"><span data-stu-id="fb444-153">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="fb444-154">Parametry a návratové hodnoty pro procedury ve více vláknech (C#)</span><span class="sxs-lookup"><span data-stu-id="fb444-154">Parameters and Return Values for Multithreaded Procedures (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)  
 [<span data-ttu-id="fb444-155">Dělení na vlákna (C#)</span><span class="sxs-lookup"><span data-stu-id="fb444-155">Threading (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/index.md)