---
title: "dangerousThreadingAPI – pomocník spravovaného ladění (MDA)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b7c4e7f5612cb6a46f16b6e42327e8430d548e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="dangerousthreadingapi-mda"></a>dangerousThreadingAPI – pomocník spravovaného ladění (MDA)
`dangerousThreadingAPI` Pomocník spravovaného ladění (MDA) se aktivuje při <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> metoda je volána ve vlákně než aktuální vlákno.  
  
## <a name="symptoms"></a>Příznaky  
 Aplikace je reagovat, nebo přestane reagovat po neomezenou dobu. Systém nebo aplikace, data mohou být ponecháno v nepředvídatelném stavu dočasně nebo i po aplikace byla vypnuta. Některé operace nebudou dokončovat podle očekávání.  
  
 Příznaky může odlišovat kvůli náhodnost vyplývajících tento problém.  
  
## <a name="cause"></a>příčina  
 Vlákno je pozastaveno asynchronně pomocí jiné vlákno <xref:System.Threading.Thread.Suspend%2A> metoda. Neexistuje žádný způsob, jak zjistit, kdy je bezpečné pozastavit jiné vlákno, což může být uprostřed operace. Pozastavení vlákno může způsobit poškození dat nebo přerušení výstupních podmínek. Má umístit vlákno do pozastaveném stavu a nikdy obnovit pomocí <xref:System.Threading.Thread.Resume%2A> metody aplikace může na neomezenou dobu zaseknout a případně poškodit data aplikací. Tyto metody byly označeny jako zastaralé.  
  
 Synchronizace primitiv jsou uložené ve vlákně na cílový, zůstanou udržovaných během pozastavení. To může vést k zablokování by měl jiného vlákna, například vlákno provádění <xref:System.Threading.Thread.Suspend%2A>, pokusí se získat zámek na primitivní vlastnost. V takovém případě problém projevuje jako vzájemné zablokování.  
  
## <a name="resolution"></a>Rozlišení  
 Vyhněte se návrhy, které vyžadují použití <xref:System.Threading.Thread.Suspend%2A> a <xref:System.Threading.Thread.Resume%2A>. Pro spolupráci mezi vlákny, použijte synchronizace primitiv <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex>, nebo jazyka C# `lock` příkaz. Pokud musíte použít tyto metody, zmenší okno čas a minimalizovat kód, který provede při vlákno je v pozastaveném stavu.  
  
## <a name="effect-on-the-runtime"></a>Vliv na modulu Runtime  
 Tato MDA nemá žádný vliv na modulu CLR. Pouze sestavy data o nebezpečné operace vláken.  
  
## <a name="output"></a>Výstup  
 MDA identifikuje metodu nebezpečná vláken, která způsobila, že její aktivaci.  
  
## <a name="configuration"></a>Konfigurace  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje volání <xref:System.Threading.Thread.Suspend%2A> metoda, která způsobí, že aktivace `dangerousThreadingAPI`.  
  
```  
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.Thread>  
 [Diagnostikování chyb pomocí asistentů spravovaného ladění](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [lock – příkaz](~/docs/csharp/language-reference/keywords/lock-statement.md)
