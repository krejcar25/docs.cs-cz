---
title: "221 – MessageReceivedFromTransport"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 139ca9e0fbe4d3f59d3d593f7785d5fb65e64702
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="221---messagereceivedfromtransport"></a>221 – MessageReceivedFromTransport
## <a name="properties"></a>Vlastnosti  
  
|||  
|-|-|  
|ID|221|  
|Klíčová slova|EndToEndMonitoring, řešení potíží s ServiceModel|  
|úroveň|Informace o|  
|Kanál|Aplikaci Microsoft Windows Server – aplikace nebo analytické|  
  
## <a name="description"></a>Popis  
 Tato událost je vygenerované, když Model služby přijme zprávu o z přenosu.  
  
## <a name="message"></a>Zpráva  
 Dispečer přijala zprávu z přenosu. ID korelace == '%1'.  
  
## <a name="details"></a>Podrobnosti  
  
|Název položky dat|Datová položka – Typ|Popis|  
|--------------------|--------------------|-----------------|  
|ID korelace|`xs:GUID`|Aktivita ID použít ke korelaci `MessageSentToTransport` událostí ze služby nebo klienta na jeho odpovídající `MessageReceivedFromTransport` na druhém konci.|  
|HostReference|`xs:string`|Pro hostované webové služby v tomto poli jednoznačně identifikuje v hierarchii webové služby. Formát je definovaný jako "virtuální cesta aplikace název webu &#124; Virtuální cesta služby &#124; ServiceName}. Příklad: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|Domény aplikace|`xs:string`|Řetězec vrácený AppDomain.CurrentDomain.FriendlyName.|
