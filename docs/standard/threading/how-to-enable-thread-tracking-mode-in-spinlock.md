---
title: "Postupy: Povolení režimu sledování vláken ve struktuře SpinLock"
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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f3d5b40f1f7b4b7534a44f4f7ab542d33d373702
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>Postupy: Povolení režimu sledování vláken ve struktuře SpinLock
<xref:System.Threading.SpinLock?displayProperty=nameWithType>je uzamčen nízké úrovně vzájemné vyloučení, který můžete použít pro scénáře, které mají velmi krátké čekací doby. <xref:System.Threading.SpinLock>není vícenásobně. Po vlákno zadá zámek, se musí zámek správně ukončit, než můžete znovu zadat. Obvykle pokusy o znovu zadat zámek způsobí zablokování a blokování může být velmi obtížné ladění. Jako pomůcku při vývoji <xref:System.Threading.SpinLock?displayProperty=nameWithType> podporuje režimu sledování vláken, které způsobí výjimku vyvolána, pokud se pokusí znovu zadat zámku, která již obsahuje vlákna. To umožňuje více snadno najít bod, kdy nebyl správně opustil zámek. Můžete zapnout na režimu sledování vláken pomocí <xref:System.Threading.SpinLock> konstruktor, který přebírá logickou hodnotu vstupní parametr a předávání argument `true`. Po dokončení vývoj a testování fáze, vypněte režimu sledování vláken pro dosažení vyššího výkonu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje režimu sledování vláken. Řádky, které správně ukončit zámek jsou vloženy do komentáře k simulaci kódování chyba, která způsobí, že jeden z následující výsledky:  
  
-   Pokud je vyvolána výjimka <xref:System.Threading.SpinLock> byla vytvořena pomocí argument `true` (`True` v jazyce Visual Basic).  
  
-   Zablokování, pokud <xref:System.Threading.SpinLock> byla vytvořena pomocí argument `false` (`False` v jazyce Visual Basic).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>Viz také  
 [SpinLock](../../../docs/standard/threading/spinlock.md)
