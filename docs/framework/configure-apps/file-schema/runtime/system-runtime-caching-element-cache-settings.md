---
title: "&lt;System.Runtime.Caching –&gt; – Element (nastavení mezipaměti)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83964d3a6e07267eaa946fa306301bc6d0d16e8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemruntimecachinggt-element-cache-settings"></a>&lt;System.Runtime.Caching –&gt; – Element (nastavení mezipaměti)
Poskytuje konfigurace pro výchozí v paměťově <xref:System.Runtime.Caching.ObjectCache> implementace prostřednictvím `memoryCache` položka v konfiguračním souboru.  
  
 \<Konfigurace >  
\<System.Runtime.Caching – >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 `None`  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<memoryCache >](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Definuje element, který slouží ke konfiguraci mezipaměti, který je založen na <xref:System.Runtime.Caching.MemoryCache> třídy.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<Konfigurace >](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Určuje kořenový element v každém konfiguračním souboru, který je používán modul common language runtime a [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] aplikace.|  
  
## <a name="remarks"></a>Poznámky  
 Třídy v tomto oboru názvů poskytují způsob, jak použít zařízení pro ukládání do mezipaměti jako ty, technologie ASP.NET, ale bez závislosti na `System.Web` sestavení. Další informace najdete v tématu [ukládání do mezipaměti v aplikacích .NET Framework](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).  
  
> [!NOTE]
>  Výstupní mezipaměti typy v a funkce <xref:System.Runtime.Caching> obor názvů jsou v nové [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak nakonfigurovat mezipaměti, který je založen na <xref:System.Runtime.Caching.MemoryCache> třídy. Tento příklad ukazuje, jak nakonfigurovat instanci `namedCaches` položka pro mezipaměť. Název mezipaměti se nastaví na výchozí název položky mezipaměti nastavením `name` atribut "Výchozí".  
  
 `cacheMemoryLimitMegabytes` Atribut a `physicalMemoryPercentage` atribut nastaveny na nulu. Nastavení těchto atributů na nulu, znamená to, který <xref:System.Runtime.Caching.MemoryCache> Automatická změna velikosti heuristiky se používají ve výchozím nastavení. Implementace mezipaměti musí porovnat aktuálního zatížení paměti do paměti absolutní a na základě procenta omezení každé dvě minuty.  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také  
 [\<memoryCache > – Element (nastavení mezipaměti)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
