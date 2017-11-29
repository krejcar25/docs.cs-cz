---
title: '&lt;serviceDiscovery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9c371455767b912bd124c2207a1cc29b8ead71cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicediscoverygt"></a><span data-ttu-id="123c8-102">&lt;serviceDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="123c8-102">&lt;serviceDiscovery&gt;</span></span>
<span data-ttu-id="123c8-103">Určuje možnosti rozpoznání koncových bodů služby.</span><span class="sxs-lookup"><span data-stu-id="123c8-103">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="123c8-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="123c8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="123c8-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="123c8-105">\<behaviors></span></span>  
<span data-ttu-id="123c8-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="123c8-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="123c8-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="123c8-107">\<behavior></span></span>  
<span data-ttu-id="123c8-108">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="123c8-108">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123c8-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="123c8-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String" 
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String" 
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="123c8-110">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="123c8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="123c8-111">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="123c8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="123c8-112">Atributy</span><span class="sxs-lookup"><span data-stu-id="123c8-112">Attributes</span></span>  
 <span data-ttu-id="123c8-113">Žádné</span><span class="sxs-lookup"><span data-stu-id="123c8-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="123c8-114">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="123c8-114">Child Elements</span></span>  
  
|<span data-ttu-id="123c8-115">Prvek</span><span class="sxs-lookup"><span data-stu-id="123c8-115">Element</span></span>|<span data-ttu-id="123c8-116">Popis</span><span class="sxs-lookup"><span data-stu-id="123c8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="123c8-117">\<announcementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="123c8-117">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="123c8-118">Kolekce koncových bodů oznámení.</span><span class="sxs-lookup"><span data-stu-id="123c8-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="123c8-119">Pomocí této části můžete určovat koncové body k použití pro odesílání zpráv oznámení.</span><span class="sxs-lookup"><span data-stu-id="123c8-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="123c8-120">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="123c8-120">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="123c8-121">Kolekce zjišťování koncových bodů.</span><span class="sxs-lookup"><span data-stu-id="123c8-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="123c8-122">V této části použijte k určení koncových bodů, na kterém se má naslouchat pro zprávy zjišťování.</span><span class="sxs-lookup"><span data-stu-id="123c8-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="123c8-123">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="123c8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="123c8-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="123c8-124">Element</span></span>|<span data-ttu-id="123c8-125">Popis</span><span class="sxs-lookup"><span data-stu-id="123c8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="123c8-126">\<chování ></span><span class="sxs-lookup"><span data-stu-id="123c8-126">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="123c8-127">Určuje chování element.</span><span class="sxs-lookup"><span data-stu-id="123c8-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="123c8-128">Poznámky</span><span class="sxs-lookup"><span data-stu-id="123c8-128">Remarks</span></span>  
 <span data-ttu-id="123c8-129">Když se přidá do konfigurace chování služby, tento element konfigurace zajistí koncové body služeb zjistitelný.</span><span class="sxs-lookup"><span data-stu-id="123c8-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="123c8-130">Funkce zjišťování těchto koncových bodů lze dále konfigurovat pomocí [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) nebo [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) podřízené elementy.</span><span class="sxs-lookup"><span data-stu-id="123c8-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="123c8-131">Použít [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) část konfigurace hlášení zadáním konfigurace koncového bodu, která se má použít k odeslání oznámení týkající se služeb (nebo Hello je online a offline nebo Bye).</span><span class="sxs-lookup"><span data-stu-id="123c8-131">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="123c8-132">Použití [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) části ručně zadat koncový bod, ke kterému chcete přijímat zprávy zjišťování.</span><span class="sxs-lookup"><span data-stu-id="123c8-132">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="123c8-133">Příklad</span><span class="sxs-lookup"><span data-stu-id="123c8-133">Example</span></span>  
 <span data-ttu-id="123c8-134">Následující příklad konfigurace určuje, že CalculatorService zjistitelné a volitelně specifikuje koncového bodu oznámení má být použit.</span><span class="sxs-lookup"><span data-stu-id="123c8-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
  ...  
  </service>  
</services>  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery>  
        <announcementEndpoints>  
              <endpoint name="udpEndpoint"  
                        kind="udpAnnouncementEndpoint" />  
        </announcementEndpoints>  
      </serviceDiscovery>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="123c8-135">Viz také</span><span class="sxs-lookup"><span data-stu-id="123c8-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>