---
title: "Synchronizace vláken (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e42b1be6-c93c-479f-a148-be0759f1a4e1
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2b51775eac5221ec8c723d89323d1f4f542d2453
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="thread-synchronization-c"></a><span data-ttu-id="7e4aa-102">Synchronizace vláken (C#)</span><span class="sxs-lookup"><span data-stu-id="7e4aa-102">Thread Synchronization (C#)</span></span>
<span data-ttu-id="7e4aa-103">Následující části popisují funkce a třídy, které slouží k synchronizaci přístup k prostředkům v vícevláknové aplikace.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-103">The following sections describe features and classes that can be used to synchronize access to resources in multithreaded applications.</span></span>  
  
 <span data-ttu-id="7e4aa-104">Jednou z výhod používání více vláken v aplikaci je asynchronně provádí každé vlákno.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-104">One of the benefits of using multiple threads in an application is that each thread executes asynchronously.</span></span> <span data-ttu-id="7e4aa-105">Pro aplikace systému Windows to umožňuje časově náročné úlohy, které mají být provedeny na pozadí při okna aplikace a ovládací prvky zůstanou reaguje.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-105">For Windows applications, this allows time-consuming tasks to be performed in the background while the application window and controls remain responsive.</span></span> <span data-ttu-id="7e4aa-106">Aplikace, více vláken pro server poskytuje možnost pro zpracování jednotlivých příchozích požadavků s jiném podprocesu.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-106">For server applications, multithreading provides the ability to handle each incoming request with a different thread.</span></span> <span data-ttu-id="7e4aa-107">Každý nový požadavek, jinak hodnota nebude získat servis dokud předchozí požadavek je plně splněna.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-107">Otherwise, each new request would not get serviced until the previous request had been fully satisfied.</span></span>  
  
 <span data-ttu-id="7e4aa-108">Ale musí být koordinované asynchronní povaha vláken znamená, že přístup k prostředkům, jako jsou popisovače souborů, připojení k síti a paměti.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-108">However, the asynchronous nature of threads means that access to resources such as file handles, network connections, and memory must be coordinated.</span></span> <span data-ttu-id="7e4aa-109">Dvě nebo více vláken, jinak hodnota přístup stejného zdroje ve stejnou dobu, každý dál, bez ohledu druhé strany akcí.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-109">Otherwise, two or more threads could access the same resource at the same time, each unaware of the other's actions.</span></span> <span data-ttu-id="7e4aa-110">Výsledkem je poškození dat nepředvídatelné.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-110">The result is unpredictable data corruption.</span></span>  
  
 <span data-ttu-id="7e4aa-111">Pro jednoduché operace na integrální číselné datové typy synchronizace vláken lze provést pomocí členy <xref:System.Threading.Interlocked> třídy.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-111">For simple operations on integral numeric data types, synchronizing threads can be accomplished with members of the <xref:System.Threading.Interlocked> class.</span></span> <span data-ttu-id="7e4aa-112">Pro všechna ostatní data typy a prostředky nejsou bezpečné pro přístup z více vláken, multithreading můžete bezpečně provést pouze pomocí konstrukce v tomto tématu.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-112">For all other data types and non thread-safe resources, multithreading can only be safely performed using the constructs in this topic.</span></span>  
  
 <span data-ttu-id="7e4aa-113">Základní informace o vícevláknové programování naleznete v tématu:</span><span class="sxs-lookup"><span data-stu-id="7e4aa-113">For background information on multithreaded programming, see:</span></span>  
  
-   [<span data-ttu-id="7e4aa-114">Dělení na spravovaná vlákna základy</span><span class="sxs-lookup"><span data-stu-id="7e4aa-114">Managed Threading Basics</span></span>](../../../../standard/threading/managed-threading-basics.md)  
  
-   [<span data-ttu-id="7e4aa-115">Použití vláken a dělení na vlákna</span><span class="sxs-lookup"><span data-stu-id="7e4aa-115">Using Threads and Threading</span></span>](../../../../standard/threading/using-threads-and-threading.md)  
  
-   [<span data-ttu-id="7e4aa-116">Dělení na spravovaná vlákna osvědčené postupy</span><span class="sxs-lookup"><span data-stu-id="7e4aa-116">Managed Threading Best Practices</span></span>](../../../../standard/threading/managed-threading-best-practices.md)  
  
## <a name="the-lock-keyword"></a><span data-ttu-id="7e4aa-117">Lock – klíčové slovo</span><span class="sxs-lookup"><span data-stu-id="7e4aa-117">The lock Keyword</span></span>  
 <span data-ttu-id="7e4aa-118">C# `lock` příkaz lze použít k zajištění, že blok kódu zcela dokončena bez přerušení jiná vlákna.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-118">The C# `lock` statement can be used to ensure that a block of code runs to completion without interruption by other threads.</span></span> <span data-ttu-id="7e4aa-119">To lze provést po dobu trvání blok kódu získávání zámku vzájemné vyloučení pro daný objekt.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-119">This is accomplished by obtaining a mutual-exclusion lock for a given object for the duration of the code block.</span></span>  
  
 <span data-ttu-id="7e4aa-120">A `lock` příkaz je zadaný objekt jako argument a následuje blok kódu, který se má provádět pouze jedním vláknem současně.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-120">A `lock` statement is given an object as an argument, and is followed by a code block that is to be executed by only one thread at a time.</span></span> <span data-ttu-id="7e4aa-121">Příklad:</span><span class="sxs-lookup"><span data-stu-id="7e4aa-121">For example:</span></span>  
  
```csharp  
public class TestThreading  
{  
    private System.Object lockThis = new System.Object();  
  
    public void Process()  
    {  
  
        lock (lockThis)  
        {  
            // Access thread-sensitive resources.  
        }  
    }  
  
}  
```  
  
 <span data-ttu-id="7e4aa-122">Argument poskytnuté `lock` – klíčové slovo musí být založený na typu odkaz na objekt a slouží k definování oboru zámku.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-122">The argument provided to the `lock` keyword must be an object based on a reference type, and is used to define the scope of the lock.</span></span> <span data-ttu-id="7e4aa-123">V předchozím příkladu obor zámků je omezena na tuto funkci, protože žádné odkazy na objekt `lockThis` existovat mimo funkci.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-123">In the example above, the lock scope is limited to this function because no references to the object `lockThis` exist outside the function.</span></span> <span data-ttu-id="7e4aa-124">Pokud odkazu, by tento objekt rozšířit obor zámků.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-124">If such a reference did exist, lock scope would extend to that object.</span></span> <span data-ttu-id="7e4aa-125">Zadaný objekt přesněji řečeno, slouží výhradně k jednoznačné identifikaci sdílený mezi více vláken, aby ho bylo možné instance třídy libovolný prostředek.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-125">Strictly speaking, the object provided is used solely to uniquely identify the resource being shared among multiple threads, so it can be an arbitrary class instance.</span></span> <span data-ttu-id="7e4aa-126">V praxi ale tento objekt obvykle reprezentuje prostředků, pro které vlákno synchronizace je nezbytné.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-126">In practice, however, this object usually represents the resource for which thread synchronization is necessary.</span></span> <span data-ttu-id="7e4aa-127">Například pokud objektu kontejneru se má používat více vláken, předána kontejneru k uzamčení a synchronizované kód bloku následující zámek by přístup kontejneru.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-127">For example, if a container object is to be used by multiple threads, then the container can be passed to lock, and the synchronized code block following the lock would access the container.</span></span> <span data-ttu-id="7e4aa-128">Tak dlouho, dokud jiná vlákna zamkne ve stejném obsahuje před přístupem k, pak je přístup k objektu bezpečně synchronizován.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-128">As long as other threads locks on the same contain before accessing it, then access to the object is safely synchronized.</span></span>  
  
 <span data-ttu-id="7e4aa-129">Obecně je vyhýbat se na zamykání `public` typ, nebo na instancí objektů mimo kontrolu vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-129">Generally, it is best to avoid locking on a `public` type, or on object instances beyond the control of your application.</span></span> <span data-ttu-id="7e4aa-130">Například `lock(this)` může být problematické, pokud instance je přístupná veřejně, protože kód mimo vaši kontrolu může zamknout na objekt i.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-130">For example, `lock(this)` can be problematic if the instance can be accessed publicly, because code beyond your control may lock on the object as well.</span></span> <span data-ttu-id="7e4aa-131">To může vytvořit zablokování situacích, kde dva nebo více podprocesů čeká na uvolnění výskyty stejného objektu.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-131">This could create deadlock situations where two or more threads wait for the release of the same object.</span></span> <span data-ttu-id="7e4aa-132">Uzamčení na veřejné datového typu, na rozdíl od objektu, může způsobit problémy ze stejného důvodu.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-132">Locking on a public data type, as opposed to an object, can cause problems for the same reason.</span></span> <span data-ttu-id="7e4aa-133">Uzamčení na řetězcové literály je obzvláště rizikové, protože řetězcové literály *interned* modulem common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7e4aa-133">Locking on literal strings is especially risky because literal strings are *interned* by the common language runtime (CLR).</span></span> <span data-ttu-id="7e4aa-134">To znamená, že jednu instanci libovolný daný řetězec je literál pro celý program, přesně stejný objekt představuje literál ve všech systémem všechna vlákna aplikační domény.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-134">This means that there is one instance of any given string literal for the entire program, the exact same object represents the literal in all running application domains, on all threads.</span></span> <span data-ttu-id="7e4aa-135">V důsledku toho uzamknout řetězec se stejným obsahem, kdekoli v procesu uzamčení aplikace všechny instance tento řetězec v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-135">As a result, a lock placed on a string with the same contents anywhere in the application process locks all instances of that string in the application.</span></span> <span data-ttu-id="7e4aa-136">V důsledku toho je vhodné zamknout privátní nebo chráněného člena, který není interned.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-136">As a result, it is best to lock a private or protected member that is not interned.</span></span> <span data-ttu-id="7e4aa-137">Některé třídy poskytují členy, konkrétně k uzamčení.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-137">Some classes provide members specifically for locking.</span></span> <span data-ttu-id="7e4aa-138"><xref:System.Array> Typu, například poskytuje <xref:System.Array.SyncRoot%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-138">The <xref:System.Array> type, for example, provides <xref:System.Array.SyncRoot%2A>.</span></span> <span data-ttu-id="7e4aa-139">Zadejte mnoho typů kolekce `SyncRoot` také člen.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-139">Many collection types provide a `SyncRoot` member as well.</span></span>  
  
 <span data-ttu-id="7e4aa-140">Další informace o `lock` příkaz, naleznete v následujících tématech:</span><span class="sxs-lookup"><span data-stu-id="7e4aa-140">For more information about the `lock` statement, see the following topics:</span></span>  
  
-   [<span data-ttu-id="7e4aa-141">Lock – příkaz</span><span class="sxs-lookup"><span data-stu-id="7e4aa-141">lock Statement</span></span>](../../../../csharp/language-reference/keywords/lock-statement.md)  
  
-   <xref:System.Threading.Monitor>  
  
## <a name="monitors"></a><span data-ttu-id="7e4aa-142">Sledování</span><span class="sxs-lookup"><span data-stu-id="7e4aa-142">Monitors</span></span>  
 <span data-ttu-id="7e4aa-143">Podobně jako `lock` – klíčové slovo, monitorování zabránit bloky kódu ze současné spuštění více vláken.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-143">Like the `lock` keyword, monitors prevent blocks of code from simultaneous execution by multiple threads.</span></span> <span data-ttu-id="7e4aa-144"><xref:System.Threading.Monitor.Enter%2A> Metoda umožňuje pouze jednu vlákno pokračujte do následující příkazy; jiná vlákna jsou blokována až provádění vlákna volání <xref:System.Threading.Monitor.Exit%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-144">The <xref:System.Threading.Monitor.Enter%2A> method allows one and only one thread to proceed into the following statements; all other threads are blocked until the executing thread calls <xref:System.Threading.Monitor.Exit%2A>.</span></span> <span data-ttu-id="7e4aa-145">Toto je stejně jako pomocí `lock` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-145">This is just like using the `lock` keyword.</span></span> <span data-ttu-id="7e4aa-146">Příklad:</span><span class="sxs-lookup"><span data-stu-id="7e4aa-146">For example:</span></span>  
  
```csharp  
lock (x)  
{  
    DoSomething();  
}  
```  
  
 <span data-ttu-id="7e4aa-147">Jde o ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="7e4aa-147">This is equivalent to:</span></span>  
  
```csharp  
System.Object obj = (System.Object)x;  
System.Threading.Monitor.Enter(obj);  
try  
{  
    DoSomething();  
}  
finally  
{  
    System.Threading.Monitor.Exit(obj);  
}  
```  
  
 <span data-ttu-id="7e4aa-148">Pomocí `lock` – klíčové slovo je obecně upřednostňované oproti použití <xref:System.Threading.Monitor> přímo třídu, jak protože `lock` je přesnější a protože `lock` zajistí, že základní monitorování vydání, i když chráněný kód vyvolá došlo k výjimce.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-148">Using the `lock` keyword is generally preferred over using the <xref:System.Threading.Monitor> class directly, both because `lock` is more concise, and because `lock` insures that the underlying monitor is released, even if the protected code throws an exception.</span></span> <span data-ttu-id="7e4aa-149">To je provedeno pomocí `finally` – klíčové slovo, které se provádí jeho přidružený kód bloku bez ohledu na to, jestli je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-149">This is accomplished with the `finally` keyword, which executes its associated code block regardless of whether an exception is thrown.</span></span>  
  
## <a name="synchronization-events-and-wait-handles"></a><span data-ttu-id="7e4aa-150">Synchronizace události a obslužné rutiny čekání</span><span class="sxs-lookup"><span data-stu-id="7e4aa-150">Synchronization Events and Wait Handles</span></span>  
 <span data-ttu-id="7e4aa-151">Pomocí uzamčení nebo monitorování jsou užitečné pro zabránění souběžné spouštění citlivé na vlákno bloky kódu, ale tyto konstrukce neumožňují jedno vlákno pro komunikaci událost do jiného.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-151">Using a lock or monitor is useful for preventing the simultaneous execution of thread-sensitive blocks of code, but these constructs do not allow one thread to communicate an event to another.</span></span> <span data-ttu-id="7e4aa-152">To vyžaduje *synchronizace události*, které jsou objekty, které mají mezi dvěma stavy, signalizovaného a zrušení signalizovaného, který lze použít k aktivaci a pozastavení vláken.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-152">This requires *synchronization events*, which are objects that have one of two states, signaled and un-signaled, that can be used to activate and suspend threads.</span></span> <span data-ttu-id="7e4aa-153">Vlákna pozastavil prováděné pro čekání na událost synchronizace, která je unsignaled a může být aktivováno změnou stavu událostí na signál.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-153">Threads can be suspended by being made to wait on a synchronization event that is unsignaled, and can be activated by changing the event state to signaled.</span></span> <span data-ttu-id="7e4aa-154">Pokud pro čekání na událost, která již signalizace pokusů o vlákno, vlákno pokračuje bez nutnosti zpoždění.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-154">If a thread attempts to wait on an event that is already signaled, then the thread continues to execute without delay.</span></span>  
  
 <span data-ttu-id="7e4aa-155">Existují dva typy událostí synchronizace: <xref:System.Threading.AutoResetEvent>, a <xref:System.Threading.ManualResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-155">There are two kinds of synchronization events: <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.ManualResetEvent>.</span></span> <span data-ttu-id="7e4aa-156">Liší se pouze v tom, že <xref:System.Threading.AutoResetEvent> změny z signál na unsignaled automaticky vždycky, když se aktivuje vlákna.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-156">They differ only in that <xref:System.Threading.AutoResetEvent> changes from signaled to unsignaled automatically any time it activates a thread.</span></span> <span data-ttu-id="7e4aa-157">Naopak <xref:System.Threading.ManualResetEvent> umožňuje libovolný počet vláken, které chcete aktivovat podle jeho signalizovaného stavu a obnoví jenom se unsignaled stavu při jeho <xref:System.Threading.EventWaitHandle.Reset%2A> metoda je volána.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-157">Conversely, a <xref:System.Threading.ManualResetEvent> allows any number of threads to be activated by its signaled state, and will only revert to an unsignaled state when its <xref:System.Threading.EventWaitHandle.Reset%2A> method is called.</span></span>  
  
 <span data-ttu-id="7e4aa-158">Vláken můžete provedeny pro čekání na události ve volání jedné z metod čekání, jako například <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, nebo <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-158">Threads can be made to wait on events by calling one of the wait methods, such as <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, or <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span> <span data-ttu-id="7e4aa-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>způsobí, že podproces Počkejte, dokud se změní na signál, jedna událost, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> blokuje vlákno, dokud jeden nebo více událostí uvedené stát signál, a <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> blokuje vlákno, dokud všechny uvedené události stane signál.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType> causes the thread to wait until a single event becomes signaled, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> blocks a thread until one or more indicated events become signaled, and <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> blocks the thread until all of the indicated events become signaled.</span></span> <span data-ttu-id="7e4aa-160">Událost se změní na signál, když jeho <xref:System.Threading.EventWaitHandle.Set%2A> metoda je volána.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-160">An event becomes signaled when its <xref:System.Threading.EventWaitHandle.Set%2A> method is called.</span></span>  
  
 <span data-ttu-id="7e4aa-161">V následujícím příkladu se vytvoří a spustí vlákna `Main` funkce.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-161">In the following example, a thread is created and started by the `Main` function.</span></span> <span data-ttu-id="7e4aa-162">Nové vlákno čeká na k událost pomocí <xref:System.Threading.WaitHandle.WaitOne%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-162">The new thread waits on an event using the <xref:System.Threading.WaitHandle.WaitOne%2A> method.</span></span> <span data-ttu-id="7e4aa-163">Vlákno je pozastaveno, dokud se změní na událost signál primární podprocesem, který spouští `Main` funkce.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-163">The thread is suspended until the event becomes signaled by the primary thread that is executing the `Main` function.</span></span> <span data-ttu-id="7e4aa-164">Jakmile bude signál události, vrátí pomocného vlákno.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-164">Once the event becomes signaled, the auxiliary thread returns.</span></span> <span data-ttu-id="7e4aa-165">V takovém případě protože události se používá pouze pro jedno vlákno aktivace buď <xref:System.Threading.AutoResetEvent> nebo <xref:System.Threading.ManualResetEvent> třídy by bylo možné použít.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-165">In this case, because the event is only used for one thread activation, either the <xref:System.Threading.AutoResetEvent> or <xref:System.Threading.ManualResetEvent> classes could be used.</span></span>  
  
```csharp  
using System;  
using System.Threading;  
  
class ThreadingExample  
{  
    static AutoResetEvent autoEvent;  
  
    static void DoWork()  
    {  
        Console.WriteLine("   worker thread started, now waiting on event...");  
        autoEvent.WaitOne();  
        Console.WriteLine("   worker thread reactivated, now exiting...");  
    }  
  
    static void Main()  
    {  
        autoEvent = new AutoResetEvent(false);  
  
        Console.WriteLine("main thread starting worker thread...");  
        Thread t = new Thread(DoWork);  
        t.Start();  
  
        Console.WriteLine("main thread sleeping for 1 second...");  
        Thread.Sleep(1000);  
  
        Console.WriteLine("main thread signaling worker thread...");  
        autoEvent.Set();  
    }  
}  
```  
  
## <a name="mutex-object"></a><span data-ttu-id="7e4aa-166">Objekt mutex</span><span class="sxs-lookup"><span data-stu-id="7e4aa-166">Mutex Object</span></span>  
 <span data-ttu-id="7e4aa-167">A *mutex* je podobná monitorování; zabraňuje souběžných spuštění bloku kódu ve více než jedno vlákno najednou.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-167">A *mutex* is similar to a monitor; it prevents the simultaneous execution of a block of code by more than one thread at a time.</span></span> <span data-ttu-id="7e4aa-168">Ve skutečnosti název "mutex" je zkrácený tvar termín "vzájemně vylučují."</span><span class="sxs-lookup"><span data-stu-id="7e4aa-168">In fact, the name "mutex" is a shortened form of the term "mutually exclusive."</span></span> <span data-ttu-id="7e4aa-169">Na rozdíl od monitorování ale mutex slouží k synchronizaci vláken napříč procesy.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-169">Unlike monitors, however, a mutex can be used to synchronize threads across processes.</span></span> <span data-ttu-id="7e4aa-170">Mutex je reprezentována <xref:System.Threading.Mutex> třídy.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-170">A mutex is represented by the <xref:System.Threading.Mutex> class.</span></span>  
  
 <span data-ttu-id="7e4aa-171">Pokud se použije pro synchronizace mezi procesy, se nazývá mutex *pojmenovaný vzájemně vyloučený přístup* vzhledem k tomu, že je pro použití v jiné aplikaci, a proto nemohou být sdíleny prostřednictvím globální nebo statické proměnné.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-171">When used for inter-process synchronization, a mutex is called a *named mutex* because it is to be used in another application, and therefore it cannot be shared by means of a global or static variable.</span></span> <span data-ttu-id="7e4aa-172">Je nutné mít název, aby obě aplikace přístup na stejný objekt mutex.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-172">It must be given a name so that both applications can access the same mutex object.</span></span>  
  
 <span data-ttu-id="7e4aa-173">Mutex lze pro synchronizace uvnitř zpracování vláken, ale pomocí <xref:System.Threading.Monitor> je obecně upřednostňované, protože monitorování byly navrženy speciálně pro rozhraní .NET Framework a proto lépe využívat zdroje.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-173">Although a mutex can be used for intra-process thread synchronization, using <xref:System.Threading.Monitor> is generally preferred, because monitors were designed specifically for the .NET Framework and therefore make better use of resources.</span></span> <span data-ttu-id="7e4aa-174">Naopak <xref:System.Threading.Mutex> třída je obálka pro Win32 konstrukce.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-174">In contrast, the <xref:System.Threading.Mutex> class is a wrapper to a Win32 construct.</span></span> <span data-ttu-id="7e4aa-175">I když je mnohem snazší než monitorování, mutex vyžaduje spolupráce přechody, které jsou výpočetně nákladné než ty, které vyžadují <xref:System.Threading.Monitor> třídy.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-175">While it is more powerful than a monitor, a mutex requires interop transitions that are more computationally expensive than those required by the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="7e4aa-176">Příklad použití mutex, naleznete v části [mutex – třídy](../../../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="7e4aa-176">For an example of using a mutex, see [Mutexes](../../../../standard/threading/mutexes.md).</span></span>  
  
## <a name="interlocked-class"></a><span data-ttu-id="7e4aa-177">Interlocked – třída</span><span class="sxs-lookup"><span data-stu-id="7e4aa-177">Interlocked Class</span></span>  
 <span data-ttu-id="7e4aa-178">Můžete použít metody <xref:System.Threading.Interlocked> třídy, aby problémy, ke kterým dochází při pokusu o několik vláken současně aktualizovat nebo porovnat stejnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-178">You can use the methods of the <xref:System.Threading.Interlocked> class to prevent problems that can occur when multiple threads attempt to simultaneously update or compare the same value.</span></span> <span data-ttu-id="7e4aa-179">Metody této třídy vám umožní bezpečně přírůstek, snížení, exchange a porovnání hodnot z libovolného vlákna.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-179">The methods of this class let you safely increment, decrement, exchange, and compare values from any thread.</span></span>  
  
## <a name="readerwriter-locks"></a><span data-ttu-id="7e4aa-180">Zámky ReaderWriter</span><span class="sxs-lookup"><span data-stu-id="7e4aa-180">ReaderWriter Locks</span></span>  
 <span data-ttu-id="7e4aa-181">V některých případech můžete chtít uzamknout prostředek jenom v případě, že zapisuje data a povolit více klientů současně číst data, je-li data není aktualizován.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-181">In some cases, you may want to lock a resource only when data is being written and permit multiple clients to simultaneously read data when data is not being updated.</span></span> <span data-ttu-id="7e4aa-182"><xref:System.Threading.ReaderWriterLock> Třída vynucuje výhradní přístup k prostředku vlákno upravuje prostředek, ale nikoli výhradní přístup umožňuje při čtení prostředku.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-182">The <xref:System.Threading.ReaderWriterLock> class enforces exclusive access to a resource while a thread is modifying the resource, but it allows non-exclusive access when reading the resource.</span></span> <span data-ttu-id="7e4aa-183">Zámky ReaderWriter jsou užitečné alternativou k výhradní zámek, které způsobují jiná vlákna počkat, i když tyto vláken není potřeba aktualizovat data.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-183">ReaderWriter locks are a useful alternative to exclusive locks, which cause other threads to wait, even when those threads do not need to update data.</span></span>  
  
## <a name="deadlocks"></a><span data-ttu-id="7e4aa-184">Zablokování</span><span class="sxs-lookup"><span data-stu-id="7e4aa-184">Deadlocks</span></span>  
 <span data-ttu-id="7e4aa-185">Synchronizace vláken je velice užitečné v vícevláknové aplikace, ale je vždy nebezpečí vytváření `deadlock`, kde více vláken, které čekají na sebe navzájem a aplikace se dodává zastavení.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-185">Thread synchronization is invaluable in multithreaded applications, but there is always the danger of creating a `deadlock`, where multiple threads are waiting for each other and the application comes to a halt.</span></span> <span data-ttu-id="7e4aa-186">Zablokování se podobá k situaci, ve kterém jsou zastaveny automobilů na čtyři způsob zastavení a každá osoba čekání na další přejdete.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-186">A deadlock is analogous to a situation in which cars are stopped at a four-way stop and each person is waiting for the other to go.</span></span> <span data-ttu-id="7e4aa-187">Zamezení zablokování je důležité. klíč je pečlivé plánování.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-187">Avoiding deadlocks is important; the key is careful planning.</span></span> <span data-ttu-id="7e4aa-188">Zablokování situacích můžete často předvídání podle diagramů vícevláknové aplikace před zahájením kódování.</span><span class="sxs-lookup"><span data-stu-id="7e4aa-188">You can often predict deadlock situations by diagramming multithreaded applications before you start coding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4aa-189">Viz také</span><span class="sxs-lookup"><span data-stu-id="7e4aa-189">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.WaitHandle.WaitOne%2A>  
 <xref:System.Threading.WaitHandle.WaitAny%2A>  
 <xref:System.Threading.WaitHandle.WaitAll%2A>  
 <xref:System.Threading.Thread.Join%2A>  
 <xref:System.Threading.Thread.Start%2A>  
 <xref:System.Threading.Thread.Sleep%2A>  
 <xref:System.Threading.Monitor>  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading>  
 <xref:System.Threading.EventWaitHandle.Set%2A>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="7e4aa-190">Vícevláknové aplikace (C#)</span><span class="sxs-lookup"><span data-stu-id="7e4aa-190">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="7e4aa-191">Lock – příkaz</span><span class="sxs-lookup"><span data-stu-id="7e4aa-191">lock Statement</span></span>](../../../../csharp/language-reference/keywords/lock-statement.md)  
 [<span data-ttu-id="7e4aa-192">Mutex – třídy</span><span class="sxs-lookup"><span data-stu-id="7e4aa-192">Mutexes</span></span>](../../../../standard/threading/mutexes.md)  
 [<span data-ttu-id="7e4aa-193">Propojené operace</span><span class="sxs-lookup"><span data-stu-id="7e4aa-193">Interlocked Operations</span></span>](../../../../standard/threading/interlocked-operations.md)  
 [<span data-ttu-id="7e4aa-194">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="7e4aa-194">AutoResetEvent</span></span>](../../../../standard/threading/autoresetevent.md)  
 [<span data-ttu-id="7e4aa-195">Synchronizace dat pro Multithreading</span><span class="sxs-lookup"><span data-stu-id="7e4aa-195">Synchronizing Data for Multithreading</span></span>](../../../../standard/threading/synchronizing-data-for-multithreading.md)