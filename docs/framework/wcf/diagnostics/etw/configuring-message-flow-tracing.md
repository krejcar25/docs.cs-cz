---
title: "Konfigurace trasování toku zpráv"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 15571ca2-bee2-47fb-ba10-fcbc09152ad0
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77a7148a0fc96c4a043a06fbfac7b139c7720d4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="configuring-message-flow-tracing"></a><span data-ttu-id="05c5e-102">Konfigurace trasování toku zpráv</span><span class="sxs-lookup"><span data-stu-id="05c5e-102">Configuring Message Flow Tracing</span></span>
<span data-ttu-id="05c5e-103">Když [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] je povolené trasování aktivity, začátku do konce ID aktivit jsou přiřazeny logické aktivity v rámci [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] zásobníku.</span><span class="sxs-lookup"><span data-stu-id="05c5e-103">When [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] activity tracing is enabled, End-To-End Activity IDs are assigned to logical activities throughout the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack.</span></span> <span data-ttu-id="05c5e-104">V [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)], je teď vyšší výkon verze této funkce, která funguje s událostí trasování pro Windows (ETW) názvem trasování toku zpráv.</span><span class="sxs-lookup"><span data-stu-id="05c5e-104">In [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)], there is now a higher performance version of this feature that works with Event Tracing for Windows (ETW) called message flow tracing.</span></span> <span data-ttu-id="05c5e-105">Když je povolené, ID aktivit začátku do konce převzat ze (nebo přiřazená, pokud je prázdný) příchozí zprávy a jsou rozšířen do všech událostí trasování, vydávané po zpráva má byla dekódovat pomocí kanálu.</span><span class="sxs-lookup"><span data-stu-id="05c5e-105">When enabled, End-To-End activity IDs are taken from (or assigned to if empty) incoming messages and are propagated to all tracing events that are emitted after the message has been decoded by the channel.</span></span> <span data-ttu-id="05c5e-106">Zákazníci mohou pomocí této funkce lze po dekódování rekonstrukci toky zprávu s protokoly trasování z jiné služby.</span><span class="sxs-lookup"><span data-stu-id="05c5e-106">Customers can use this feature to reconstruct message flows with trace logs from different services after decoding.</span></span>  
  
 <span data-ttu-id="05c5e-107">Trasování lze povolit po zjištění problému s aplikací a pak zakázáno, jakmile je problém vyřešen.</span><span class="sxs-lookup"><span data-stu-id="05c5e-107">Tracing can be enabled after a problem is detected with the application and then disabled once the problem is resolved.</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="05c5e-108">Povolení trasování</span><span class="sxs-lookup"><span data-stu-id="05c5e-108">Enabling Tracing</span></span>  
 <span data-ttu-id="05c5e-109">Můžete povolit trasování toku zpráv tak na rozhraní .NET Framework 4 `messageFlowTracing` prvku konfigurace `true`, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="05c5e-109">You can enable message flow tracing by setting the .NET Framework 4 `messageFlowTracing` configuration element to `true`, as shown in the following example.</span></span>  
  
```xml  
<system.servicemodel>  
  <diagnostics>  
    <endToEndTracing propagateActivity="true" messageFlowTracing="true" />  
  </diagnostics>  
</system.servicemodel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="05c5e-110">Protože `endToEndTracing` konfigurační prvek nachází v souboru Web.config, nedá se nakonfigurovat dynamicky stejným způsobem jako trasování událostí pro Windows.</span><span class="sxs-lookup"><span data-stu-id="05c5e-110">Because the `endToEndTracing` configuration element resides in a Web.config file, it cannot be dynamically configured in the same way as ETW.</span></span> <span data-ttu-id="05c5e-111">Pro `endToEndTracing` element konfigurace projevila, aplikace musí být recykluje.</span><span class="sxs-lookup"><span data-stu-id="05c5e-111">For the `endToEndTracing` configuration element to take effect, the application must be recycled.</span></span>  
  
 <span data-ttu-id="05c5e-112">Aktivity jsou korelační podle výměny identifikátor s názvem ID aktivity.</span><span class="sxs-lookup"><span data-stu-id="05c5e-112">Activities are correlated by the interchange of an identifier called the activity ID.</span></span> <span data-ttu-id="05c5e-113">Tento identifikátor je identifikátor GUID a je vygenerována třídou System.Diagnostics.CorrelationManager.</span><span class="sxs-lookup"><span data-stu-id="05c5e-113">This identifier is a GUID, and is generated by the System.Diagnostics.CorrelationManager class.</span></span> <span data-ttu-id="05c5e-114">Pokud pracovat s System.Diagnostics.Trace.CorrelationManager.ActivityID, ujistěte se, že je hodnota nastavena na původní při přenosech řízení provádění zpět do kódu WCF.</span><span class="sxs-lookup"><span data-stu-id="05c5e-114">If you manipulate System.Diagnostics.Trace.CorrelationManager.ActivityID, ensure that the value is set to original when execution control transfers back to WCF code.</span></span>  <span data-ttu-id="05c5e-115">Navíc pokud používáte asynchronní programovací model WCF Ujistěte se, že je System.Diagnostics.Trace.CorrelationManager.ActivityID přenášet mezi vláken.</span><span class="sxs-lookup"><span data-stu-id="05c5e-115">Also, if you use an asynchronous WCF programming model ensure that System.Diagnostics.Trace.CorrelationManager.ActivityID is transferred between the threads.</span></span>  
  
## <a name="message-flow-tracing-and-rest-services"></a><span data-ttu-id="05c5e-116">Trasování toku zpráv a služby REST</span><span class="sxs-lookup"><span data-stu-id="05c5e-116">Message Flow Tracing and REST Services</span></span>  
 <span data-ttu-id="05c5e-117">Trasování toku zpráv umožňuje trasování požadavku konce.</span><span class="sxs-lookup"><span data-stu-id="05c5e-117">Message flow tracing allows you to trace a request end to end.</span></span>  <span data-ttu-id="05c5e-118">Založený na protokolu SOAP služby je k ní ID aktivity odeslán v hlavičce protokolu SOAP zprávy.</span><span class="sxs-lookup"><span data-stu-id="05c5e-118">With SOAP-based services an Activity ID is sent in a SOAP message header.</span></span> <span data-ttu-id="05c5e-119">Požadavky REST neobsahují tuto hlavičku, je místo toho použít speciální událostí hlavičku protokolu HTTP.</span><span class="sxs-lookup"><span data-stu-id="05c5e-119">REST requests do not contain this header so a special HTTP event header is used instead.</span></span> <span data-ttu-id="05c5e-120">Následující fragment kódu ukazuje, jak můžete programově načíst hodnotu ID aktivity:</span><span class="sxs-lookup"><span data-stu-id="05c5e-120">The following code snippet shows how you can programmatically retrieve the Activity ID value:</span></span>  
  
```csharp
Object output = null;
if (OperationContext.Current.IncomingMessageProperties.TryGetValue(HttpRequestMessageProperty.Name, out output))
{
   HttpRequestMessageProperty httpHeaders = output as HttpRequestMessageProperty;
   // Retrieve the Activity Id from the HTTP header    string e2eId = httpHeaders.Headers["E2EActivity"];
   // ...
}
```

 <span data-ttu-id="05c5e-121">Prostřednictvím kódu programu, můžete přidat hlavičku pomocí následujícího kódu:</span><span class="sxs-lookup"><span data-stu-id="05c5e-121">You can programmatically add the header using the following code:</span></span>  
  
```csharp  
HttpContent content = new StreamContent(contentStream);  
Guid correlation = Guid.NewGuid();  
content.Headers.Add("E2EActivity", Convert.ToBase64String(correlation.ToByteArray()));  
```