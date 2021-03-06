---
title: "contextSwitchDeadlock – pomocník spravovaného ladění (MDA)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 816afbae0cca18de24c11152541a509b54c119b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="contextswitchdeadlock-mda"></a>contextSwitchDeadlock – pomocník spravovaného ladění (MDA)
`contextSwitchDeadlock` Pomocník spravovaného ladění (MDA) se aktivuje, když bude během pokusu o přechod kontextu COM zjištěno zablokování.  
  
## <a name="symptoms"></a>Příznaky  
 Nejběžnější symptomem je, že se nevrací volání nespravovaného komponentu COM ze spravovaného kódu.  Dalším symptomem je využití paměti v průběhu času zvětšuje.  
  
## <a name="cause"></a>příčina  
 Nejvíce pravděpodobné příčiny je, že vlákno single-threaded apartment (STA) není čerpání – zprávy. STA vlákno je buď čekání bez čerpání zpráv nebo provádí náročná operace a nepovolí fronty zpráv čerpadla.  
  
 Využití paměti v průběhu času zvětšuje je způsobena finalizační metodu vlákno pokus o volání `Release` na nespravované modelu COM není vrácení součásti a součást.  To brání tomu, aby finalizační metodu opětovného získání jiné objekty.  
  
 Výchozí hodnota je STA modelu vláken pro hlavní vlákno konzolové aplikace jazyka Visual Basic Tato MDA je aktivována, pokud zřetězení STA používá interoperabilita modelů COM přímo nebo nepřímo přes modul common language runtime nebo ovládacího prvku třetích stran.  Abyste se vyhnuli aktivace této MDA v konzolové aplikaci jazyka Visual Basic, použít <xref:System.MTAThreadAttribute> atribut hlavní metodu nebo upravit aplikaci na čerpadlo zprávy.  
  
 Je možné pro tento MDA k nesprávně aktivovat, pokud jsou splněny všechny následující podmínky:  
  
-   Aplikace vytvoří komponenty modelu COM z vláken STA přímo nebo nepřímo prostřednictvím knihovny.  
  
-   Aplikace byla zastavena v ladicím programu a uživatel dál aplikace nebo provést operaci kroku.  
  
-   Nespravované ladění není povoleno.  
  
 Pokud chcete zjistit, pokud MDA nesprávně aktivován, zakažte všechny zarážky, restartujte aplikaci a povolit jeho spuštění bez zastavení. Pokud MDA není aktivováno, je pravděpodobné, že původní aktivace je chybná. V takovém případě zakážete MDA, aby se zabránilo narušení s relaci ladění.  
  
> [!NOTE]
>  Tato (mda) je ve výchozím nastavení pro [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] a novějších verzích. Když je proces hostování povoleno v [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], nelze zakázat mda, které jsou ve výchozím nastavení. Proces hostování je zapnutá ve výchozím nastavení, takže musí být explicitně zakázány. Informace o tom, jak zakázat mda, najdete v části "Povolení a zákaz mda" v [diagnostikování chyb pomocí asistentů spravovaného ladění](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="resolution"></a>Rozlišení  
 Postupujte podle COM pravidla týkající se STA čerpání zpráv.  
  
## <a name="effect-on-the-runtime"></a>Vliv na modulu Runtime  
 Tato MDA nemá žádný vliv na modulu CLR. Pouze sestavy data o kontextech COM.  
  
## <a name="output"></a>Výstup  
 Zpráva popisující aktuální kontext a cílový kontext.  
  
## <a name="configuration"></a>Konfigurace  
  
```xml  
<mdaConfig>  
  <assistants>  
    <contextSwitchDeadlock />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnostikování chyb pomocí asistentů spravovaného ladění](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Zařazování spolupráce](../../../docs/framework/interop/interop-marshaling.md)
