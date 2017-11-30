---
title: '&lt;messageLogging&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5b232e3faf1e0e8976b0c08264c8ba03988902a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagelogginggt"></a><span data-ttu-id="4f388-102">&lt;messageLogging&gt;</span><span class="sxs-lookup"><span data-stu-id="4f388-102">&lt;messageLogging&gt;</span></span>
<span data-ttu-id="4f388-103">Tento element definuje nastavení pro protokolování zpráv možnosti Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4f388-103">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="4f388-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4f388-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4f388-105">\<diagnostické ></span><span class="sxs-lookup"><span data-stu-id="4f388-105">\<diagnostic></span></span>  
<span data-ttu-id="4f388-106">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="4f388-106">\<messageLogging></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f388-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4f388-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <messageLogging logEntireMessage="Boolean"  
          logMalformedMessages="Boolean"  
          logMessagesAtServiceLevel="Boolean"  
          logMessagesAtTransportLevel="Boolean"  
                    maxMessagesToLog="Integer"  
          maxSizeOfMessageToLog="Integer" >  
          <filters>  
                            <clear />  
          </filters>  
       </messageLogging>  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f388-108">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="4f388-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4f388-109">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="4f388-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f388-110">Atributy</span><span class="sxs-lookup"><span data-stu-id="4f388-110">Attributes</span></span>  
  
|<span data-ttu-id="4f388-111">Atribut</span><span class="sxs-lookup"><span data-stu-id="4f388-111">Attribute</span></span>|<span data-ttu-id="4f388-112">Popis</span><span class="sxs-lookup"><span data-stu-id="4f388-112">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="4f388-113">Logická hodnota, která určuje, zda je zaznamenána celé zprávy (záhlaví zprávy a text).</span><span class="sxs-lookup"><span data-stu-id="4f388-113">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="4f388-114">Výchozí hodnota je `false`, což znamená, že pouze záhlaví zprávy přihlášen.</span><span class="sxs-lookup"><span data-stu-id="4f388-114">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="4f388-115">Toto nastavení ovlivňuje všechny úrovně protokolování zpráv (service, přenos a chybná).</span><span class="sxs-lookup"><span data-stu-id="4f388-115">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="4f388-116">Logická hodnota, která určuje, zda mají být protokolovány poškozených zpráv.</span><span class="sxs-lookup"><span data-stu-id="4f388-116">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="4f388-117">Poškozených zpráv nepočítá `maxMessagesToLog`.</span><span class="sxs-lookup"><span data-stu-id="4f388-117">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="4f388-118">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="4f388-118">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="4f388-119">Logická hodnota, která určuje, zda jsou zprávy nalezeny na úrovni služby (před šifrování a přenosu související transformací).</span><span class="sxs-lookup"><span data-stu-id="4f388-119">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="4f388-120">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="4f388-120">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="4f388-121">Logická hodnota, která určuje, zda jsou zprávy nalezeny na úrovni přenosu.</span><span class="sxs-lookup"><span data-stu-id="4f388-121">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="4f388-122">Jsou použity žádné filtry zadané v konfiguračním souboru, a budou trasovány pouze zprávy, které splňují podmínky filtrů.</span><span class="sxs-lookup"><span data-stu-id="4f388-122">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="4f388-123">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="4f388-123">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="4f388-124">Kladné celé číslo, které určuje maximální počet zpráv do protokolu.</span><span class="sxs-lookup"><span data-stu-id="4f388-124">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="4f388-125">Výchozí hodnota je 1 000.</span><span class="sxs-lookup"><span data-stu-id="4f388-125">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="4f388-126">Kladné celé číslo, které určuje maximální velikost v bajtech zprávy do protokolu.</span><span class="sxs-lookup"><span data-stu-id="4f388-126">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="4f388-127">Zprávy, které jsou větší než limit se nebudou protokolovat.</span><span class="sxs-lookup"><span data-stu-id="4f388-127">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="4f388-128">Toto nastavení ovlivňuje všechny úrovně trasování.</span><span class="sxs-lookup"><span data-stu-id="4f388-128">This setting affects all trace levels.</span></span> <span data-ttu-id="4f388-129">Výchozí hodnota je 262144(0x4000).</span><span class="sxs-lookup"><span data-stu-id="4f388-129">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f388-130">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="4f388-130">Child Elements</span></span>  
  
|<span data-ttu-id="4f388-131">Prvek</span><span class="sxs-lookup"><span data-stu-id="4f388-131">Element</span></span>|<span data-ttu-id="4f388-132">Popis</span><span class="sxs-lookup"><span data-stu-id="4f388-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f388-133">filtry</span><span class="sxs-lookup"><span data-stu-id="4f388-133">filters</span></span>|<span data-ttu-id="4f388-134">`filters` Element obsahuje kolekci filtrů XPath.</span><span class="sxs-lookup"><span data-stu-id="4f388-134">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="4f388-135">Když je povoleno protokolování přenosu zpráv (`logMessagesAtTransportLevel` je `true`), bude do protokolu pouze zprávy odpovídající filtry.</span><span class="sxs-lookup"><span data-stu-id="4f388-135">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="4f388-136">Filtry se použijí jenom v přenosové vrstvě.</span><span class="sxs-lookup"><span data-stu-id="4f388-136">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="4f388-137">Protokolování úrovně a poškozených zpráv služby nemá vliv filtry.</span><span class="sxs-lookup"><span data-stu-id="4f388-137">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="4f388-138">Atribut pouze pro tento element `filter`, je třída XpathFilter.</span><span class="sxs-lookup"><span data-stu-id="4f388-138">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f388-139">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="4f388-139">Parent Elements</span></span>  
  
|<span data-ttu-id="4f388-140">Prvek</span><span class="sxs-lookup"><span data-stu-id="4f388-140">Element</span></span>|<span data-ttu-id="4f388-141">Popis</span><span class="sxs-lookup"><span data-stu-id="4f388-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f388-142">diagnostika</span><span class="sxs-lookup"><span data-stu-id="4f388-142">diagnostics</span></span>|<span data-ttu-id="4f388-143">Definuje nastavení WCF pro modul runtime kontroly a řízení pro správce.</span><span class="sxs-lookup"><span data-stu-id="4f388-143">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f388-144">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4f388-144">Remarks</span></span>  
 <span data-ttu-id="4f388-145">Zprávy se zaznamenávají na třech různých úrovních v zásobníku: service, přenos a je poškozený.</span><span class="sxs-lookup"><span data-stu-id="4f388-145">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="4f388-146">Každá úroveň je možné aktivovat samostatně.</span><span class="sxs-lookup"><span data-stu-id="4f388-146">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="4f388-147">Filtry jazyka XPath lze přidat k protokolování konkrétní zpráv na úrovni přenosu a služby.</span><span class="sxs-lookup"><span data-stu-id="4f388-147">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="4f388-148">Pokud jsou definovány žádné filtry, jsou protokolovány všechny zprávy.</span><span class="sxs-lookup"><span data-stu-id="4f388-148">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="4f388-149">Filtry se použijí jenom u záhlaví zprávy.</span><span class="sxs-lookup"><span data-stu-id="4f388-149">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="4f388-150">Text se ignoruje.</span><span class="sxs-lookup"><span data-stu-id="4f388-150">The body is ignored.</span></span> <span data-ttu-id="4f388-151">WCF ignoruje tělo zprávy ke zlepšení výkonu.</span><span class="sxs-lookup"><span data-stu-id="4f388-151">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="4f388-152">Pokud chcete filtrovat podle obsah textu, můžete vytvořit vlastní naslouchací proces s filtr, který nemá tak.</span><span class="sxs-lookup"><span data-stu-id="4f388-152">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="4f388-153">Budete muset vytvořit naslouchací proces trasování aktivujte trasování zpráv.</span><span class="sxs-lookup"><span data-stu-id="4f388-153">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="4f388-154">Naslouchací proces samotné může být jakékoli naslouchací proces, který funguje s <xref:System.Diagnostics> architektura trasování.</span><span class="sxs-lookup"><span data-stu-id="4f388-154">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="4f388-155">Následující příklad ukazuje, jak vytvořit naslouchací proces.</span><span class="sxs-lookup"><span data-stu-id="4f388-155">The following example demonstrates how to create such a listener.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
          <source name="System.ServiceModel" switchValue="Verbose">  
              <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="ServiceModel Listener" traceOutputOptions="None" />  
               </listeners>  
        </source>  
            <source name="System.ServiceModel.MessageLogging">  
                <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="MessageLogging Listener" traceOutputOptions="None"/>  
               </listeners>  
        </source>  
    </sources>  
     <sharedListeners>  
            <add initializeData="C:\ItProTools\TraceLog.xml"  
                    type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
                    name="ServiceModel Listener"  
                    traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />  
            <add initializeData="C:\ItProTools\MessageLog.log"  
                    type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
                   name="MessageLogging Listener"  
                   traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />  
    </sharedListeners>  
</system.diagnostics>  
```  
  
## <a name="example"></a><span data-ttu-id="4f388-156">Příklad</span><span class="sxs-lookup"><span data-stu-id="4f388-156">Example</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"  
    logMalformedMessages="true"  
    logMessagesAtServiceLevel="true"  
    logMessagesAtTransportLevel="true"  
    maxMessagesToLog="42"  
    maxSizeOfMessageToLog="42">  
     <filters>  
         <clear />  
     </filters>  
 </messageLogging>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f388-157">Viz také</span><span class="sxs-lookup"><span data-stu-id="4f388-157">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 [<span data-ttu-id="4f388-158">Konfigurace protokolování zpráv</span><span class="sxs-lookup"><span data-stu-id="4f388-158">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)