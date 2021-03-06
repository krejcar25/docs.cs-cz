---
title: '&lt;certificateReference&gt; pro &lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7728f2ffc74462e43de32b07b819cc2371c9bc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificatereferencegt-for-ltidentitygt"></a>&lt;certificateReference&gt; pro &lt;identity&gt;
Určuje nastavení pro ověření certifikátu X.509. Zabezpečený [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] klienta, která se připojuje k koncový bod s tuto identitu ověřuje, že deklarací identity předkládaných server obsahovat použitý k vytvoření tuto identitu deklarace identity.  
  
 \<identity >  
\<certificateReference >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<certificateReference   
        findValue="String"   
    isChainIncluded="Boolean"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
  
    storeLocation="LocalMachine/CurrentUser"  
  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
</certificateReference>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|findValue|Určuje hodnotu k vyhledání v úložišti certifikátů X.509. Typ obsažený v tomto atributu musí splňovat požadavky na zadané `X509FindType` hodnotu. Výchozí hodnota je prázdný řetězec.|  
|isChainIncluded|Logická hodnota, která určuje, pokud se provádí ověření pomocí řetěz certifikátů.|  
|storeLocation|Určuje umístění úložiště certifikátů, které může klient použít pro ověření certifikátu serveru.<br /><br /> Platné hodnoty patří:<br /><br /> -LocalMachine: Úložiště certifikátů přiřazené k místnímu počítači.<br />-CurrentUser: Úložiště certifikátů přiřazená aktuálnímu uživateli.<br /><br /> Výchozí hodnota je v místním počítači.<br /><br /> Tento atribut je typu <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Určuje název úložiště certifikátu X.509 otevřete.<br /><br /> Platné hodnoty patří:<br /><br /> -Adresáře: Úložiště certifikátů pro ostatní uživatele.<br />-AuthRoot: Certifikát úložiště pro třetí strany certifikační autority (CA).<br />-CertificateAuthority: Úložiště certifikátů pro zprostředkující certifikační autority.<br />-Nepovolené: Certifikát úložiště pro odvolané certifikáty.<br />-: Úložiště certifikátů my Pro osobní certifikáty.<br />-Root: Úložiště certifikátů pro důvěryhodné kořenové certifikační autority.<br />-TrustedPeople: Úložiště certifikátů přímo důvěryhodných osob a prostředky.<br />-TrustedPublisher: Úložiště certifikátů pro přímo důvěryhodné vydavatele.<br /><br /> Výchozí hodnota je můj.<br /><br /> Tento atribut je typu <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Určuje typ vyhledávání X.509 provést. Typ obsažený v `findValue` atributu musí splňovat požadavky na zadaný X509FindType.<br /><br /> Platné hodnoty patří:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName.<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> Výchozí hodnota je FindBySubjectDistinguishedName.<br /><br /> Tento atribut je typu <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<identity >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Určuje nastavení, které umožňují ověřování koncový bod pomocí dalších koncových bodů výměna zpráv s ním.|  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>
