---
title: "&lt;transport&gt; – &lt;netTcpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5ad2271b86d37d9063ac54d9a4e45681d132eb1d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltnettcpbindinggt"></a>&lt;transport&gt; – &lt;netTcpBinding&gt;
Definuje typ požadavků na zabezpečení na úrovni zpráv pro koncový bod nakonfigurované [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
 \<system.ServiceModel>  
\<vazby >  
\<netTcpBinding>  
\<Vazba >  
\<zabezpečení >  
\<transport>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<netTcpBinding>  
    <binding>  
        <security  
         mode="None|Transport|Message|TransportWithMessageCredential">  
            <transport clientCredentialType="None|Windows|Certificate"  
             protectionLevel="None|Sign|EncryptAndSign"             sslProtocols="Tls|Tls11|Tls12">  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</netTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují nadřazené elementy, atributy a podřízené elementy  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|clientCredentialType|Volitelné. Určuje typ pověření, který se má použít při ověřování klienta pomocí zabezpečení přenosu.<br /><br /> -Výchozí hodnota je `Windows`.<br />-Tento atribut je typu <xref:System.ServiceModel.TcpClientCredentialType>.|  
|ProtectionLevel|Volitelné. Definuje zabezpečení na úrovni přenosu protokolu TCP. Podepisování zpráv snižuje riziko třetích stran manipulaci s zprávy při jejich přenosu. Během přenosu zajišťuje šifrování dat na úrovni o ochraně osobních údajů.<br /><br /> Výchozí hodnota je `EncryptAndSign`.|  
|sslProtocols|Hodnotu výčtu příznak SslProtocols, která určuje, které SslProtocols jsou podporovány. Výchozí hodnota je Tls &#124; Tls11 &#124; Tls12.|  
|policyEnforcement|Tento výčet Určuje, kdy <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> by se měly vynucovat.<br /><br /> 1.  Nikdy – zásady se vynucují nikdy (rozšířené ochrany je zakázáno).<br />2.  WhenSupported – zásady se vynucují jenom v případě, že klient podporuje rozšířené ochrany.<br />3.  Vždy – je vždy tato zásada vynucená. Klienti, které nepodporují rozšířené ochrany se nepodaří ověřit.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType atribut  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|Žádné|Klient je anonymní. To vyžaduje certifikát pro službu.|  
|Windows|Určuje ověřování systému Windows z klienta pomocí SP vyjednávání (vyjednávání protokolu Kerberos).|  
|certifikát|Používá certifikát ověření klienta. To se používá vyjednávání SSL a vyžaduje certifikát pro službu.|  
  
## <a name="protectionlevel-attribute"></a>Atribut protectionLevel  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|Žádné|Žádná ochrana.|  
|Přihlášení|Zprávy jsou podepsané.|  
|EncryptAndSign|-Zprávy jsou šifrovaný a podepsaný.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<zabezpečení >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Určuje možnosti zabezpečení [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).|  
  
## <a name="remarks"></a>Poznámky  
 Pro integrity a důvěrnosti zpráv protokolu SOAP a vzájemné ověřování, použijte zabezpečení přenosu. Pokud je tento režim zabezpečení na vazbu, zásobník kanál je nakonfigurován pomocí zabezpečení přenosu a protokolu SOAP zprávy jsou zabezpečené pomocí zabezpečení přenosu, například Windows (Negotiate) nebo SSL přes protokol TCP.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.TcpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [Zabezpečení služeb a klientů](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Vazby](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurace vazeb poskytovaných systémem](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Používání vazeb ke konfiguraci služby Windows Communication Foundation a klienty](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Vazba >](../../../../../docs/framework/misc/binding.md)
