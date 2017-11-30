---
title: "Dělení na spravovaná vlákna"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61cd2317b5690573532af2a25c0b84b1fe136fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading"></a><span data-ttu-id="e8dbf-102">Dělení na spravovaná vlákna</span><span class="sxs-lookup"><span data-stu-id="e8dbf-102">Managed Threading</span></span>
<span data-ttu-id="e8dbf-103">Zda vyvíjíte pro počítače s jeden procesor nebo několik, má vaše aplikace poskytují nejvíce přizpůsobivý interakci s uživatelem, i když aplikaci právě provádí jinou práci.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-103">Whether you are developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="e8dbf-104">Používání více vláken, která je jedním z nejúčinnějších způsobů, jak udržovat aplikace reaguje na uživatele a současně proveďte využití procesoru v mezi nebo i během událostí uživatele.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-104">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="e8dbf-105">Při této části jsou popsány základní koncepty dělení na vlákna, se zaměřuje na spravovaná vlákna koncepty a pomocí spravovaného dělení na vlákna.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-105">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8dbf-106">Počínaje [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], vícevláknové programování je výrazně jednodušší s <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> a <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> třídy, [paralelní LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), nové souběžných kolekce tříd v <xref:System.Collections.Concurrent?displayProperty=nameWithType> obor názvů a nové programovací model, který je založen na konceptu úkolů, nikoli vláken.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-106">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="e8dbf-107">Další informace najdete v tématu [paralelní programování](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="e8dbf-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8dbf-108">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="e8dbf-108">In This Section</span></span>  
 [<span data-ttu-id="e8dbf-109">Dělení na spravovaná vlákna základy</span><span class="sxs-lookup"><span data-stu-id="e8dbf-109">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)  
 <span data-ttu-id="e8dbf-110">Poskytuje přehled spravovaného dělení na vlákna a popisuje použití více vláken.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-110">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="e8dbf-111">Použití vláken a dělení na vlákna</span><span class="sxs-lookup"><span data-stu-id="e8dbf-111">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 <span data-ttu-id="e8dbf-112">Vysvětluje, jak vytvořit a spuštění, pozastavení, obnovení a zrušení vláken.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-112">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="e8dbf-113">Dělení na spravovaná vlákna osvědčené postupy</span><span class="sxs-lookup"><span data-stu-id="e8dbf-113">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="e8dbf-114">Popisuje úrovně synchronizace, jak se vyhnout blokování a konflikty časování, jedním procesorem a počítačů s více procesory a další vláken problémy.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-114">Discusses levels of synchronization, how to avoid deadlocks and race conditions, single-processor and multiprocessor computers, and other threading issues.</span></span>  
  
 [<span data-ttu-id="e8dbf-115">Dělení na vlákna objektů a funkcí</span><span class="sxs-lookup"><span data-stu-id="e8dbf-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 <span data-ttu-id="e8dbf-116">Popisuje spravované třídy, které můžete použít k synchronizaci aktivity vláken a data objektů získat přístup v různých vláknech a poskytuje přehled podprocesy z fondu podprocesů.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-116">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e8dbf-117">Odkaz</span><span class="sxs-lookup"><span data-stu-id="e8dbf-117">Reference</span></span>  
 <xref:System.Threading>  
 <span data-ttu-id="e8dbf-118">Obsahuje třídy pro použití a synchronizace spravovaných vláken.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-118">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="e8dbf-119">Obsahuje třídy kolekce, které jsou bezpečné pro použití s více vlákny.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-119">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="e8dbf-120">Obsahuje třídy pro vytváření a plánování úloh souběžné zpracování.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-120">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e8dbf-121">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="e8dbf-121">Related Sections</span></span>  
 [<span data-ttu-id="e8dbf-122">Aplikační domény</span><span class="sxs-lookup"><span data-stu-id="e8dbf-122">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="e8dbf-123">Poskytuje přehled aplikační domény a jejich použití Common Language Infrastructure.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-123">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="e8dbf-124">Asynchronní I/O soubory</span><span class="sxs-lookup"><span data-stu-id="e8dbf-124">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="e8dbf-125">Popisuje výhody výkonu a základní operace asynchronních vstupně-výstupních operací.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-125">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 [<span data-ttu-id="e8dbf-126">Asynchronní vzor založený na událostech (EAP)</span><span class="sxs-lookup"><span data-stu-id="e8dbf-126">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="e8dbf-127">Poskytuje přehled o asynchronní programování.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-127">Provides an overview of asynchronous programming.</span></span>  
  
 [<span data-ttu-id="e8dbf-128">Asynchronní volání synchronních metod</span><span class="sxs-lookup"><span data-stu-id="e8dbf-128">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="e8dbf-129">Vysvětluje, jak volat metody pro přístup z více vláken pomocí integrovaných funkcí delegáti z fondu podprocesů.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-129">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="e8dbf-130">Paralelní programování</span><span class="sxs-lookup"><span data-stu-id="e8dbf-130">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="e8dbf-131">Popisuje paralelní programování knihoven, které zjednodušují používání více vláken v aplikacích.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-131">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="e8dbf-132">Paralelní LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="e8dbf-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 <span data-ttu-id="e8dbf-133">Popisuje systému pro spuštění dotazů paralelně, abyste mohli využívat více procesorů.</span><span class="sxs-lookup"><span data-stu-id="e8dbf-133">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>