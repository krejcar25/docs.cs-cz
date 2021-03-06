---
title: '&lt;comContract&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8fa70ba3cf8e66411812b84821e80772c9930f7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltcomcontractgt"></a>&lt;comContract&gt;
Určuje modelu COM + integrace kontraktu služby.  
  
 \<systém. ServiceModel >  
\<comContracts >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<comContracts>  
  <comContract  
      contract="string"  
      namespace="string"  
      name="string"  
      requireSession="Boolean">  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|kontrakt|Řetězec, který obsahuje typ smlouvy.|  
|name|Řetězec, který obsahuje název kontraktu.|  
|– obor názvů|Řetězec, který obsahuje obor názvů kontraktu.|  
|Vlastnost requiresSession|Logická hodnota, která určuje, zda kontrakt lze použít pouze na relacemi vazby. Při inicializaci služby modulu runtime integrace zajistí, že toto nastavení bude konzistentní s typ vazby, který se má použít. Výjimku se vygeneruje, pokud jeden nebo více vazby pro daný kontrakt je v konfliktu. Pokud je tato vlastnost `false`a jednosměrné kanál, který je používán a [parametry out] existují, generuje se taky výjimku.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|persistableTypes|Všechny trvalá typy.|  
|userDefinedTypes|Kolekce z uživatele definované typy (UDT), které má být součástí kontraktu služby.|  
|exposedMethods|Kolekce metod modelu COM +, které jsou zveřejněné, pokud je jako webovou službu vystavený rozhraní komponenty modelu COM +.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|comContracts|Obsahuje kolekci `comContract` elementy.|  
  
## <a name="remarks"></a>Poznámky  
 Kontrakty služeb integrace COM + jsou aktuálně omezeno na obor názvů "http://tempuri.org" a název smlouvy je odvozený od podpůrné rozhraní modelu COM. Můžete však zadat alternativy pomocí `comContracts` části, a taky `comContract` element v konfiguračním souboru. Například můžete použít následující konfigurace a zadat obor názvů, název kontraktu a uživatelem definované typy, které mají být zahrnuty, jakož i další nastavení pro kontrakt služby.  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
      <exposedMethods>  
         <exposedMethod name="BuyStock" />  
         <exposedMethod name="SellStock" />  
         <exposedMethod name="ExecuteTransaction" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
 Při inicializaci služby zadaných oborů názvů a názvy kontraktu platí pro popis generovaného služby.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [\<comContracts >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [Integrace s aplikacemi modelu COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [Postupy: Konfigurace nastavení služby modelu COM+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
