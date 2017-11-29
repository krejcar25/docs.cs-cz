---
title: '&lt;discoveryEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eae0769d6bed98639b3f1a476b7bcfed8259f9e5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ltdiscoveryendpointgt"></a><span data-ttu-id="56afd-102">&lt;discoveryEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="56afd-102">&lt;discoveryEndpoint&gt;</span></span>

<span data-ttu-id="56afd-103">Tento element konfigurace definuje standardní koncový bod s pevnou zjišťování kontrakt.</span><span class="sxs-lookup"><span data-stu-id="56afd-103">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="56afd-104">Při přidání konfigurace služby, určuje, kde přijímat zprávy zjišťování.</span><span class="sxs-lookup"><span data-stu-id="56afd-104">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="56afd-105">Po přidání do konfigurace klienta Určuje, kam má posílat dotazy zjišťování.</span><span class="sxs-lookup"><span data-stu-id="56afd-105">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
<span data-ttu-id="56afd-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="56afd-106">\<system.serviceModel></span></span>  
<span data-ttu-id="56afd-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="56afd-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56afd-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="56afd-108">Syntax</span></span>

```xml
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed" 
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxResponseDelay="Timespan" 
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56afd-109">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="56afd-109">Attributes and elements</span></span>

<span data-ttu-id="56afd-110">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="56afd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56afd-111">Atributy</span><span class="sxs-lookup"><span data-stu-id="56afd-111">Attributes</span></span>

| <span data-ttu-id="56afd-112">Atribut</span><span class="sxs-lookup"><span data-stu-id="56afd-112">Attribute</span></span>        | <span data-ttu-id="56afd-113">Popis</span><span class="sxs-lookup"><span data-stu-id="56afd-113">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="56afd-114">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="56afd-114">discoveryMode</span></span>    | <span data-ttu-id="56afd-115">Řetězec, který určuje režim zjišťování protokolu.</span><span class="sxs-lookup"><span data-stu-id="56afd-115">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="56afd-116">Platné hodnoty jsou "Ad hoc" a "Spravovaný".</span><span class="sxs-lookup"><span data-stu-id="56afd-116">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="56afd-117">Ve spravovaném režimu protokol spoléhá na zjišťování Proxy, která funguje jako úložiště zjistitelný služeb.</span><span class="sxs-lookup"><span data-stu-id="56afd-117">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="56afd-118">Ad hoc režim vyžaduje, aby protokol bude použit UDP vícesměrového vysílání mechanismus k vyhledání dostupných služeb.</span><span class="sxs-lookup"><span data-stu-id="56afd-118">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="56afd-119">Další informace o vlastnosti najdete v tématu <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="56afd-119">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="56afd-120">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="56afd-120">discoveryVersion</span></span> | <span data-ttu-id="56afd-121">Řetězec, který určuje jeden z dvě verze protokolu WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="56afd-121">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="56afd-122">Platné hodnoty jsou WSDiscovery11 a WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="56afd-122">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="56afd-123">Tato hodnota je typu <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="56afd-123">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="56afd-124">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="56afd-124">maxResponseDelay</span></span> | <span data-ttu-id="56afd-125">Časový interval hodnotu, která určuje maximální hodnota zpoždění protokol zjišťování bude čekat před odesláním některé zprávy, jako je například testu nebo vyřešit shodu.</span><span class="sxs-lookup"><span data-stu-id="56afd-125">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="56afd-126">Pokud jsou všechny ProbeMatches odesílá ve stejnou dobu, může způsobit storm sítě.</span><span class="sxs-lookup"><span data-stu-id="56afd-126">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="56afd-127">Chcete-li tomu zabránit, odešlou ProbeMatches s náhodné zpoždění mezi každou ProbeMatch.</span><span class="sxs-lookup"><span data-stu-id="56afd-127">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="56afd-128">Hodnota náhodného zpoždění je v rozsahu 0 je hodnota nastavená tímto atributem.</span><span class="sxs-lookup"><span data-stu-id="56afd-128">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="56afd-129">Pokud tento atribut je nastaven na hodnotu 0, jsou odesílány zprávy ProbeMatches ve smyčce úzkou bez jakéhokoli zpoždění.</span><span class="sxs-lookup"><span data-stu-id="56afd-129">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="56afd-130">ProbeMatches zprávy, jinak se odesílají s některé náhodné zpoždění tak, aby celkový čas potřebný k zasílání ProbeMatches není delší než maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="56afd-130">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="56afd-131">Tato hodnota je platné pouze pro služby, není použita klienty.</span><span class="sxs-lookup"><span data-stu-id="56afd-131">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="56afd-132">Řetězec, který určuje název konfigurace standardní koncového bodu.</span><span class="sxs-lookup"><span data-stu-id="56afd-132">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="56afd-133">Název je používán `endpointConfiguration` atribut propojení koncový bod standardní konfiguraci koncového bodu služby.</span><span class="sxs-lookup"><span data-stu-id="56afd-133">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="56afd-134">Podřízené prvky</span><span class="sxs-lookup"><span data-stu-id="56afd-134">Child elements</span></span>

<span data-ttu-id="56afd-135">Žádné</span><span class="sxs-lookup"><span data-stu-id="56afd-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56afd-136">Nadřazené prvky</span><span class="sxs-lookup"><span data-stu-id="56afd-136">Parent elements</span></span>

| <span data-ttu-id="56afd-137">Prvek</span><span class="sxs-lookup"><span data-stu-id="56afd-137">Element</span></span> | <span data-ttu-id="56afd-138">Popis</span><span class="sxs-lookup"><span data-stu-id="56afd-138">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="56afd-139">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="56afd-139">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | <span data-ttu-id="56afd-140">Kolekce standardních koncových bodů, které jsou předem definované koncových bodů s jedním nebo více jejich vlastnosti (adresy, vazby, kontrakt) pevné.</span><span class="sxs-lookup"><span data-stu-id="56afd-140">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="56afd-141">Příklad</span><span class="sxs-lookup"><span data-stu-id="56afd-141">Example</span></span>

<span data-ttu-id="56afd-142">Následující příklad ukazuje služby naslouchá na zjišťování zprávy pomocí přenosového sdílené net vícesměrového vysílání.</span><span class="sxs-lookup"><span data-stu-id="56afd-142">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="56afd-143">V příkladu explicitně určuje WS-Discovery. dubna 2005 verze.</span><span class="sxs-lookup"><span data-stu-id="56afd-143">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="56afd-144">Konfigurace standardní koncového bodu se definují pro jednotlivé služby a nesmí se sdílet napříč službou.</span><span class="sxs-lookup"><span data-stu-id="56afd-144">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="56afd-145">Pokud jiné služby chtěli mít stejný koncový bod zjišťování, musí být přidán k této službě části stejnou konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="56afd-145">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
```xml
<services>  
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding" 
              address="calculator" 
              contract="ICalculatorService" />  
    <endpoint name="peerNetDiscovery"  
              binding="peerTcpBinding"  
              address="net.p2p://discoveryMesh/multicast"  
              kind="discoveryEndpoint"  
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"  
              bindingConfiguration="discoveryPeerTcpBindingConfig" />      
  </service>  
</services>  
<standardEndpoints>  
  <discoveryEndpoint>  
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"                         
                      version="WSDiscoveryApril2005" />  
  </discoveryEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56afd-146">Viz také</span><span class="sxs-lookup"><span data-stu-id="56afd-146">See also</span></span>

<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>