---
title: '&lt;filtry&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a91be2862f58994b4495f1fa1a5c4e692b5ff7b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltersgt"></a>&lt;filtry&gt;

`filters` Element obsahuje kolekci filtrů XPath použít k řízení, jaký typ zprávy přihlášen.

Filtry se použijí jenom v přenosové vrstvě určeného `logMessagesAtTransportLevel` je `true`. Protokolování úrovně a poškozených zpráv služby nemá vliv filtry.

Chcete-li přidat filtr do kolekce, použijte `add` – klíčové slovo. Když jsou definovány jeden nebo více filtrů, jsou protokolovány pouze zprávy, které odpovídají alespoň jeden z filtrů. Pokud je definován žádný filtr, všechny zprávy předávat.

Filtry podporovat úplnou syntaxí XPath a aplikují v pořadí, ve kterém se zobrazují v konfiguračním souboru. Správnou syntaxi filtr výsledkem výjimka v konfiguraci.

Následuje příklad, jak nakonfigurovat filtr, který zaznamenává jen zprávy, které máte oddíl hlavičky SOAP.

```xml
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">  
  <filters>  
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
      /soap:Envelope/soap:Headers  
    </add>  
  </filters>  
</messageLogging>
```

## <a name="see-also"></a>Viz také

 <xref:System.ServiceModel.Configuration.DiagnosticSection><xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [Konfigurace protokolování zpráv](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [ \<messageLogging >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
