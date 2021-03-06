---
title: "Pomocí zprostředkovatele komunikace se serverem Exchange externích dat"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b777cab4caf5b2b02c66e8378a7efce265157df0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-interop-with-external-data-exchange"></a>Pomocí zprostředkovatele komunikace se serverem Exchange externích dat
<xref:System.Activities.Statements.Interop> Aktivity můžete použít ke spuštění aktivity z [!INCLUDE[wf](../../../../includes/wf-md.md)] v [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] a [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) a pracovních postupů v rámci [!INCLUDE[wf2](../../../../includes/wf2-md.md)] v [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4). Tento příklad ukazuje, jak nakonfigurovat a spustit WF3 pracovní postup, který používá <xref:System.Workflow.Activities.ExternalDataExchangeService> (a odpovídající vlastní aktivity pro volání metod a zpracování událostí) pomocí <xref:System.Activities.Statements.Interop> aktivity v WF4 služby pracovních postupů.  
  
> [!IMPORTANT]
>  Ukázky může být již nainstalována na váš počítač. Před pokračováním zkontrolovat na následující adresář (výchozí).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky. Tato ukázka se nachází v následujícím adresáři.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a>Pro fungování této ukázky  
  
1.  Otevřete soubor ExternalDataExchange.sln v [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Chcete-li sestavit ukázku, stiskněte CTRL + SHIFT + B.  
  
3.  Pokud chcete spustit ukázku, stisknutím klávesy F5.
