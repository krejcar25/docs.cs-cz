---
title: "&lt;security&gt; – &lt;netHttpBinding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cbe36a801565af0d3664e5c827f8ce903be3b5c7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltnethttpbinding"></a>&lt;security&gt; – &lt;netHttpBinding
Definuje možnosti zabezpečení [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 \<system.ServiceModel>  
\<vazby >  
\<netHttpBinding>  
\<Vazba >  
\<zabezpečení >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují nadřazené elementy, atributy a podřízené elementy  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|režim|Volitelné. Určuje typ zabezpečení, který se používá. Výchozí hodnota je `None`. Tento atribut je typu <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> --> `System.ServiceModel.NetHttpSecurityMode`.|
  
## <a name="mode-attribute"></a>režim atribut  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|Žádné|-Zprávy není zabezpečená při přenosu.|  
|Přenos|Zabezpečení je k dispozici použití přenosu HTTPS. Protokolu SOAP zprávy jsou zabezpečené pomocí protokolu HTTPS. Služba je ověřen u klienta pomocí certifikátu X.509 služby. Klient je ověřen pomocí ClientCredentialType zadaný.|  
|Zpráva|Zabezpečení je k dispozici pomocí zabezpečení zpráv protokolu SOAP. Ve výchozím nastavení je text šifrovaný a podepsaný. Pro tuto vazbu systému vyžaduje, aby certifikát serveru poskytnuta klientovi vzdálené správy. Jediné platné `ClientCredentialType` pro tuto vazbu `Certificate`.|  
|TransportWithMessageCredential|Ověření integrity a důvěrnosti serveru jsou poskytovány zabezpečení přenosu. Ověření klienta je k dispozici prostřednictvím zabezpečení zpráv protokolu SOAP. Tento režim je důležité, když se uživatel ověřuje pomocí uživatelského jména a hesla a je stávajícího nasazení HTTP pro přenos zpráv zabezpečení.|  
|TransportCredentialOnly|Tento režim neposkytuje integrity a důvěrnosti zpráv. Poskytuje ověření klienta založené na protokolu http. Tento režim musí být použit s opatrní. By být používána v prostředích, kde se jiným způsobem (například IPSec) zajišťuje zabezpečení přenosu a zajišťuje pouze ověřování klienta [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastruktury.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nethttpbinding.md)|Definuje nastavení zabezpečení přenosu pro základní služba HTTP. Tento element odpovídá <xref:System.ServiceModel.HttpTransportSecurity>.|  
|[\<Zpráva >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-nethttpbinding.md)|Definuje nastavení zabezpečení zpráv pro základní služba HTTP. Tento element odpovídá <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|vazba|Element vazby [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).|  
  
## <a name="remarks"></a>Poznámky  
 Ve výchozím nastavení není zabezpečené zprávu protokolu SOAP a klient není ověřen. Tento element umožňuje konfigurovat nastavení dalšího ověření zabezpečení pro `netHttpBinding` elementu.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.NetHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>    
 [Zabezpečení služeb a klientů](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Výběr typu přihlašovacích údajů](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [Vazby](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurace vazeb poskytovaných systémem](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Používání vazeb ke konfiguraci služby Windows Communication Foundation a klienty](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Vazba >](../../../../../docs/framework/misc/binding.md)
