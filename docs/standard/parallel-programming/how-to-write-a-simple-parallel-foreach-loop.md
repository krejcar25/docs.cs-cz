---
title: "Postupy: Zápis jednoduché smyčky Parallel.ForEach"
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
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bb628c0de1f0e4452ae13b5f5ee392084118bea5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Postupy: Zápis jednoduché smyčky Parallel.ForEach
Tento příklad ukazuje, jak používat <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> smyčky umožňující datový paralelismus přes jakoukoli <xref:System.Collections.IEnumerable?displayProperty=nameWithType> nebo <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> zdroj dat.  
  
> [!NOTE]
>  Tato dokumentace používá k definování delegátů v PLINQ výrazy lambda. Pokud nejste obeznámeni s výrazy lambda v jazyce C# nebo Visual Basic, přečtěte si téma [výrazy Lambda v PLINQ a TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Příklad  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 A <xref:System.Threading.Tasks.Parallel.ForEach%2A> smyčky funguje jako <xref:System.Threading.Tasks.Parallel.For%2A> smyčky. Zdrojové kolekci je rozdělena na oddíly a práce je naplánována na více vláken v závislosti na prostředí systému. Více procesorů v systému, tím rychleji paralelní metoda se spouští. Pro některé zdroje kolekcí může být rychlejší, v závislosti na velikosti zdroji a druh pracovní provádí sekvenční smyčky. Další informace o výkonu najdete v tématu [Potenciální nástrahy datového a funkčního paralelismu](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)  
  
 Další informace o paralelních smyčkách naleznete v tématu [postupy: zápis jednoduché smyčky Parallel.For](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).  
  
 Použít <xref:System.Threading.Tasks.Parallel.ForEach%2A> s negenerická kolekce, můžete použít <xref:System.Linq.Enumerable.Cast%2A> metoda rozšíření převést kolekci obecnou kolekci, jak je znázorněno v následujícím příkladu:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 Paralelní LINQ (PLINQ) můžete také použít učinit paralelní zpracování <xref:System.Collections.Generic.IEnumerable%601> datové zdroje. PLINQ umožňuje syntaxí deklarativní dotazu k vyjádření chování smyčky. Další informace najdete v tématu [paralelní LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
  
-   Zkopírujte a vložte tento kód do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 projekt konzolové aplikace.  
  
-   Přidat odkaz na System.Drawing.dll  
  
-   Stisknutím klávesy F5  
  
## <a name="see-also"></a>Viz také  
 [Datový paralelismus](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Paralelní programování](../../../docs/standard/parallel-programming/index.md)  
 [Paralelní LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
