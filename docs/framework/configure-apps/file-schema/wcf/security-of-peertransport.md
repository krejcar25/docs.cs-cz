---
title: "&lt;security&gt; – &lt;peerTransport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d08d839d0eb80c23b96f87cf26d3d68db7d358f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a>&lt;security&gt; – &lt;peerTransport&gt;
Obsahuje nastavení zabezpečení, které jsou přidružené k rovnocenného kanálu, včetně typu ověřování použité a zabezpečení použít pro přenos zpráv.  
  
 \<system.serviceModel >  
\<vazby >  
\<customBinding >  
\<Vazba >  
\<– peerTransport >  
\<zabezpečení >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`mode`|Určuje typ zabezpečení, které se má použít. Výchozí hodnota je zpráva. Tento atribut je typu <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>režim atribut  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`None`|Zabezpečení je vypnuté.|  
|`Transport`|Zabezpečení je k dispozici pomocí protokolu HTTPS.|  
|`Message`|Zabezpečení protokolu SOAP poskytuje ověřování, integrity a důvěrnosti.|  
|`TransportWithMessageCredential`|HTTPS poskytuje možnosti ověřování a důvěrnost. Protokolu SOAP zprávy poskytují typy bohaté přihlašovacích údajů.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<přenos >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Definuje sdílené přenos vlastní vazby. Tento element má `clientCredentialType` atribut, který určuje pověření, která má být použit při interakci s služby. Tento atribut je typu <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> Tento element je typu <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<– peerTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Definuje sdílené přenos vlastní vazby.|  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Zabezpečení přenosu](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Přenosy](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Volba přenosu](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Vazby](../../../../../docs/framework/wcf/bindings.md)  
 [Rozšíření vazeb](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Vlastní vazby](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
