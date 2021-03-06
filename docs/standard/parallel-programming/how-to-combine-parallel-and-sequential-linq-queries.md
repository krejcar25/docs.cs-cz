---
title: "Postupy: Kombinování paralelních a sekvenčních LINQ dotazů"
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 02e3af91525b75df051b73587eb3e7cd8ede5504
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>Postupy: Kombinování paralelních a sekvenčních LINQ dotazů
Tento příklad ukazuje způsob použití <xref:System.Linq.ParallelEnumerable.AsSequential%2A> metoda k vynucení PLINQ postupně zpracovat všechny následné operátory v dotazu. I když je obecně pomalejší než paralelní zpracování sekvenčních, někdy je nezbytné pro správné výsledky.  
  
> [!WARNING]
>  Tento příklad je určený k předvedení využití a nemusí být možné spustit rychleji, než ekvivalentní sekvenčních LINQ na objekty dotazu. Další informace o zrychlení najdete v tématu [porozumění zrychlení v PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje jeden scénář, ve kterém <xref:System.Linq.ParallelEnumerable.AsSequential%2A> je potřeba, a to zachování pořadí, které bylo vytvořeno v předchozí klauzuli dotazu.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Pro zkompilování a spuštění tohoto kódu, vložte jej do [ukázková Data pro PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) projekt, přidejte řádek zavolat metodu z `Main`, a stiskněte klávesu F5.  
  
## <a name="see-also"></a>Viz také  
 [Paralelní LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
