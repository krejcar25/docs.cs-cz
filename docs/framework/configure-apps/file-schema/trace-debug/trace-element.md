---
title: "&lt;trasování&gt; – Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 157adb6c7317aa047976cdb9e30711d20c9e543b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="lttracegt-element"></a><span data-ttu-id="c49c7-102">&lt;trasování&gt; – Element</span><span class="sxs-lookup"><span data-stu-id="c49c7-102">&lt;trace&gt; Element</span></span>
<span data-ttu-id="c49c7-103">Obsahuje naslouchací procesy, které shromažďování, ukládání a směrovat trasovací zprávy.</span><span class="sxs-lookup"><span data-stu-id="c49c7-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="c49c7-104">\<Konfigurace ></span><span class="sxs-lookup"><span data-stu-id="c49c7-104">\<configuration></span></span>  
<span data-ttu-id="c49c7-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="c49c7-105">\<system.diagnostics></span></span>  
<span data-ttu-id="c49c7-106">\<trasování ></span><span class="sxs-lookup"><span data-stu-id="c49c7-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c49c7-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c49c7-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c49c7-108">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="c49c7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c49c7-109">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="c49c7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c49c7-110">Atributy</span><span class="sxs-lookup"><span data-stu-id="c49c7-110">Attributes</span></span>  
  
|<span data-ttu-id="c49c7-111">Atribut</span><span class="sxs-lookup"><span data-stu-id="c49c7-111">Attribute</span></span>|<span data-ttu-id="c49c7-112">Popis</span><span class="sxs-lookup"><span data-stu-id="c49c7-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="c49c7-113">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="c49c7-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c49c7-114">Určuje, zda naslouchací procesy trasování automaticky vyprázdnění výstupní vyrovnávací paměť po každé operace zápisu.</span><span class="sxs-lookup"><span data-stu-id="c49c7-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="c49c7-115">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="c49c7-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c49c7-116">Určuje počet prostory pro odsazení.</span><span class="sxs-lookup"><span data-stu-id="c49c7-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="c49c7-117">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="c49c7-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c49c7-118">Určuje, zda má být použita globální zámek.</span><span class="sxs-lookup"><span data-stu-id="c49c7-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="c49c7-119">autoflush atribut</span><span class="sxs-lookup"><span data-stu-id="c49c7-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="c49c7-120">Hodnota</span><span class="sxs-lookup"><span data-stu-id="c49c7-120">Value</span></span>|<span data-ttu-id="c49c7-121">Popis</span><span class="sxs-lookup"><span data-stu-id="c49c7-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c49c7-122">Není k vyprázdnění automaticky výstupní vyrovnávací paměť.</span><span class="sxs-lookup"><span data-stu-id="c49c7-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="c49c7-123">Toto nastavení je výchozí.</span><span class="sxs-lookup"><span data-stu-id="c49c7-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c49c7-124">Automaticky vyprázdní vyrovnávací paměť pro výstup.</span><span class="sxs-lookup"><span data-stu-id="c49c7-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="c49c7-125">useGlobalLock atribut</span><span class="sxs-lookup"><span data-stu-id="c49c7-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="c49c7-126">Hodnota</span><span class="sxs-lookup"><span data-stu-id="c49c7-126">Value</span></span>|<span data-ttu-id="c49c7-127">Popis</span><span class="sxs-lookup"><span data-stu-id="c49c7-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c49c7-128">Pokud je naslouchací proces vláken; nepoužívá globální zámek jinak použije globální zámek.</span><span class="sxs-lookup"><span data-stu-id="c49c7-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="c49c7-129">Využívá globální zámek bez ohledu na to, jestli naslouchací proces je zaručeno bezpečné používání vláken.</span><span class="sxs-lookup"><span data-stu-id="c49c7-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="c49c7-130">Toto nastavení je výchozí.</span><span class="sxs-lookup"><span data-stu-id="c49c7-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c49c7-131">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="c49c7-131">Child Elements</span></span>  
  
|<span data-ttu-id="c49c7-132">Prvek</span><span class="sxs-lookup"><span data-stu-id="c49c7-132">Element</span></span>|<span data-ttu-id="c49c7-133">Popis</span><span class="sxs-lookup"><span data-stu-id="c49c7-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c49c7-134">\<moduly pro naslouchání ></span><span class="sxs-lookup"><span data-stu-id="c49c7-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="c49c7-135">Určuje naslouchací proces, který shromažďuje, úložiště a směrování zpráv.</span><span class="sxs-lookup"><span data-stu-id="c49c7-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c49c7-136">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="c49c7-136">Parent Elements</span></span>  
  
|<span data-ttu-id="c49c7-137">Prvek</span><span class="sxs-lookup"><span data-stu-id="c49c7-137">Element</span></span>|<span data-ttu-id="c49c7-138">Popis</span><span class="sxs-lookup"><span data-stu-id="c49c7-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c49c7-139">Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c49c7-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c49c7-140">Určuje naslouchací procesy trasování, které shromažďování, ukládání a směrování zpráv a úroveň, kde je nastaven na přepínač trasování.</span><span class="sxs-lookup"><span data-stu-id="c49c7-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c49c7-141">Příklad</span><span class="sxs-lookup"><span data-stu-id="c49c7-141">Example</span></span>  
 <span data-ttu-id="c49c7-142">Následující příklad ukazuje, jak používat `<trace>` elementu, který chcete přidat naslouchací proces `MyListener` k `Listeners` kolekce.</span><span class="sxs-lookup"><span data-stu-id="c49c7-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="c49c7-143">`MyListener`Vytvoří soubor s názvem `MyListener.log` a zapíše výstup do souboru.</span><span class="sxs-lookup"><span data-stu-id="c49c7-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="c49c7-144">`useGlobalLock` Je atribut nastaven na `false`, což způsobí, že globální zámek nechcete použít v případě naslouchací proces trasování je zaručeno bezpečné používání vláken.</span><span class="sxs-lookup"><span data-stu-id="c49c7-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="c49c7-145">`autoflush` Je atribut nastaven na `true`, což způsobí, že naslouchací proces trasování k zápisu do souboru bez ohledu na to, jestli <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> metoda je volána.</span><span class="sxs-lookup"><span data-stu-id="c49c7-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="c49c7-146">`indentsize` Je nastavena na hodnotu 0 (nula), což způsobí, že naslouchací proces pro odsazení nulové prostory při <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> metoda je volána.</span><span class="sxs-lookup"><span data-stu-id="c49c7-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c49c7-147">Viz také</span><span class="sxs-lookup"><span data-stu-id="c49c7-147">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="c49c7-148">Trasování a ladění schématu nastavení</span><span class="sxs-lookup"><span data-stu-id="c49c7-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)