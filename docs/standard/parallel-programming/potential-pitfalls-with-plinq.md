---
title: "Potenciální nástrahy PLINQ"
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
helpviewer_keywords: PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7c971d2c039e6441669108e966eba472819fde5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="potential-pitfalls-with-plinq"></a><span data-ttu-id="614f4-102">Potenciální nástrahy PLINQ</span><span class="sxs-lookup"><span data-stu-id="614f4-102">Potential Pitfalls with PLINQ</span></span>
<span data-ttu-id="614f4-103">V mnoha případech můžete PLINQ poskytují významné zlepšení výkonu přes sekvenčních LINQ na objekty dotazy.</span><span class="sxs-lookup"><span data-stu-id="614f4-103">In many cases, PLINQ can provide significant performance improvements over sequential LINQ to Objects queries.</span></span> <span data-ttu-id="614f4-104">Vytváření paralelních dotazů však zavádí složitost, který může vést k problémům, které v sekvenčních kódu nejsou jako běžné nebo nejsou vůbec došlo.</span><span class="sxs-lookup"><span data-stu-id="614f4-104">However, the work of parallelizing the query execution introduces complexity that can lead to problems that, in sequential code, are not as common or are not encountered at all.</span></span> <span data-ttu-id="614f4-105">Toto téma uvádí některé postupy, abyste se vyhnuli při psaní PLINQ dotazů.</span><span class="sxs-lookup"><span data-stu-id="614f4-105">This topic lists some practices to avoid when you write PLINQ queries.</span></span>  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a><span data-ttu-id="614f4-106">Nepředpokládejte, že paralelní, není vždy rychlejší</span><span class="sxs-lookup"><span data-stu-id="614f4-106">Do Not Assume That Parallel Is Always Faster</span></span>  
 <span data-ttu-id="614f4-107">Někdy paralelizace způsobí, že dotazu PLINQ spustit něco pomalejší než jeho LINQ na objekty ekvivalentní.</span><span class="sxs-lookup"><span data-stu-id="614f4-107">Parallelization sometimes causes a PLINQ query to run slower than its LINQ to Objects equivalent.</span></span> <span data-ttu-id="614f4-108">Základní pravidlem je, že jsou dotazy, které mají několik zdrojové elementy a rychlé uživatelské delegáty mnohem není možné příliš.</span><span class="sxs-lookup"><span data-stu-id="614f4-108">The basic rule of thumb is that queries that have few source elements and fast user delegates are unlikely to speedup much.</span></span> <span data-ttu-id="614f4-109">Ale protože výkonu mnoho faktorů, doporučujeme změřit skutečné výsledky, než se rozhodnete, jestli se má použít PLINQ.</span><span class="sxs-lookup"><span data-stu-id="614f4-109">However, because many factors are involved in performance, we recommend that you measure actual results before you decide whether to use PLINQ.</span></span> <span data-ttu-id="614f4-110">Další informace najdete v tématu [porozumění zrychlení v PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="614f4-110">For more information, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="avoid-writing-to-shared-memory-locations"></a><span data-ttu-id="614f4-111">Vyhněte se zápis do umístění sdílené paměti</span><span class="sxs-lookup"><span data-stu-id="614f4-111">Avoid Writing to Shared Memory Locations</span></span>  
 <span data-ttu-id="614f4-112">V sekvenčních kódu není z číst nebo zapisovat na statické proměnné nebo třída polí.</span><span class="sxs-lookup"><span data-stu-id="614f4-112">In sequential code, it is not uncommon to read from or write to static variables or class fields.</span></span> <span data-ttu-id="614f4-113">Vždy, když souběžně několik vláken přistupují takovéto proměnné, je však vysoká pravděpodobnost časování.</span><span class="sxs-lookup"><span data-stu-id="614f4-113">However, whenever multiple threads are accessing such variables concurrently, there is a big potential for race conditions.</span></span> <span data-ttu-id="614f4-114">I když používáte zámky synchronizovat přístup k proměnné náklady na synchronizace může narušit výkonnost.</span><span class="sxs-lookup"><span data-stu-id="614f4-114">Even though you can use locks to synchronize access to the variable, the cost of synchronization can hurt performance.</span></span> <span data-ttu-id="614f4-115">Proto doporučujeme můžete vyhnout, nebo alespoň omezit přístup ke sdílenému stavu v PLINQ dotazu co nejvíc.</span><span class="sxs-lookup"><span data-stu-id="614f4-115">Therefore, we recommend that you avoid, or at least limit, access to shared state in a PLINQ query as much as possible.</span></span>  
  
## <a name="avoid-over-parallelization"></a><span data-ttu-id="614f4-116">Vyhněte se nadbytečnému</span><span class="sxs-lookup"><span data-stu-id="614f4-116">Avoid Over-Parallelization</span></span>  
 <span data-ttu-id="614f4-117">Pomocí `AsParallel` operátor, způsobit režijní náklady na vytváření oddílů zdrojové kolekci a synchronizaci pracovních vláken.</span><span class="sxs-lookup"><span data-stu-id="614f4-117">By using the `AsParallel` operator, you incur the overhead costs of partitioning the source collection and synchronizing the worker threads.</span></span> <span data-ttu-id="614f4-118">Výhody paralelního zpracování jsou další omezen počet procesorů v počítači.</span><span class="sxs-lookup"><span data-stu-id="614f4-118">The benefits of parallelization are further limited by the number of processors on the computer.</span></span> <span data-ttu-id="614f4-119">Neexistuje žádné zrychlení užitečného spuštěním několika výpočetních vláken na počítače s více procesory.</span><span class="sxs-lookup"><span data-stu-id="614f4-119">There is no speedup to be gained by running multiple compute-bound threads on just one processor.</span></span> <span data-ttu-id="614f4-120">Proto musí být pozor, abyste přepsání paralelní dotaz.</span><span class="sxs-lookup"><span data-stu-id="614f4-120">Therefore, you must be careful not to over-parallelize a query.</span></span>  
  
 <span data-ttu-id="614f4-121">Nejběžnější scénáře v nadbytečného paralelního zpracování může dojít, je ve vnořené dotazy, jak je znázorněno v následujícím fragmentu kódu.</span><span class="sxs-lookup"><span data-stu-id="614f4-121">The most common scenario in which over-parallelization can occur is in nested queries, as shown in the following snippet.</span></span>  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 <span data-ttu-id="614f4-122">V takovém případě je nejlepší učinit paralelní pouze vnější zdroji dat (zákazníci), pokud jeden nebo více z následujících podmínek:</span><span class="sxs-lookup"><span data-stu-id="614f4-122">In this case, it is best to parallelize only the outer data source (customers) unless one or more of the following conditions apply:</span></span>  
  
-   <span data-ttu-id="614f4-123">Zdroj dat vnitřní (položka zákazníka. Objednávky) je znám trvat velmi dlouho.</span><span class="sxs-lookup"><span data-stu-id="614f4-123">The inner data source (cust.Orders) is known to be very long.</span></span>  
  
-   <span data-ttu-id="614f4-124">V každé pořadí jsou prováděny nákladné výpočty.</span><span class="sxs-lookup"><span data-stu-id="614f4-124">You are performing an expensive computation on each order.</span></span> <span data-ttu-id="614f4-125">(Operace v příkladu není nákladné.)</span><span class="sxs-lookup"><span data-stu-id="614f4-125">(The operation shown in the example is not expensive.)</span></span>  
  
-   <span data-ttu-id="614f4-126">Cílový systém se označuje má dostatek procesorů pro zpracování počet vláken, které budou vytvořeny paralelním prováděním dotaz na `cust.Orders`.</span><span class="sxs-lookup"><span data-stu-id="614f4-126">The target system is known to have enough processors to handle the number of threads that will be produced by parallelizing the query on `cust.Orders`.</span></span>  
  
 <span data-ttu-id="614f4-127">Ve všech případech je nejlepší způsob, jak určit optimální tvar dotazu pro testování a měření.</span><span class="sxs-lookup"><span data-stu-id="614f4-127">In all cases, the best way to determine the optimum query shape is to test and measure.</span></span> <span data-ttu-id="614f4-128">Další informace najdete v tématu [postupy: měření výkonu dotazu PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span><span class="sxs-lookup"><span data-stu-id="614f4-128">For more information, see [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span></span>  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a><span data-ttu-id="614f4-129">Vyhněte se volání metody není bezpečná pro přístup z více vláken</span><span class="sxs-lookup"><span data-stu-id="614f4-129">Avoid Calls to Non-Thread-Safe Methods</span></span>  
 <span data-ttu-id="614f4-130">Zápis metod není bezpečná pro přístup z více vláken, které PLINQ dotazu může vést k poškození dat, který může nebo nemusí být v programu.</span><span class="sxs-lookup"><span data-stu-id="614f4-130">Writing to non-thread-safe instance methods from a PLINQ query can lead to data corruption which may or may not go undetected in your program.</span></span> <span data-ttu-id="614f4-131">Může vést k výjimkám.</span><span class="sxs-lookup"><span data-stu-id="614f4-131">It can also lead to exceptions.</span></span> <span data-ttu-id="614f4-132">V následujícím příkladu by být více vláken pokusit volání `Filestream.Write` metoda současně, což není podporováno v třídě.</span><span class="sxs-lookup"><span data-stu-id="614f4-132">In the following example, multiple threads would be attempting to call the `Filestream.Write` method simultaneously, which is not supported by the class.</span></span>  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a><span data-ttu-id="614f4-133">Limit volání metody bezpečné pro přístup z více vláken</span><span class="sxs-lookup"><span data-stu-id="614f4-133">Limit Calls to Thread-Safe Methods</span></span>  
 <span data-ttu-id="614f4-134">Většina statických metod v rozhraní .NET Framework jsou bezpečné pro přístup z více vláken a lze volat z více vláken současně.</span><span class="sxs-lookup"><span data-stu-id="614f4-134">Most static methods in the .NET Framework are thread-safe and can be called from multiple threads concurrently.</span></span> <span data-ttu-id="614f4-135">I v těchto případech však zapojení synchronizace může vést k významnému zpomalení v dotazu.</span><span class="sxs-lookup"><span data-stu-id="614f4-135">However, even in these cases, the synchronization involved can lead to significant slowdown in the query.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="614f4-136">Můžete vyzkoušet pro tento sami vložením některé volání <xref:System.Console.WriteLine%2A> v dotazech.</span><span class="sxs-lookup"><span data-stu-id="614f4-136">You can test for this yourself by inserting some calls to <xref:System.Console.WriteLine%2A> in your queries.</span></span> <span data-ttu-id="614f4-137">I když tato metoda se používá v příkladech dokumentace pro demonstrační účely, nepoužívejte ji v PLINQ dotazy.</span><span class="sxs-lookup"><span data-stu-id="614f4-137">Although this method is used in the documentation examples for demonstration purposes, do not use it in PLINQ queries.</span></span>  
  
## <a name="avoid-unnecessary-ordering-operations"></a><span data-ttu-id="614f4-138">Vyhněte se nadbytečným operacím řazení</span><span class="sxs-lookup"><span data-stu-id="614f4-138">Avoid Unnecessary Ordering Operations</span></span>  
 <span data-ttu-id="614f4-139">Když PLINQ provede dotaz paralelně, rozdělí zdrojové sekvence na oddíly, které lze provozovat na souběžně na více vláken.</span><span class="sxs-lookup"><span data-stu-id="614f4-139">When PLINQ executes a query in parallel, it divides the source sequence into partitions that can be operated on concurrently on multiple threads.</span></span> <span data-ttu-id="614f4-140">Ve výchozím nastavení, není předvídatelný pořadí, ve kterém oddíly, které se zpracovávají a výsledky se dodávají (s výjimkou operátory, jako například `OrderBy`).</span><span class="sxs-lookup"><span data-stu-id="614f4-140">By default, the order in which the partitions are processed and the results are delivered is not predictable (except for operators such as `OrderBy`).</span></span> <span data-ttu-id="614f4-141">Můžete určit, aby PLINQ zachovat řazení žádné zdrojové sekvence, ale to má negativní dopad na výkon.</span><span class="sxs-lookup"><span data-stu-id="614f4-141">You can instruct PLINQ to preserve the ordering of any source sequence, but this has a negative impact on performance.</span></span> <span data-ttu-id="614f4-142">Osvědčený postup, kdykoli je to možné, je na dotazy, struktura, aby se nespoléhejte na zachování pořadí.</span><span class="sxs-lookup"><span data-stu-id="614f4-142">The best practice, whenever possible, is to structure queries so that they do not rely on order preservation.</span></span> <span data-ttu-id="614f4-143">Další informace najdete v tématu [zachování pořadí v PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="614f4-143">For more information, see [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span></span>  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a><span data-ttu-id="614f4-144">Foreach – Pokud je možné, raději ForAll</span><span class="sxs-lookup"><span data-stu-id="614f4-144">Prefer ForAll to ForEach When It Is Possible</span></span>  
 <span data-ttu-id="614f4-145">I když PLINQ provede dotaz na více vláken, pokud využívat výsledky v `foreach` smyčky (`For Each` v jazyce Visual Basic), pak musí být sloučeny zpět do jednoho vlákna a k sériově pomocí enumerátoru výsledky dotazu.</span><span class="sxs-lookup"><span data-stu-id="614f4-145">Although PLINQ executes a query on multiple threads, if you consume the results in a `foreach` loop (`For Each` in Visual Basic), then the query results must be merged back into one thread and accessed serially by the enumerator.</span></span> <span data-ttu-id="614f4-146">V některých případech je to nevyhnutelné; ale pokud je to možné, použijte `ForAll` způsob povolení každé vlákno výstup vlastních výsledků, například jako zápisem do kolekce bezpečné pro přístup z více vláken <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="614f4-146">In some cases, this is unavoidable; however, whenever possible, use the `ForAll` method to enable each thread to output its own results, for example, by writing to a thread-safe collection such as <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="614f4-147">Stejný problém se vztahuje na <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> jinými slovy, `source.AsParallel().Where().ForAll(...)` by měla být důrazně upřednostňované na</span><span class="sxs-lookup"><span data-stu-id="614f4-147">The same issue applies to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> In other words, `source.AsParallel().Where().ForAll(...)` should be strongly preferred to</span></span>  
  
 <span data-ttu-id="614f4-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span><span class="sxs-lookup"><span data-stu-id="614f4-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span></span>  
  
## <a name="be-aware-of-thread-affinity-issues"></a><span data-ttu-id="614f4-149">Mějte na paměti problémy spřažení podprocesu</span><span class="sxs-lookup"><span data-stu-id="614f4-149">Be Aware of Thread Affinity Issues</span></span>  
 <span data-ttu-id="614f4-150">Některé technologie, například interoperabilita modelů COM pro jedno vláknové objekty Apartment (STA) součásti Windows Forms a Windows Presentation Foundation (WPF) použít omezení na spřažení vláken, které vyžadují spuštění kódu na konkrétní vlákno.</span><span class="sxs-lookup"><span data-stu-id="614f4-150">Some technologies, for example, COM interoperability for Single-Threaded Apartment (STA) components, Windows Forms, and Windows Presentation Foundation (WPF), impose thread affinity restrictions that require code to run on a specific thread.</span></span> <span data-ttu-id="614f4-151">Například ve Windows Forms a WPF ovládacího prvku můžete přistupovat pouze ve vlákně, v němž byla vytvořena.</span><span class="sxs-lookup"><span data-stu-id="614f4-151">For example, in both Windows Forms and WPF, a control can only be accessed on the thread on which it was created.</span></span> <span data-ttu-id="614f4-152">Pokud se pokusíte přístup ke sdílenému stavu ovládacího prvku Windows Forms v PLINQ dotazu, je vyvolána výjimka, pokud používáte v ladicím programu.</span><span class="sxs-lookup"><span data-stu-id="614f4-152">If you try to access the shared state of a Windows Forms control in a PLINQ query, an exception is raised if you are running in the debugger.</span></span> <span data-ttu-id="614f4-153">(Toto nastavení může být vypnuto.) Ale pokud dotaz se využívá v vlákna uživatelského rozhraní, pak dostanete z ovládacího prvku `foreach` smyčky, která se zobrazí dotaz výsledky, protože tento kód je prováděn pouze jedno vlákno.</span><span class="sxs-lookup"><span data-stu-id="614f4-153">(This setting can be turned off.) However, if your query is consumed on the UI thread, then you can access the control from the `foreach` loop that enumerates the query results because that code executes on just one thread.</span></span>  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a><span data-ttu-id="614f4-154">Nepředpokládejte, že iterace ForEach, pro a ForAll vždy provést paralelní</span><span class="sxs-lookup"><span data-stu-id="614f4-154">Do Not Assume that Iterations of ForEach, For and ForAll Always Execute in Parallel</span></span>  
 <span data-ttu-id="614f4-155">Je důležité mít na paměti, že jednotlivé iterace ve <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> nebo <xref:System.Linq.ParallelEnumerable.ForAll%2A> cykly může, ale není nutné provést paralelně.</span><span class="sxs-lookup"><span data-stu-id="614f4-155">It is important to keep in mind that individual iterations in a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> or <xref:System.Linq.ParallelEnumerable.ForAll%2A> loop may but do not have to execute in parallel.</span></span> <span data-ttu-id="614f4-156">Proto byste neměli psaní jakéhokoli kódu, který správnost závisí na paralelní provádění iterací nebo provádění iterací v libovolném pořadí.</span><span class="sxs-lookup"><span data-stu-id="614f4-156">Therefore, you should avoid writing any code that depends for correctness on parallel execution of iterations or on the execution of iterations in any particular order.</span></span>  
  
 <span data-ttu-id="614f4-157">Tento kód je například pravděpodobně dojde k zablokování:</span><span class="sxs-lookup"><span data-stu-id="614f4-157">For example, this code is likely to deadlock:</span></span>  
  
```vb  
Dim mre = New ManualResetEventSlim()  
    Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll(Sub(j)   
  
                                                     If j = Environment.ProcessorCount Then  
  
                                                         Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Set()  
  
                                                     Else  
  
                                                         Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Wait()  
                                                     End If  
    End Sub) ' deadlocks  
```  
  
```csharp  
ManualResetEventSlim mre = new ManualResetEventSlim();  
            Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll((j) =>  
            {  
                if (j == Environment.ProcessorCount)  
                {  
                    Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Set();  
                }  
                else  
                {  
                    Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Wait();  
                }  
            }); //deadlocks  
```  
  
 <span data-ttu-id="614f4-158">V tomto příkladu jedna iterace události a všechny ostatní iterace čekat na události.</span><span class="sxs-lookup"><span data-stu-id="614f4-158">In this example, one iteration sets an event, and all other iterations wait on the event.</span></span> <span data-ttu-id="614f4-159">Žádná z čekajících iterací provést až po dokončení nastavení události iterací.</span><span class="sxs-lookup"><span data-stu-id="614f4-159">None of the waiting iterations can complete until the event-setting iteration has completed.</span></span> <span data-ttu-id="614f4-160">Je však možné, že čekajících iterací blokovat všechna vlákna, které se používají ke spouštění paralelní smyčky před událostí iterace dostal příležitost provést.</span><span class="sxs-lookup"><span data-stu-id="614f4-160">However, it is possible that the waiting iterations block all threads that are used to execute the parallel loop, before the event-setting iteration has had a chance to execute.</span></span> <span data-ttu-id="614f4-161">To vede k zablokování – událost iterace se nikdy neprovede a čekající iterace se nikdy probuzení.</span><span class="sxs-lookup"><span data-stu-id="614f4-161">This results in a deadlock – the event-setting iteration will never execute, and the waiting iterations will never wake up.</span></span>  
  
 <span data-ttu-id="614f4-162">Na konkrétní jeden iterace paralelní smyčky by nikdy čekat na jinou iteraci smyčky pokračovat.</span><span class="sxs-lookup"><span data-stu-id="614f4-162">In particular, one iteration of a parallel loop should never wait on another iteration of the loop to make progress.</span></span> <span data-ttu-id="614f4-163">Pokud se při plánování iterace sekvenčně, ale v opačném pořadí rozhodne paralelní smyčky, dojde k zablokování.</span><span class="sxs-lookup"><span data-stu-id="614f4-163">If the parallel loop decides to schedule the iterations sequentially but in the opposite order, a deadlock will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614f4-164">Viz také</span><span class="sxs-lookup"><span data-stu-id="614f4-164">See Also</span></span>  
 [<span data-ttu-id="614f4-165">Paralelní LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="614f4-165">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)