---
title: '&lt;discoveryEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51caf46f85e7edd1f8e4b9a08ab6a1198ccd9c79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiscoveryendpointgt"></a>&lt;discoveryEndpoint&gt;

Tento element konfigurace definuje standardní koncový bod s pevnou zjišťování kontrakt. Při přidání konfigurace služby, určuje, kde přijímat zprávy zjišťování. Po přidání do konfigurace klienta Určuje, kam má posílat dotazy zjišťování.  
  
\<system.serviceModel >  
\<standardEndpoints >  
  
## <a name="syntax"></a>Syntaxe

```xml
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed" 
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxResponseDelay="Timespan" 
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy

Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy

| Atribut        | Popis |  
| ---------------- | ----------- |  
| discoveryMode    | Řetězec, který určuje režim zjišťování protokolu. Platné hodnoty jsou "Ad hoc" a "Spravovaný". Ve spravovaném režimu protokol spoléhá na zjišťování Proxy, která funguje jako úložiště zjistitelný služeb. Ad hoc režim vyžaduje, aby protokol bude použit UDP vícesměrového vysílání mechanismus k vyhledání dostupných služeb. Další informace o vlastnosti najdete v tématu <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>. |  
| discoveryVersion | Řetězec, který určuje jeden z dvě verze protokolu WS-Discovery. Platné hodnoty jsou WSDiscovery11 a WSDiscoveryApril2005. Tato hodnota je typu <xref:System.ServiceModel.Discovery.DiscoveryVersion>. |  
| maxResponseDelay | Časový interval hodnotu, která určuje maximální hodnota zpoždění protokol zjišťování bude čekat před odesláním některé zprávy, jako je například testu nebo vyřešit shodu.<br /><br /> Pokud jsou všechny ProbeMatches odesílá ve stejnou dobu, může způsobit storm sítě. Chcete-li tomu zabránit, odešlou ProbeMatches s náhodné zpoždění mezi každou ProbeMatch. Hodnota náhodného zpoždění je v rozsahu 0 je hodnota nastavená tímto atributem. Pokud tento atribut je nastaven na hodnotu 0, jsou odesílány zprávy ProbeMatches ve smyčce úzkou bez jakéhokoli zpoždění. ProbeMatches zprávy, jinak se odesílají s některé náhodné zpoždění tak, aby celkový čas potřebný k zasílání ProbeMatches není delší než maxResponseDelay. Tato hodnota je platné pouze pro služby, není použita klienty. |  
| `name`           | Řetězec, který určuje název konfigurace standardní koncového bodu. Název je používán `endpointConfiguration` atribut propojení koncový bod standardní konfiguraci koncového bodu služby. |  
  
### <a name="child-elements"></a>Podřízené prvky

Žádné  
  
### <a name="parent-elements"></a>Nadřazené prvky

| Prvek | Popis |  
| ------- | ----------- |  
| [\<standardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | Kolekce standardních koncových bodů, které jsou předem definované koncových bodů s jedním nebo více jejich vlastnosti (adresy, vazby, kontrakt) pevné. |  
  
## <a name="example"></a>Příklad

Následující příklad ukazuje služby naslouchá na zjišťování zprávy pomocí přenosového sdílené net vícesměrového vysílání. V příkladu explicitně určuje WS-Discovery. dubna 2005 verze.  
  
Konfigurace standardní koncového bodu se definují pro jednotlivé služby a nesmí se sdílet napříč službou. Pokud jiné služby chtěli mít stejný koncový bod zjišťování, musí být přidán k této službě části stejnou konfiguraci.  
  
```xml
<services>  
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding" 
              address="calculator" 
              contract="ICalculatorService" />  
    <endpoint name="peerNetDiscovery"  
              binding="peerTcpBinding"  
              address="net.p2p://discoveryMesh/multicast"  
              kind="discoveryEndpoint"  
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"  
              bindingConfiguration="discoveryPeerTcpBindingConfig" />      
  </service>  
</services>  
<standardEndpoints>  
  <discoveryEndpoint>  
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"                         
                      version="WSDiscoveryApril2005" />  
  </discoveryEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a>Viz také

<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
