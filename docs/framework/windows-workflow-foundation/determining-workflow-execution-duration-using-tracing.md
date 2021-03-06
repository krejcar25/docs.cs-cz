---
title: "Určení dobu trvání provádění pracovního postupu pomocí trasování"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2687d045db28974e99b2f2b6a3222924a520720
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="determining-workflow-execution-duration-using-tracing"></a>Určení dobu trvání provádění pracovního postupu pomocí trasování
Toto téma ukazuje, jak určit čas potřebný pro úspěšně dokončila, vlastním hostováním pracovní postup provést pomocí trasování pracovního postupu.  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a>Chcete-li zjistit dobu trvání provádění pracovního postupu aplikace pomocí trasování pracovního postupu  
  
1.  Otevřete [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  Vyberte **soubor**, **nové**, **projektu**.  V části **C#**, vyberte **pracovního postupu** uzlu.  Vyberte **pracovního postupu konzolové aplikace** ze seznamu šablon.  Název nového projektu `WorkflowDurationTracing` a klikněte na tlačítko **OK**.  
  
2.  Otevřete Workflow1.xaml.  Přetáhněte <xref:System.Activities.Statements.Delay> aktivity na plochu návrháře. Vlastnost doba trvání aktivity přiřadíte hodnotu 00:00:10 (deseti sekund).  
  
3.  Otevřete Prohlížeč událostí kliknutím **spustit**, **spustit**a zadáním `eventvwr.exe`.  
  
4.  Pokud jste nepovolili trasování pracovního postupu, rozbalte položku **protokoly aplikací a služeb**, **Microsoft**, **Windows**, **serveru aplikace – aplikace** . Vyberte **zobrazení**, **ukazují analytické a ladicí protokoly**. Klikněte pravým tlačítkem na **ladění** a vyberte **povolit protokol**. Ponechte prohlížeče událostí otevřete tak, aby trasování lze zobrazit po spuštění pracovního postupu.  
  
5.  Spusťte pracovní postup aplikace stisknutím kombinace kláves CTRL + SHIFT + B.  
  
6.  V prohlížeči událostí najdete poslední událost s ID 1009 a zobrazí se zpráva podobná této. Poznamenejte si dobu, která zprávu protokolu byla zaznamenána.  
  
 **Nadřazené aktivity '', DisplayName: ", identifikátor InstanceId: '' naplánované podřízené aktivity 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', identifikátor InstanceId: '1'.**  
  
7.  Najít jinou poslední událost s ID 1001 a zobrazí se zpráva podobná této.  Odečtena předchozí čas zprávy od této zprávy protokolováno hodnoty určete dobu trvání provádění pracovního postupu, které by měly být přibližně 10 sekund.  
  
 **Instance pracovního postupu Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' byla dokončena v uzavřeném stavu.**  
  
## <a name="see-also"></a>Viz také  
 [Trasování pracovních postupů](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [Windows Server App Fabric monitorování](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Monitorování aplikací pomocí App Fabric](http://go.microsoft.com/fwlink/?LinkId=201275)
