---
title: "&lt;udpTransportSettings&gt; – &lt;udpAnnouncementEndpoint&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7ddff1a-5eed-4bbc-8580-b95ef8890e1f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a5de8d55d34c2db0d0b1efd5a05024f1dbc4f42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltudptransportsettingsgt-of-ltudpannouncementendpointgt"></a>&lt;udpTransportSettings&gt; – &lt;udpAnnouncementEndpoint&gt;
Tento element konfigurace se zobrazí nastavení přenosu UDP pro [ \<udpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md).  
  
\<systém. ServiceModel >  
\<standardEndpoints >  
\<udpAnnouncementEndpoint >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <udpAnnouncementEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer" 
                              maxBufferPoolSize="Integer" 
                              maxMulticastRetransmitCount="Integer" 
                              maxPendingMessageCount="Integer" 
                              maxReceivedMessageSize="Integer" 
                              maxUnicastRetransmitCount="Integer" 
                              multicastInterfaceId="String" 
                              socketReceiveBufferSize="Integer" 
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpAnnouncementEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|duplicateMessageHistoryLength|Celé číslo, které určuje maximální počet hodnotách hash zpráv, které používá přenos pro nalezení duplicitních zpráv.  Duplicitní detekce se provádí na úrovni Správce TransportManager. Nastavení této vlastnosti na hodnotu 0 zakáže vyhledávání duplicit.<br /><br /> Tento atribut umožňuje správcům systému a vývojářům vypnout algoritmy detekce duplicitních zpráv. To může být žádoucí, pokud chcete implementovat vlastní detekci duplikátů algoritmus.<br /><br /> Výchozí hodnota je 4112.|  
|maxBufferPoolSize|Celé číslo, které určuje maximální velikost všechny fondy vyrovnávací paměti používané přenosu.|  
|maxMulticastRetransmitCount|Celé číslo, které určuje maximální počet, kolikrát zpráva by měla být přeneseny (kromě první odesílání).<br /><br /> Výchozí hodnota je 2.|  
|maxPendingMessageCount|Celé číslo, které určuje maximální počet zpráv, které bylo přijato, ale ještě nebyla odebrána z InputQueue instance jednotlivých kanálu.  Pokud InputQueue narazil na svůj limit počtu čeká na zprávu, zpráva se zahodí.<br /><br /> Výchozí hodnota je 32.|  
|MaxReceivedMessageSize|Celé číslo, které určuje maximální velikost zprávy, která může být zpracována vazbou.<br /><br /> Výchozí hodnota je 65507.|  
|maxUnicastRetransmitCount|Celé číslo, které určuje maximální počet, kolikrát zpráva by měla být přeneseny (kromě první odesílání).  Pokud je zpráva odeslána na adresu jednosměrového vysílání a příjmu zprávy odpovědi s odpovídající související s hlavičkou, může přenos ukončit již v rané fázi (před opětovným odesláním nakonfigurované stanovený počet).<br /><br /> Výchozí hodnota je 1.|  
|multicastInterfaceId|Řetězec, který jednoznačně identifikuje síťový adaptér, který se má použít při odesílání a příjem přenosů vícesměrového vysílání na počítačích s více adresami. Za běhu, bude přenos používat hodnota atributu k vyhledávání index rozhraní, které se pak použije k nastavení `IP_MULTICAST_IF` a `IPV6_MULTICAST_IF` soketu možnosti.  Stejný index rozhraní se použije při připojení ke skupině vícesměrového vysílání, pokud je k dispozici.<br /><br /> Výchozí hodnota je `null`.|  
|socketReceiveBufferSize|Celé číslo, které určuje velikost vyrovnávací paměti receive na základní soketu rozhraní WinSock.<br /><br /> Může uživatel přijímající kanál používat tento atribut na vazby pro řízení chování při přijetí dat v systému.  Například danou aplikaci, která spotřebovává příchozí zprávy WCF na maximální prahová hodnota, pomocí vyšší hodnota pro tento atribut by povolit zpráv zásobníku ve vyrovnávací paměti rozhraní WinSock při čekání na aplikaci, která bude moct jejich zpracování.  Pomocí na nižší hodnotu ve stejné situaci by způsobilo získávání ztracených zpráv. Tento atribut zpřístupňuje základní rozhraní WinSock `SO_RCVBUF` soketu možnost. Hodnota tohoto atributu musí být alespoň velikost `maxReceivedMessageSize`.   Jeho nastavení na hodnotu menší, než `maxReceivedMessageSize` způsobí výjimku modulu runtime.<br /><br /> Výchozí hodnota je 65536.|  
|TimeToLive|Celé číslo, které určuje počet síťové segment směrování, které mohou procházet paketů vícesměrového vysílání.  Tento atribut zveřejňuje funkce související s `IP_MULTICAST_TTL` a `IP_TTL` soketu možnosti.<br /><br /> Výchozí hodnota je 1.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<udpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|Standardní koncový bod, který má pevnou oznámení, že vazba přenosu kontraktu a UDP.|  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Discovery.UdpTransportSettings>
