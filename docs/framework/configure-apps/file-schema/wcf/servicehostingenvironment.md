---
title: '&lt;serviceHostingEnvironment&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a08df7c620065bb483d276e3ead2c179040f1c9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicehostingenvironmentgt"></a>&lt;serviceHostingEnvironment&gt;
Tento element definuje typ, který vytvoří instanci služby hostování prostředí konkrétního přenosu. Pokud tento element je prázdné, použije se výchozí typ. Tento element dá použít jenom na aplikace či soubory konfiguraci na úrovni počítačů.  
  
 \<systém. ServiceModel >  
\<ServiceHostingEnvironment >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean" 
                           minFreeMemoryPercentageToActivateService="Integer" 
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String" service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String" transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|aspNetCompatibilityEnabled|Logickou hodnotu udávající, zda je režim kompatibility ASP.NET je zapnutý pro aktuální aplikaci. Výchozí hodnota je `false`.<br /><br /> Když tento atribut je nastaven na `true`, požadavky na [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] služby procházet skrz kanál protokolu HTTP technologie ASP.NET a komunikaci v rámci jiných protokolů než HTTP je zakázáno. Další informace najdete v tématu [služby WCF a ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).|  
|minFreeMemoryPercentageToActivateService|Celé číslo, které určuje minimální množství volné paměti, která by měla být k dispozici systému, než [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] služby je možné aktivovat. **Upozornění:** zadání tohoto atributu společně s částečnou důvěryhodností v souboru web.config [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] v důsledku toho služba <xref:System.Security.SecurityException> spuštění služby.|  
|multipleSiteBindingsEnabled|Logická hodnota, která určuje, zda je povoleno více vazby služby IIS na webu.<br /><br /> IIS se skládá z webů, které jsou kontejnery pro virtuální aplikace obsahující virtuální adresáře. Aplikace v síti je přístupná přes jeden nebo více vazby služby IIS. Vazbu služby IIS poskytuje dva kusy informací: protokol vazby a informace o vazbě. Vytvoření vazby protokolu definuje schéma, přes který probíhá komunikace a informace o vazbě je informace, které slouží pro přístup k webu. Příklad vazby protokolu může být protokolu HTTP, kdežto informace o vazbě může obsahovat IP adresu, Port, Hlavička hostitele, atd.<br /><br /> Služba IIS podporuje zadání více vazby služby IIS na webu, což vede k více základní adresy na schéma. Ale [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] služba hostovaná na webu umožňuje vazbu na jedinou baseAddress na schéma.<br /><br /> Chcete-li povolit více vazby služby IIS na webovém serveru [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] služby, nastavte tento atribut na `true`. Všimněte si, že více vazba webu je podporována pouze pro protokol HTTP. Adresy koncových bodů v konfiguračním souboru musí být úplný identifikátor URI.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|Kolekci elementů konfigurace, které zadejte předponu filtry pro základní adresy používané hostitele služby.|  
|[\<serviceActivations >](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceactivations.md)|Konfigurační oddíl, který popisuje nastavení aktivace.|  
|[\<transportConfigurationTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|Kolekce konfigurační prvky, které identifikují typ konkrétního přenosu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|ServiceModel|Kořenový element všechny konfigurační prvky Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Poznámky  
 Ve výchozím nastavení služeb WCF spuštění-souběžného s technologií ASP.NET v aplikační domény hostované (AppDomain). I když do stejné domény aplikace můžou existovat společně WCF a ASP.NET, WCF požadavky nejsou zpracovává HTTP kanálu ASP.NET ve výchozím nastavení. Několik prvky platformu aplikací ASP.NET v důsledku toho nejsou k dispozici pro služby WCF. Mezi ně patří  
  
-   Autorizace ASP.NET soubor nebo adresa URL  
  
-   Zosobnění technologie ASP.NET  
  
-   Stav relace na základě souborů cookie  
  
-   HttpContext.Current  
  
-   Rozšiřitelnost kanálů prostřednictvím vlastního modulu HTTP  
  
 Pokud potřebujete služby WCF je funkce v rámci ASP.NET a komunikovat pouze prostřednictvím protokolu HTTP, můžete použít režim kompatibility ASP.NET na WCF. Tento režim zapnutý, když `aspNetCompatibilityEnabled` je nastavena na hodnotu `true` na úrovni aplikace. Implementace služby, musí deklarovat schopnost spustit v režimu kompatibility pomocí <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> třídy. Když je povolený režim kompatibility,  
  
-   Autorizace ASP.NET soubor nebo adresa URL se vynucuje před WCF autorizace. Rozhodnutí o autorizaci vychází transportní vrstvy identitu požadavku. Identity na úrovni zpráv se ignorují.  
  
-   Operací služby WCF začít spuštěn v kontextu zosobnění technologie ASP.NET. Pokud zosobnění technologie ASP.NET a WCF zosobnění jsou povolené pro konkrétní službu, platí kontextu zosobnění WCF.  
  
-   HttpContext.Current lze z kódu služby WCF a služby se vám bránit vystavení koncové body jiným protokolem než HTTP.  
  
-   Zpracovává požadavky WCF kanálu ASP.NET. HttpModules, které byly nakonfigurovány tak, aby fungoval na příchozí požadavky může také zpracovat WCF žádosti. Patří mezi komponenty platformy ASP.NET (například <xref:System.Web.SessionState.SessionStateModule>), a také moduly vlastní třetích stran.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak povolit režim kompatibility ASP.  
  
## <a name="code"></a>Kód  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [Hostování](../../../../../docs/framework/wcf/feature-details/hosting.md)  
 [Služby WCF a ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
