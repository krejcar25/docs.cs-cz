---
title: "Základní informace o využití SendParameters a ReceiveParameters aktivit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 375168f45ee0bba5df1ca723398d448ead89555c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a>Základní informace o využití SendParameters a ReceiveParameters aktivit
Tento příklad ukazuje použití <xref:System.ServiceModel.Activities.SendParametersContent> a <xref:System.ServiceModel.Activities.ReceiveParametersContent> aktivity. Službu zpřístupní jednu operaci, která argument řetězce a vrátí je vstupní zpět do klienta. Ukázka ukazuje, jak nastavit parametry pro tyto aktivity zasílání zpráv.  
  
> [!IMPORTANT]
>  Ukázky může být již nainstalována na váš počítač. Před pokračováním zkontrolovat na následující adresář (výchozí).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky. Tato ukázka se nachází v následujícím adresáři.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a>Pomocí této ukázky  
  
1.  Načtení projektu řešení v [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] a sestavte projekt.  
  
2.  Nejprve spusťte aplikaci EchoWorkflowService vygenerovaných \EchoWorkflowService\bin\debug [základní adresář řešení].  
  
3.  Druhý spusťte aplikaci EchoWorkflowClient vygenerovaných \EchoWorkflowClient\bin\debug [základní adresář řešení].  
  
4.  Klient volání operace služby Echo a zobrazí výsledky. Po dokončení stiskněte klávesu ENTER ukončíte klienta a pak službu.