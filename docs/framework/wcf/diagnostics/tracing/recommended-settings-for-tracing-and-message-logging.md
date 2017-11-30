---
title: "Doporučené nastavení pro trasování a protokolování zpráv"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b6986c775db50ea5b763288f8f3b9bdcf1bf7e67
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="65178-102">Doporučené nastavení pro trasování a protokolování zpráv</span><span class="sxs-lookup"><span data-stu-id="65178-102">Recommended Settings for Tracing and Message Logging</span></span>
<span data-ttu-id="65178-103">Toto téma popisuje doporučené trasování a nastavení protokolování zpráv pro různá provozní prostředí.</span><span class="sxs-lookup"><span data-stu-id="65178-103">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="65178-104">Doporučená nastavení pro produkční prostředí</span><span class="sxs-lookup"><span data-stu-id="65178-104">Recommended Settings for a Production Environment</span></span>  
 <span data-ttu-id="65178-105">Pro produkční prostředí, pokud používáte zdrojů trasování WCF, nastavte `switchValue` na upozornění.</span><span class="sxs-lookup"><span data-stu-id="65178-105">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="65178-106">Pokud používáte WCF `System.ServiceModel` zdroj trasování, nastavte `switchValue` atribut `Warning` a `propagateActivity` atribut `true`.</span><span class="sxs-lookup"><span data-stu-id="65178-106">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="65178-107">Pokud používáte zdroj trasování definovaný uživatelem, nastavte `switchValue` atribut `Warning, ActivityTracing`.</span><span class="sxs-lookup"><span data-stu-id="65178-107">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="65178-108">To lze provést ručně pomocí [nástroj Configuration Editor (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="65178-108">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="65178-109">Pokud očekáváte není podle výkonu, můžete nastavit `switchValue` atribut `Information` ve všech výše uvedených případech, který generuje poměrně velké množství dat trasování.</span><span class="sxs-lookup"><span data-stu-id="65178-109">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="65178-110">Následující příklad ukazuje tyto doporučené nastavení.</span><span class="sxs-lookup"><span data-stu-id="65178-110">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="65178-111">Doporučená nastavení pro nasazení nebo ladění</span><span class="sxs-lookup"><span data-stu-id="65178-111">Recommended Settings for Deployment or Debugging</span></span>  
 <span data-ttu-id="65178-112">Pro nasazení nebo ladění prostředí, zvolte `Information` nebo `Verbose`, spolu s `ActivityTracing` pro buď uživatelem definované nebo `System.ServiceModel` zdroj trasování.</span><span class="sxs-lookup"><span data-stu-id="65178-112">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="65178-113">K vylepšení, ladění, měli byste také přidat na další trasování zdroj (`System.ServiceModel.MessageLogging`) ke konfiguraci povolit protokolování zpráv.</span><span class="sxs-lookup"><span data-stu-id="65178-113">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="65178-114">Všimněte si, že `switchValue` atribut nemá žádný vliv na tento zdroj trasování.</span><span class="sxs-lookup"><span data-stu-id="65178-114">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="65178-115">Následující příklad ukazuje doporučená nastavení, pomocí sdílené naslouchací proces, který využívá `XmlWriterTraceListener`.</span><span class="sxs-lookup"><span data-stu-id="65178-115">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"   
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="65178-116">WMI používá k úpravě nastavení</span><span class="sxs-lookup"><span data-stu-id="65178-116">Using WMI to Modify Settings</span></span>  
 <span data-ttu-id="65178-117">Chcete-li změnit nastavení konfigurace v době běhu můžete použít rozhraní WMI (povolením `wmiProviderEnabled` atribut v konfiguraci, jak je předvedeno v dříve příklad konfigurace).</span><span class="sxs-lookup"><span data-stu-id="65178-117">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="65178-118">Například můžete v rámci nástroje CIM Studio WMI Pokud chcete změnit úrovně zdroj trasování z upozornění na informace za běhu.</span><span class="sxs-lookup"><span data-stu-id="65178-118">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="65178-119">Byste měli vědět, že mohou být velmi vysoký výkon náklady za provozu ladění tímto způsobem.</span><span class="sxs-lookup"><span data-stu-id="65178-119">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="65178-120">Další informace o používání rozhraní WMI najdete v tématu [pomocí rozhraní Windows Management Instrumentation pro diagnostiku](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="65178-120">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="65178-121">Povolit korelační události v trasování rozhraní ASP.NET</span><span class="sxs-lookup"><span data-stu-id="65178-121">Enable Correlated Events in ASP.NET Tracing</span></span>  
 <span data-ttu-id="65178-122">Události ASP.NET nenastavujte ID korelace (ID), pokud je zapnutá trasování událostí ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="65178-122">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="65178-123">Zobrazte korelační události správně, budete muset zapnout ASP.NET události trasování, pomocí následujícího příkazu v konzole pro příkaz, který lze vyvolat přechodem na **spustit**, **spustit** a typ **cmd** ,</span><span class="sxs-lookup"><span data-stu-id="65178-123">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="65178-124">Chcete-li vypnout trasování událostí pro technologii ASP.NET, použijte následující příkaz,</span><span class="sxs-lookup"><span data-stu-id="65178-124">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```  
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="65178-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="65178-125">See Also</span></span>  
 [<span data-ttu-id="65178-126">Pomocí rozhraní Windows Management Instrumentation pro diagnostiku</span><span class="sxs-lookup"><span data-stu-id="65178-126">Using Windows Management Instrumentation for Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)