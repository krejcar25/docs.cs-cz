---
title: '&lt;dataContractSerializer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27b80c831fdc66bd3b022645c3de9c0c31ee575a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltdatacontractserializergt"></a>&lt;dataContractSerializer&gt;
Obsahuje konfigurační data pro <xref:System.Runtime.Serialization.DataContractSerializer>. Tento element proběhne dvě různé hierarchie. Jeden je uvedena v následující části schéma hierarchie a druhý je uveden v oddílu Poznámky.  
  
 \<systém. ServiceModel >  
\<chování >  
\<serviceBehaviors >  
\<chování >  
\<dataContractSerializer >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|ignoreExtensionDataObject|Logická hodnota, která určuje, jestli se ignorovat dat uvedených v koncovém bodě při jeho serializován nebo deserializován. Tento atribut je nastavit pouze na `<dataContractSerializer>` pod `<behavior>` elementu.|  
|maxItemsInObjectGraph|Celé číslo, které určuje maximální počet položek k serializaci nebo deserializaci. Tento atribut je 65536.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<chování >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|Kolekce nastavení pro chování služby.|  
|[\<System.Runtime.Serialization >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Reprezentuje kořenový element <xref:System.Runtime.Serialization> část oboru názvů a obsahuje prvky pro nastavení možností nástroje <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Poznámky  
 Jak jsme uvedli v úvodu tohoto tématu, to je druhá hierarchie, ve kterém \<X509Extension > dojde k elementu.  
  
 [\<System.Runtime.Serialization >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 Další informace o známé typy najdete v tématu <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [Známé typy kontraktů dat](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [Přenos a serializace dat](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
