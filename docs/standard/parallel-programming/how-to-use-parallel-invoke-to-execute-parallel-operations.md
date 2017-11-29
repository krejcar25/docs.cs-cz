---
title: "Postupy: Použití Parallel.Invoke k vykonávání paralelních operací"
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
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8a51f180a394c1baa2ecb0620279ea15c62e1edc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="ea2e4-102">Postupy: Použití Parallel.Invoke k vykonávání paralelních operací</span><span class="sxs-lookup"><span data-stu-id="ea2e4-102">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>
<span data-ttu-id="ea2e4-103">Tento příklad ukazuje, jak operace paralelními pomocí <xref:System.Threading.Tasks.Parallel.Invoke%2A> v knihovně Task Parallel Library.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-103">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="ea2e4-104">Na sdílený zdroj dat je třeba udělat tři operace.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-104">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="ea2e4-105">Protože žádná operace, které upraví zdroj, se mohou být provedeny souběžně přehledné způsobem.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-105">Because none of the operations modifies the source, they can be executed in parallel in a straightforward manner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea2e4-106">Tato dokumentace používá k definování delegátů v TPL lambda výrazy.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-106">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="ea2e4-107">Pokud nejste obeznámeni s výrazy lambda v jazyce C# nebo Visual Basic, přečtěte si téma [výrazy Lambda v PLINQ a TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="ea2e4-107">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea2e4-108">Příklad</span><span class="sxs-lookup"><span data-stu-id="ea2e4-108">Example</span></span>  
 [!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
 [!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]  
  
 <span data-ttu-id="ea2e4-109">Všimněte si, že s <xref:System.Threading.Tasks.Parallel.Invoke%2A>, jednoduše express které akce, kterou chcete spustit souběžně a modul runtime zpracovává všechny podrobnosti, včetně změny automaticky počet jader na hostitelském počítači plánování vláken.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-109">Note that with <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>  
  
 <span data-ttu-id="ea2e4-110">Tento příklad parallelizes operace, ne data.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-110">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="ea2e4-111">Alternativní způsob můžete paralelními dotazů LINQ pomocí PLINQ a spouštět dotazy postupně.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-111">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="ea2e4-112">Alternativně můžete může paralelními data pomocí PLINQ.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-112">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="ea2e4-113">Další možností je učinit paralelní dotazy a úlohy.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-113">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="ea2e4-114">I když výsledná režie může snížit výkon na hostitelských počítačích s relativně malý počet procesorů, by měl být nárůst mnohem lepší na počítačích s více procesory.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-114">Although the resulting overhead might degrade performance on host computers with relatively few processors, it would scale much better on computers with many processors.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ea2e4-115">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="ea2e4-115">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ea2e4-116">Zkopírujte a vložte celý příklad do projektu Microsoft Visual Studio 2010 a stisknutím klávesy F5.</span><span class="sxs-lookup"><span data-stu-id="ea2e4-116">Copy and paste the entire example into a Microsoft Visual Studio 2010 project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2e4-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="ea2e4-117">See Also</span></span>  
 [<span data-ttu-id="ea2e4-118">Paralelní programování</span><span class="sxs-lookup"><span data-stu-id="ea2e4-118">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="ea2e4-119">Postupy: zrušení úlohy a její podřízené položky</span><span class="sxs-lookup"><span data-stu-id="ea2e4-119">How to: Cancel a Task and Its Children</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)  
 [<span data-ttu-id="ea2e4-120">Paralelní LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="ea2e4-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)