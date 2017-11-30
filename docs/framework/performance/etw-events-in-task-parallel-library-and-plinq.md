---
title: "Události Trasování událostí pro Windows v knihovně Task Parallel Library a PLINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, ETW events
ms.assetid: 87a9cff5-d86f-4e44-a06e-d12764d0dce2
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9e3ff6c4ec8febda93136c5ac88223b5baf80124
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="etw-events-in-task-parallel-library-and-plinq"></a><span data-ttu-id="ccaec-102">Události Trasování událostí pro Windows v knihovně Task Parallel Library a PLINQ</span><span class="sxs-lookup"><span data-stu-id="ccaec-102">ETW Events in Task Parallel Library and PLINQ</span></span>
<span data-ttu-id="ccaec-103">Knihovně Task Parallel Library a PLINQ generovat události trasování pro Windows (ETW) události, které můžete použít k profilu a řešení potíží s aplikací pomocí nástroje, jako je analyzátor výkonu systému Windows.</span><span class="sxs-lookup"><span data-stu-id="ccaec-103">Both the Task Parallel Library and PLINQ generate Event Trace for Windows (ETW) events that you can use to profile and troubleshoot applications by using tools such as the Windows Performance Analyzer.</span></span> <span data-ttu-id="ccaec-104">Ve většině scénářů, nejlepší způsob, jak kód paralelní aplikace profilu je však používat [vizualizér souběžnosti](/visualstudio/profiling/concurrency-visualizer) v [!INCLUDE[vsUltShort](../../../includes/vsultshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccaec-104">However, in most scenarios, the best way to profile parallel application code is to use the [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer) in [!INCLUDE[vsUltShort](../../../includes/vsultshort-md.md)].</span></span>  
  
## <a name="task-parallel-library-etw-events"></a><span data-ttu-id="ccaec-105">Události trasování událostí pro úlohy Parallel Library</span><span class="sxs-lookup"><span data-stu-id="ccaec-105">Task Parallel Library ETW Events</span></span>  
 <span data-ttu-id="ccaec-106">Ve struktuře EVENT_HEADER ProviderId GUID pro události vygenerované <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> a <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> je:</span><span class="sxs-lookup"><span data-stu-id="ccaec-106">In the EVENT_HEADER structure, the ProviderId GUID for events generated by <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> is:</span></span>  
  
```  
0x2e5dba47, 0xa3d2, 0x4d16, 0x8e, 0xe0, 0x66, 0x71, 0xff, 0xdc, 0xd7, 0xb5  
```  
  
### <a name="parallel-loop-begin"></a><span data-ttu-id="ccaec-107">Začátek paralelní smyčky</span><span class="sxs-lookup"><span data-stu-id="ccaec-107">Parallel Loop Begin</span></span>  
 <span data-ttu-id="ccaec-108">EVENT_DESCRIPTOR. Úloha = 1</span><span class="sxs-lookup"><span data-stu-id="ccaec-108">EVENT_DESCRIPTOR.Task = 1</span></span>  
  
 <span data-ttu-id="ccaec-109">EVENT_DESCRIPTOR. ID = 1</span><span class="sxs-lookup"><span data-stu-id="ccaec-109">EVENT_DESCRIPTOR.Id = 1</span></span>  
  
#### <a name="user-data"></a><span data-ttu-id="ccaec-110">Uživatelská Data</span><span class="sxs-lookup"><span data-stu-id="ccaec-110">User Data</span></span>  
  
|<span data-ttu-id="ccaec-111">**Jméno**</span><span class="sxs-lookup"><span data-stu-id="ccaec-111">**Name**</span></span>|<span data-ttu-id="ccaec-112">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ccaec-112">**Type**</span></span>|<span data-ttu-id="ccaec-113">**Popis**</span><span class="sxs-lookup"><span data-stu-id="ccaec-113">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="ccaec-114">OriginatingTaskSchedulerID</span><span class="sxs-lookup"><span data-stu-id="ccaec-114">OriginatingTaskSchedulerID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-115">ID TaskScheduler, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-115">The ID of the TaskScheduler that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-116">OriginatingTaskID</span><span class="sxs-lookup"><span data-stu-id="ccaec-116">OriginatingTaskID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-117">ID úlohy, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-117">The ID of the task that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-118">ForkJoinContextID</span><span class="sxs-lookup"><span data-stu-id="ccaec-118">ForkJoinContextID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-119">Jedinečný identifikátor, který slouží k určení vnoření a páry pro události se sémantiku rozvětvení/spojení.</span><span class="sxs-lookup"><span data-stu-id="ccaec-119">A unique identifier used to indicate nesting and pairs for events with fork/join semantics.</span></span>|  
|<span data-ttu-id="ccaec-120">Typ operace</span><span class="sxs-lookup"><span data-stu-id="ccaec-120">OperationType</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-121">Určuje typ smyčka:</span><span class="sxs-lookup"><span data-stu-id="ccaec-121">Indicates the type of loop:</span></span><br /><br /> <span data-ttu-id="ccaec-122">1 = ParallelInvoke</span><span class="sxs-lookup"><span data-stu-id="ccaec-122">1 = ParallelInvoke</span></span><br /><br /> <span data-ttu-id="ccaec-123">2 = ParallelFor</span><span class="sxs-lookup"><span data-stu-id="ccaec-123">2 = ParallelFor</span></span><br /><br /> <span data-ttu-id="ccaec-124">3 = ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="ccaec-124">3 = ParallelForEach</span></span>|  
|<span data-ttu-id="ccaec-125">InclusiveFrom</span><span class="sxs-lookup"><span data-stu-id="ccaec-125">InclusiveFrom</span></span>|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="ccaec-126">Výchozí hodnota čítače smyčky</span><span class="sxs-lookup"><span data-stu-id="ccaec-126">The starting value of the loop counter</span></span>|  
|<span data-ttu-id="ccaec-127">ExclusiveTo</span><span class="sxs-lookup"><span data-stu-id="ccaec-127">ExclusiveTo</span></span>|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="ccaec-128">Koncová hodnota čítače smyčky</span><span class="sxs-lookup"><span data-stu-id="ccaec-128">The ending value of the loop counter</span></span>|  
  
### <a name="parallel-loop-end"></a><span data-ttu-id="ccaec-129">Paralelní smyčky End</span><span class="sxs-lookup"><span data-stu-id="ccaec-129">Parallel Loop End</span></span>  
 <span data-ttu-id="ccaec-130">EVENT_DESCRIPTOR. Úloha = 2</span><span class="sxs-lookup"><span data-stu-id="ccaec-130">EVENT_DESCRIPTOR.Task = 2</span></span>  
  
 <span data-ttu-id="ccaec-131">EVENT_DESCRIPTOR. ID = 2</span><span class="sxs-lookup"><span data-stu-id="ccaec-131">EVENT_DESCRIPTOR.Id = 2</span></span>  
  
#### <a name="user-data"></a><span data-ttu-id="ccaec-132">Uživatelská Data</span><span class="sxs-lookup"><span data-stu-id="ccaec-132">User Data</span></span>  
  
|<span data-ttu-id="ccaec-133">**Jméno**</span><span class="sxs-lookup"><span data-stu-id="ccaec-133">**Name**</span></span>|<span data-ttu-id="ccaec-134">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ccaec-134">**Type**</span></span>|<span data-ttu-id="ccaec-135">**Popis**</span><span class="sxs-lookup"><span data-stu-id="ccaec-135">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="ccaec-136">OriginatingTaskSchedulerID</span><span class="sxs-lookup"><span data-stu-id="ccaec-136">OriginatingTaskSchedulerID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-137">ID TaskScheduler, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-137">The ID of the TaskScheduler that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-138">OriginatingTaskID</span><span class="sxs-lookup"><span data-stu-id="ccaec-138">OriginatingTaskID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-139">ID úlohy, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-139">The ID of the task that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-140">ForkJoinContextID</span><span class="sxs-lookup"><span data-stu-id="ccaec-140">ForkJoinContextID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-141">Jedinečný identifikátor, který slouží k určení vnoření a páry pro události se sémantiku rozvětvení/spojení.</span><span class="sxs-lookup"><span data-stu-id="ccaec-141">A unique identifier used to indicate nesting and pairs for events with fork/join semantics.</span></span>|  
|<span data-ttu-id="ccaec-142">totalIterations</span><span class="sxs-lookup"><span data-stu-id="ccaec-142">totalIterations</span></span>|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="ccaec-143">Celkový počet iterací</span><span class="sxs-lookup"><span data-stu-id="ccaec-143">The total number of iterations</span></span>|  
  
### <a name="parallel-invoke-begin"></a><span data-ttu-id="ccaec-144">Paralelní vyvolání začátek</span><span class="sxs-lookup"><span data-stu-id="ccaec-144">Parallel Invoke Begin</span></span>  
 <span data-ttu-id="ccaec-145">EVENT_DESCRIPTOR. Úloha = 3</span><span class="sxs-lookup"><span data-stu-id="ccaec-145">EVENT_DESCRIPTOR.Task = 3</span></span>  
  
 <span data-ttu-id="ccaec-146">EVENT_DESCRIPTOR. ID = 3</span><span class="sxs-lookup"><span data-stu-id="ccaec-146">EVENT_DESCRIPTOR.Id = 3</span></span>  
  
#### <a name="user-data"></a><span data-ttu-id="ccaec-147">Uživatelská Data</span><span class="sxs-lookup"><span data-stu-id="ccaec-147">User Data</span></span>  
  
|<span data-ttu-id="ccaec-148">**Jméno**</span><span class="sxs-lookup"><span data-stu-id="ccaec-148">**Name**</span></span>|<span data-ttu-id="ccaec-149">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ccaec-149">**Type**</span></span>|<span data-ttu-id="ccaec-150">**Popis**</span><span class="sxs-lookup"><span data-stu-id="ccaec-150">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="ccaec-151">OriginatingTaskSchedulerID</span><span class="sxs-lookup"><span data-stu-id="ccaec-151">OriginatingTaskSchedulerID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-152">ID TaskScheduler, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-152">The ID of the TaskScheduler that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-153">OriginatingTaskID</span><span class="sxs-lookup"><span data-stu-id="ccaec-153">OriginatingTaskID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-154">ID úlohy, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-154">The ID of the task that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-155">ForkJoinContextID</span><span class="sxs-lookup"><span data-stu-id="ccaec-155">ForkJoinContextID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-156">Jedinečný identifikátor, který slouží k určení vnoření a páry pro události se sémantiku rozvětvení/spojení.</span><span class="sxs-lookup"><span data-stu-id="ccaec-156">A unique identifier used to indicate nesting and pairs for events with fork/join semantics.</span></span>|  
|<span data-ttu-id="ccaec-157">totalIterations</span><span class="sxs-lookup"><span data-stu-id="ccaec-157">totalIterations</span></span>|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="ccaec-158">Celkový počet iterací</span><span class="sxs-lookup"><span data-stu-id="ccaec-158">The total number of iterations</span></span>|  
|<span data-ttu-id="ccaec-159">Typ operace</span><span class="sxs-lookup"><span data-stu-id="ccaec-159">operationType</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-160">Určuje typ smyčka:</span><span class="sxs-lookup"><span data-stu-id="ccaec-160">Indicates the type of loop:</span></span><br /><br /> <span data-ttu-id="ccaec-161">1 = ParallelInvoke</span><span class="sxs-lookup"><span data-stu-id="ccaec-161">1 = ParallelInvoke</span></span><br /><br /> <span data-ttu-id="ccaec-162">2 = ParallelFor</span><span class="sxs-lookup"><span data-stu-id="ccaec-162">2 = ParallelFor</span></span><br /><br /> <span data-ttu-id="ccaec-163">3 = ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="ccaec-163">3 = ParallelForEach</span></span>|  
|<span data-ttu-id="ccaec-164">ActionCount</span><span class="sxs-lookup"><span data-stu-id="ccaec-164">ActionCount</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-165">Počet akcí, které budou spuštěny v paralelní invoke.</span><span class="sxs-lookup"><span data-stu-id="ccaec-165">The number of actions that will be executed in the parallel invoke.</span></span>|  
  
### <a name="parallel-invoke-end"></a><span data-ttu-id="ccaec-166">Paralelní vyvolání End</span><span class="sxs-lookup"><span data-stu-id="ccaec-166">Parallel Invoke End</span></span>  
 <span data-ttu-id="ccaec-167">EVENT_DESCRIPTOR. Úloha = 4</span><span class="sxs-lookup"><span data-stu-id="ccaec-167">EVENT_DESCRIPTOR.Task = 4</span></span>  
  
 <span data-ttu-id="ccaec-168">EVENT_DESCRIPTOR. ID = 4</span><span class="sxs-lookup"><span data-stu-id="ccaec-168">EVENT_DESCRIPTOR.Id = 4</span></span>  
  
#### <a name="user-data"></a><span data-ttu-id="ccaec-169">Uživatelská Data</span><span class="sxs-lookup"><span data-stu-id="ccaec-169">User Data</span></span>  
  
|<span data-ttu-id="ccaec-170">**Jméno**</span><span class="sxs-lookup"><span data-stu-id="ccaec-170">**Name**</span></span>|<span data-ttu-id="ccaec-171">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ccaec-171">**Type**</span></span>|<span data-ttu-id="ccaec-172">**Popis**</span><span class="sxs-lookup"><span data-stu-id="ccaec-172">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="ccaec-173">OriginatingTaskSchedulerID</span><span class="sxs-lookup"><span data-stu-id="ccaec-173">OriginatingTaskSchedulerID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-174">ID TaskScheduler, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-174">The ID of the TaskScheduler that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-175">OriginatingTaskID</span><span class="sxs-lookup"><span data-stu-id="ccaec-175">OriginatingTaskID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-176">ID úlohy, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-176">The ID of the task that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-177">ForkJoinContextID</span><span class="sxs-lookup"><span data-stu-id="ccaec-177">ForkJoinContextID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-178">Jedinečný identifikátor, který slouží k určení vnoření a páry pro události se sémantiku rozvětvení/spojení.</span><span class="sxs-lookup"><span data-stu-id="ccaec-178">A unique identifier used to indicate nesting and pairs for events with fork/join semantics.</span></span>|  
  
## <a name="plinq-etw-events"></a><span data-ttu-id="ccaec-179">Události trasování událostí pro Windows PLINQ</span><span class="sxs-lookup"><span data-stu-id="ccaec-179">PLINQ ETW Events</span></span>  
 <span data-ttu-id="ccaec-180">EVENT_HEADER. GUID ProviderId pro PLINQ je:</span><span class="sxs-lookup"><span data-stu-id="ccaec-180">The EVENT_HEADER.ProviderId GUID for PLINQ is:</span></span>  
  
```  
0x159eeeec, 0x4a14, 0x4418, 0xa8, 0xfe, 0xfa, 0xab, 0xcd, 0x98, 0x78, 0x87  
```  
  
### <a name="parallel-query-begin"></a><span data-ttu-id="ccaec-181">Začátek paralelního dotazu</span><span class="sxs-lookup"><span data-stu-id="ccaec-181">Parallel Query Begin</span></span>  
 <span data-ttu-id="ccaec-182">EVENT_DESCRIPTOR. Úloha = 1</span><span class="sxs-lookup"><span data-stu-id="ccaec-182">EVENT_DESCRIPTOR.Task = 1</span></span>  
  
 <span data-ttu-id="ccaec-183">EVENT_DESCRIPTOR. ID = 1</span><span class="sxs-lookup"><span data-stu-id="ccaec-183">EVENT_DESCRIPTOR.Id = 1</span></span>  
  
#### <a name="user-data"></a><span data-ttu-id="ccaec-184">Uživatelská Data</span><span class="sxs-lookup"><span data-stu-id="ccaec-184">User Data</span></span>  
  
|<span data-ttu-id="ccaec-185">**Jméno**</span><span class="sxs-lookup"><span data-stu-id="ccaec-185">**Name**</span></span>|<span data-ttu-id="ccaec-186">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ccaec-186">**Type**</span></span>|<span data-ttu-id="ccaec-187">**Popis**</span><span class="sxs-lookup"><span data-stu-id="ccaec-187">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="ccaec-188">OriginatingTaskSchedulerID</span><span class="sxs-lookup"><span data-stu-id="ccaec-188">OriginatingTaskSchedulerID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-189">ID TaskScheduler, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-189">The ID of the TaskScheduler that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-190">OriginatingTaskID</span><span class="sxs-lookup"><span data-stu-id="ccaec-190">OriginatingTaskID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-191">ID úlohy, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-191">The ID of the task that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-192">QueryID</span><span class="sxs-lookup"><span data-stu-id="ccaec-192">QueryID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-193">Dotaz jedinečný identifikátor.</span><span class="sxs-lookup"><span data-stu-id="ccaec-193">A unique query identifier.</span></span>|  
  
### <a name="parallel-query-end"></a><span data-ttu-id="ccaec-194">End paralelního dotazu</span><span class="sxs-lookup"><span data-stu-id="ccaec-194">Parallel Query End</span></span>  
 <span data-ttu-id="ccaec-195">EVENT_DESCRIPTOR. Úloha = 2</span><span class="sxs-lookup"><span data-stu-id="ccaec-195">EVENT_DESCRIPTOR.Task = 2</span></span>  
  
 <span data-ttu-id="ccaec-196">EVENT_DESCRIPTOR. ID = 2</span><span class="sxs-lookup"><span data-stu-id="ccaec-196">EVENT_DESCRIPTOR.Id = 2</span></span>  
  
#### <a name="user-data"></a><span data-ttu-id="ccaec-197">Uživatelská Data</span><span class="sxs-lookup"><span data-stu-id="ccaec-197">User Data</span></span>  
  
|<span data-ttu-id="ccaec-198">**Jméno**</span><span class="sxs-lookup"><span data-stu-id="ccaec-198">**Name**</span></span>|<span data-ttu-id="ccaec-199">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ccaec-199">**Type**</span></span>|<span data-ttu-id="ccaec-200">**Popis**</span><span class="sxs-lookup"><span data-stu-id="ccaec-200">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="ccaec-201">OriginatingTaskSchedulerID</span><span class="sxs-lookup"><span data-stu-id="ccaec-201">OriginatingTaskSchedulerID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-202">ID TaskScheduler, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-202">The ID of the TaskScheduler that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-203">OriginatingTaskID</span><span class="sxs-lookup"><span data-stu-id="ccaec-203">OriginatingTaskID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-204">ID úlohy, který spustil smyčky.</span><span class="sxs-lookup"><span data-stu-id="ccaec-204">The ID of the task that started the loop.</span></span>|  
|<span data-ttu-id="ccaec-205">QueryID</span><span class="sxs-lookup"><span data-stu-id="ccaec-205">QueryID</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ccaec-206">Dotaz jedinečný identifikátor.</span><span class="sxs-lookup"><span data-stu-id="ccaec-206">A unique query identifier.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccaec-207">Viz také</span><span class="sxs-lookup"><span data-stu-id="ccaec-207">See Also</span></span>  
 [<span data-ttu-id="ccaec-208">Události trasování událostí pro Windows v rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ccaec-208">ETW Events in the .NET Framework</span></span>](../../../docs/framework/performance/etw-events.md)  
 [<span data-ttu-id="ccaec-209">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="ccaec-209">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [<span data-ttu-id="ccaec-210">Paralelní LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="ccaec-210">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)