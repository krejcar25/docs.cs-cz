---
title: "224 – MessageThrottleAtSeventyPercent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e7d35407fe22dc913f7122163006035717d60d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="224---messagethrottleatseventypercent"></a>224 – MessageThrottleAtSeventyPercent
## <a name="properties"></a>Vlastnosti  
  
|||  
|-|-|  
|ID|224|  
|Klíčová slova|EndToEndMonitoring, HealthMonitoring, řešení potíží s ServiceModel|  
|úroveň|Upozornění|  
|Kanál|Aplikaci Microsoft Windows Server – aplikace nebo analytické|  
  
## <a name="description"></a>Popis  
 Pokud byla překročena jedním z omezení hlavní služby, `MessageThrottleExceeded` je vygenerované události. Když zpomalí Špička aktivity a aktuální hodnota omezení je na 70 procent aktuální limit pak tato událost je vygenerované. Všimněte si, že tato událost je jenom vygenerované po zpomalení jako aktivity. Pokud je aktuální hodnota bude umístěn na značce 70 procent, (například 70,69,70,71,70,69), pouze první výskyt 70 procent výsledky v události. Po této události je vygenerované, budoucí výskyt překročení omezení je omezit vést `MessageThrottleExceeded` událostí.  
  
## <a name="message"></a>Zpráva  
 Limit omezení "%1" (%2) je na 70 %%.  
  
## <a name="details"></a>Podrobnosti  
  
|Název položky dat|Datová položka – Typ|Popis|  
|--------------------|--------------------|-----------------|  
|Název omezení.|`xs:string`|Název omezení, která byla překročena. Buď `MaxConcurrentCalls`, `MaxConcurrentInstances`, nebo `MaxConcurrentSessions`,|  
|Limit|`xs:long`|Aktuálně nakonfigurovaný limit omezení.|  
|HostReference|`xs:string`|Pro hostované webové služby v tomto poli jednoznačně identifikuje v hierarchii webové služby. Formát je definovaný jako "virtuální cesta aplikace název webu &#124; Virtuální cesta služby &#124; ServiceName}. Příklad: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|Domény aplikace|`xs:string`|Řetězec vrácený AppDomain.CurrentDomain.FriendlyName.|
