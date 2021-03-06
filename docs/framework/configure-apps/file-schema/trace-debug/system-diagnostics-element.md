---
title: "&lt;System.Diagnostics&gt; – Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: e76f5ef38e29a1afc9f438abb37239d109876cc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemdiagnosticsgt-element"></a>&lt;System.Diagnostics&gt; – Element
Určuje naslouchací procesy trasování, které shromažďování, ukládání a směrování zpráv a úroveň, kde je nastaven na přepínač trasování.  
  
 \<Konfigurace >  
\<System.Diagnostics >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<Assert – >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Určuje, jestli se má zobrazit okno se zprávou při volání <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> metoda; také určuje název souboru pro zápis zprávy.|  
|[\<čítače výkonu >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Určuje velikost globální paměť sdíleny čítače výkonu.|  
|[\<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Obsahuje naslouchací procesy, které může odkazovat všechny zdroje nebo element trasování. Moduly pro naslouchání identifikovány jako sdílené moduly pro naslouchání mohou být přidány do zdroje nebo trasování podle názvu.|  
|[\<zdroje >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Určuje trasování zdrojů, které zahájí trasování zpráv.|  
|[\<přepínače >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Obsahuje trasování – přepínače a úrovně, kde jsou nastaveny trasování – přepínače.|  
|[\<trasování >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Obsahuje naslouchací procesy, které shromažďování, ukládání a směrovat trasovací zprávy.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|`configuration`|Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak pro vložení přepínače trasování a naslouchací uvnitř  **\<system.diagnostics >** element. `General` Přepínač trasování je nastaven na hodnotu <xref:System.Diagnostics.TraceLevel> úroveň. Naslouchací proces trasování `myListener` vytvoří soubor s názvem `MyListener.log` a zapíše výstup do souboru.  
  
> [!NOTE]
>  V rozhraní .NET Framework verze 2.0 můžete zadat hodnotu pro přepínač text. Například můžete zadat `true` pro <xref:System.Diagnostics.BooleanSwitch> nebo použijte text, například představující hodnotu výčtu `Error` pro <xref:System.Diagnostics.TraceSwitch>. Na řádku `<add name="myTraceSwitch" value="Error" />` je ekvivalentní `<add name="myTraceSwitch" value="1" />`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 [Trasování a ladění schématu nastavení](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
