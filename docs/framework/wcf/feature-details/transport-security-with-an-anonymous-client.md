---
title: "Zabezpečení přenosu s anonymním klientem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: a4d4180a0a60e062ab6d8872b153d5bc8b416708
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="db617-102">Zabezpečení přenosu s anonymním klientem</span><span class="sxs-lookup"><span data-stu-id="db617-102">Transport Security with an Anonymous Client</span></span>
<span data-ttu-id="db617-103">To [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] scénáři se používá k zajištění důvěrnosti a integrity zabezpečení přenosu (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="db617-103">This [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="db617-104">Server musí být ověřeny pomocí certifikátu vrstvy SSL (Secure Sockets) a klienti musí důvěřovat certifikátu serveru.</span><span class="sxs-lookup"><span data-stu-id="db617-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="db617-105">Klient není ověřen jakýmkoli mechanismem a je proto anonymní.</span><span class="sxs-lookup"><span data-stu-id="db617-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>  
  
 <span data-ttu-id="db617-106">Ukázkovou aplikaci, najdete v části [zabezpečení přenosu WS](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="db617-106">For a sample application, see [WS Transport Security](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="db617-107">zabezpečení přenosu najdete v tématu [Přehled zabezpečení přenosu](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="db617-107"> transport security, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="db617-108">pomocí certifikátu se službou, najdete v tématu [práce s certifikáty](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) a [postup: Nakonfigurujte certifikát protokolu SSL Port](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="db617-108"> using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 <span data-ttu-id="db617-109">![Pomocí zabezpečení přenosu s anonymním klientem](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span><span class="sxs-lookup"><span data-stu-id="db617-109">![Using transport security with an anonymous client](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span></span>  
  
|<span data-ttu-id="db617-110">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="db617-110">Characteristic</span></span>|<span data-ttu-id="db617-111">Popis</span><span class="sxs-lookup"><span data-stu-id="db617-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="db617-112">Režim zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="db617-112">Security Mode</span></span>|<span data-ttu-id="db617-113">Přenos</span><span class="sxs-lookup"><span data-stu-id="db617-113">Transport</span></span>|  
|<span data-ttu-id="db617-114">Interoperabilita</span><span class="sxs-lookup"><span data-stu-id="db617-114">Interoperability</span></span>|<span data-ttu-id="db617-115">S existujících webových služeb a klientů</span><span class="sxs-lookup"><span data-stu-id="db617-115">With existing Web services and clients</span></span>|  
|<span data-ttu-id="db617-116">Ověřování (Server)</span><span class="sxs-lookup"><span data-stu-id="db617-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="db617-117">Ověřování (klient)</span><span class="sxs-lookup"><span data-stu-id="db617-117">Authentication (Client)</span></span>|<span data-ttu-id="db617-118">Ano</span><span class="sxs-lookup"><span data-stu-id="db617-118">Yes</span></span><br /><br /> <span data-ttu-id="db617-119">Úroveň aplikace (bez [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] podporu)</span><span class="sxs-lookup"><span data-stu-id="db617-119">Application level (no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] support)</span></span>|  
|<span data-ttu-id="db617-120">Integrita</span><span class="sxs-lookup"><span data-stu-id="db617-120">Integrity</span></span>|<span data-ttu-id="db617-121">Ano</span><span class="sxs-lookup"><span data-stu-id="db617-121">Yes</span></span>|  
|<span data-ttu-id="db617-122">Důvěrnost</span><span class="sxs-lookup"><span data-stu-id="db617-122">Confidentiality</span></span>|<span data-ttu-id="db617-123">Ano</span><span class="sxs-lookup"><span data-stu-id="db617-123">Yes</span></span>|  
|<span data-ttu-id="db617-124">Přenos</span><span class="sxs-lookup"><span data-stu-id="db617-124">Transport</span></span>|<span data-ttu-id="db617-125">PROTOKOL HTTPS</span><span class="sxs-lookup"><span data-stu-id="db617-125">HTTPS</span></span>|  
|<span data-ttu-id="db617-126">Vazba</span><span class="sxs-lookup"><span data-stu-id="db617-126">Binding</span></span>|<span data-ttu-id="db617-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="db617-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>|  
  
## <a name="service"></a><span data-ttu-id="db617-128">Služba</span><span class="sxs-lookup"><span data-stu-id="db617-128">Service</span></span>  
 <span data-ttu-id="db617-129">Následující kód a konfigurace jsou určená ke spuštění nezávisle.</span><span class="sxs-lookup"><span data-stu-id="db617-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="db617-130">Proveďte jednu z těchto akcí:</span><span class="sxs-lookup"><span data-stu-id="db617-130">Do one of the following:</span></span>  
  
-   <span data-ttu-id="db617-131">Vytvořte samostatnou službu pomocí kódu žádnou konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="db617-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="db617-132">Vytvoření služby pomocí zadaných konfigurací, ale nejsou definovány žádné koncové body.</span><span class="sxs-lookup"><span data-stu-id="db617-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="db617-133">Kód</span><span class="sxs-lookup"><span data-stu-id="db617-133">Code</span></span>  
 <span data-ttu-id="db617-134">Následující kód ukazuje, jak vytvořit koncový bod pomocí zabezpečení přenosu:</span><span class="sxs-lookup"><span data-stu-id="db617-134">The following code shows how to create an endpoint using transport security:</span></span>  
  
 [!code-csharp[c_SecurityScenarios#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
 [!code-vb[c_SecurityScenarios#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]  
  
### <a name="configuration"></a><span data-ttu-id="db617-135">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="db617-135">Configuration</span></span>  
 <span data-ttu-id="db617-136">Následující kód nastaví stejný koncový bod pomocí konfigurace.</span><span class="sxs-lookup"><span data-stu-id="db617-136">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="db617-137">Klient není ověřen jakýmkoli mechanismem a je proto anonymní.</span><span class="sxs-lookup"><span data-stu-id="db617-137">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="db617-138">Klient</span><span class="sxs-lookup"><span data-stu-id="db617-138">Client</span></span>  
 <span data-ttu-id="db617-139">Následující kód a konfigurace jsou určená ke spuštění nezávisle.</span><span class="sxs-lookup"><span data-stu-id="db617-139">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="db617-140">Proveďte jednu z těchto akcí:</span><span class="sxs-lookup"><span data-stu-id="db617-140">Do one of the following:</span></span>  
  
-   <span data-ttu-id="db617-141">Vytvořte samostatnou klienta pomocí kódu (a kód klienta).</span><span class="sxs-lookup"><span data-stu-id="db617-141">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="db617-142">Vytvoření klienta, které nejsou definovány žádné adresy koncových bodů.</span><span class="sxs-lookup"><span data-stu-id="db617-142">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="db617-143">Místo toho použijte konstruktor klienta, který přijímá jako argument Název konfigurace.</span><span class="sxs-lookup"><span data-stu-id="db617-143">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="db617-144">Příklad:</span><span class="sxs-lookup"><span data-stu-id="db617-144">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="db617-145">Kód</span><span class="sxs-lookup"><span data-stu-id="db617-145">Code</span></span>  
 [!code-csharp[c_SecurityScenarios#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
 [!code-vb[c_SecurityScenarios#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]  
  
### <a name="configuration"></a><span data-ttu-id="db617-146">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="db617-146">Configuration</span></span>  
 <span data-ttu-id="db617-147">Následující konfigurace můžete použít místo kód nastavit službu.</span><span class="sxs-lookup"><span data-stu-id="db617-147">The following configuration can be used instead of the code to set up the service.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db617-148">Viz také</span><span class="sxs-lookup"><span data-stu-id="db617-148">See Also</span></span>  
 [<span data-ttu-id="db617-149">Přehled zabezpečení</span><span class="sxs-lookup"><span data-stu-id="db617-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="db617-150">Zabezpečení přenosu WS</span><span class="sxs-lookup"><span data-stu-id="db617-150">WS Transport Security</span></span>](../../../../docs/framework/wcf/samples/ws-transport-security.md)  
 [<span data-ttu-id="db617-151">Přehled zabezpečení přenosu</span><span class="sxs-lookup"><span data-stu-id="db617-151">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 [<span data-ttu-id="db617-152">Model zabezpečení pro Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="db617-152">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)