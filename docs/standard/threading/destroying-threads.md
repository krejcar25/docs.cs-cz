---
title: "Zničení vláken"
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
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3bdacb1cc54e3b67a1b4cef4f9fd274e65037faa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="destroying-threads"></a>Zničení vláken
<xref:System.Threading.Thread.Abort%2A> Metoda se používá k zastavení spravované vlákno trvale. Při volání <xref:System.Threading.Thread.Abort%2A>, vyvolá modul common language runtime <xref:System.Threading.ThreadAbortException> ve vláknu cíl, který může zachytit vlákno cíl. Další informace naleznete v tématu <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Pokud vlákno provádí nespravovaného kódu při jeho <xref:System.Threading.Thread.Abort%2A> metoda je volána, modul runtime označí je <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>. Když se vrátí vlákno do spravovaného kódu, je vyvolána výjimka.  
  
 Jakmile vlákno byl přerušen, nelze ji restartovat.  
  
 <xref:System.Threading.Thread.Abort%2A> Metoda nezpůsobí vlákno k přerušení okamžitě, protože cíl vlákno může zachytit <xref:System.Threading.ThreadAbortException> a provést libovolné množství kód `finally` bloku. Můžete volat <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> Pokud potřebujete Počkejte, dokud vlákno skončila. <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>je blokování volání, která nevrátí dokud vlákno ve skutečnosti byla zastavena, provádění nebo vypršení časového limitu volitelné intervalu. Přerušené vlákno může volat <xref:System.Threading.Thread.ResetAbort%2A> metoda nebo provádět bez vazby zpracování v `finally` blokovat, takže pokud nezadáte vypršení časového limitu, není zaručena čekání na konec.  
  
 Vláken, které čekají na volání <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> metoda může být přerušeny jiná vlákna, které volají <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.  
  
## <a name="handling-threadabortexception"></a>Výjimka ThreadAbortException zpracování  
 Pokud očekáváte, že vaše vlákno přerušení, buď v důsledku volání <xref:System.Threading.Thread.Abort%2A> z vlastního kódu nebo v důsledku uvolnění domény aplikace ve které je spuštěný vlákno (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> používá <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> ukončit vláken), musí vaše podprocesu zpracování <xref:System.Threading.ThreadAbortException> a provést libovolné finální zpracování v `finally` klauzule, jak je znázorněno v následujícím kódu.  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 Vyčištění kód musí být v `catch` klauzule nebo `finally` klauzule, protože <xref:System.Threading.ThreadAbortException> je znovu vyvolány v systému na konci `finally` klauzuli, nebo na konci `catch` klauzule, pokud je žádné `finally` klauzule.  
  
 Můžete zabránit v systému opětné vyvolání výjimky při volání <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> metoda. Ale měli byste udělat tento jenom Pokud vlastní kód způsobila <xref:System.Threading.ThreadAbortException>.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [Použití vláken a dělení na vlákna](../../../docs/standard/threading/using-threads-and-threading.md)
