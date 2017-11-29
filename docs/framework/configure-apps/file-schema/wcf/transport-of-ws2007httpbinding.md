---
title: "&lt;transport&gt; – &lt;ws2007HttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 31c5404b29f025af5193386eccafdbeab95cb2cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="84cf7-102">&lt;transport&gt; – &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="84cf7-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="84cf7-103">Definuje nastavení ověřování pro přenos HTTP.</span><span class="sxs-lookup"><span data-stu-id="84cf7-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="84cf7-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="84cf7-104">\<system.serviceModel></span></span>  
<span data-ttu-id="84cf7-105">\<vazby ></span><span class="sxs-lookup"><span data-stu-id="84cf7-105">\<bindings></span></span>  
<span data-ttu-id="84cf7-106">\<– ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="84cf7-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="84cf7-107">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="84cf7-107">\<binding></span></span>  
<span data-ttu-id="84cf7-108">\<zabezpečení ></span><span class="sxs-lookup"><span data-stu-id="84cf7-108">\<security></span></span>  
<span data-ttu-id="84cf7-109">\<přenos ></span><span class="sxs-lookup"><span data-stu-id="84cf7-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84cf7-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="84cf7-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="84cf7-111">Typ</span><span class="sxs-lookup"><span data-stu-id="84cf7-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84cf7-112">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="84cf7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="84cf7-113">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="84cf7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84cf7-114">Atributy</span><span class="sxs-lookup"><span data-stu-id="84cf7-114">Attributes</span></span>  
  
|<span data-ttu-id="84cf7-115">Atribut</span><span class="sxs-lookup"><span data-stu-id="84cf7-115">Attribute</span></span>|<span data-ttu-id="84cf7-116">Popis</span><span class="sxs-lookup"><span data-stu-id="84cf7-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="84cf7-117">Určuje, že pověření použitá k ověření klienta ke službě.</span><span class="sxs-lookup"><span data-stu-id="84cf7-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="84cf7-118">Tento atribut je typu <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="84cf7-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="84cf7-119">Určuje, že pověření použitá k ověření klienta pro proxy server domény.</span><span class="sxs-lookup"><span data-stu-id="84cf7-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="84cf7-120">Tento atribut je typu <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="84cf7-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="84cf7-121">Sféra ověřování hodnotou hash nebo základní ověřování.</span><span class="sxs-lookup"><span data-stu-id="84cf7-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="84cf7-122">Výchozí hodnota je prázdný řetězec.</span><span class="sxs-lookup"><span data-stu-id="84cf7-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="84cf7-123">Sféra ověření určuje alespoň název hostitele, který provádí ověřování.</span><span class="sxs-lookup"><span data-stu-id="84cf7-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="84cf7-124">Můžete také specifikovat kolekci uživatelů, kteří mají přístup.</span><span class="sxs-lookup"><span data-stu-id="84cf7-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="84cf7-125">Uživatele můžete dotazovat sféry ověřování k určení, který z nich několik možných uživatelská jména a hesla je možné.</span><span class="sxs-lookup"><span data-stu-id="84cf7-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="84cf7-126">clientCredentialType atribut</span><span class="sxs-lookup"><span data-stu-id="84cf7-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="84cf7-127">Hodnota</span><span class="sxs-lookup"><span data-stu-id="84cf7-127">Value</span></span>|<span data-ttu-id="84cf7-128">Popis</span><span class="sxs-lookup"><span data-stu-id="84cf7-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="84cf7-129">Žádné</span><span class="sxs-lookup"><span data-stu-id="84cf7-129">None</span></span>|<span data-ttu-id="84cf7-130">Zabezpečení je vypnuté.</span><span class="sxs-lookup"><span data-stu-id="84cf7-130">Security is disabled.</span></span>|  
|<span data-ttu-id="84cf7-131">Základní</span><span class="sxs-lookup"><span data-stu-id="84cf7-131">Basic</span></span>|<span data-ttu-id="84cf7-132">Používá základní ověřování.</span><span class="sxs-lookup"><span data-stu-id="84cf7-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="84cf7-133">Ověřování algoritmem Digest</span><span class="sxs-lookup"><span data-stu-id="84cf7-133">Digest</span></span>|<span data-ttu-id="84cf7-134">Použití ověřování algoritmem digest.</span><span class="sxs-lookup"><span data-stu-id="84cf7-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="84cf7-135">NTLM</span><span class="sxs-lookup"><span data-stu-id="84cf7-135">Ntlm</span></span>|<span data-ttu-id="84cf7-136">Ověřování protokolem NTLM se používá jako nouzové řešení s doménou systému Windows.</span><span class="sxs-lookup"><span data-stu-id="84cf7-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="84cf7-137">Windows</span><span class="sxs-lookup"><span data-stu-id="84cf7-137">Windows</span></span>|<span data-ttu-id="84cf7-138">Používá integrované ověřování systému Windows.</span><span class="sxs-lookup"><span data-stu-id="84cf7-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="84cf7-139">certifikát</span><span class="sxs-lookup"><span data-stu-id="84cf7-139">Certificate</span></span>|<span data-ttu-id="84cf7-140">K ověření klienta používá certifikáty X.509.</span><span class="sxs-lookup"><span data-stu-id="84cf7-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="84cf7-141">proxyCredentialType atribut</span><span class="sxs-lookup"><span data-stu-id="84cf7-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="84cf7-142">Hodnota</span><span class="sxs-lookup"><span data-stu-id="84cf7-142">Value</span></span>|<span data-ttu-id="84cf7-143">Popis</span><span class="sxs-lookup"><span data-stu-id="84cf7-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="84cf7-144">Žádné</span><span class="sxs-lookup"><span data-stu-id="84cf7-144">None</span></span>|<span data-ttu-id="84cf7-145">Zabezpečení je vypnuté.</span><span class="sxs-lookup"><span data-stu-id="84cf7-145">Security is disabled.</span></span>|  
|<span data-ttu-id="84cf7-146">Základní</span><span class="sxs-lookup"><span data-stu-id="84cf7-146">Basic</span></span>|<span data-ttu-id="84cf7-147">Používá základní ověřování.</span><span class="sxs-lookup"><span data-stu-id="84cf7-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="84cf7-148">Ověřování algoritmem Digest</span><span class="sxs-lookup"><span data-stu-id="84cf7-148">Digest</span></span>|<span data-ttu-id="84cf7-149">Použití ověřování algoritmem digest.</span><span class="sxs-lookup"><span data-stu-id="84cf7-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="84cf7-150">NTLM</span><span class="sxs-lookup"><span data-stu-id="84cf7-150">Ntlm</span></span>|<span data-ttu-id="84cf7-151">Používá protokol NTLM jako nouzové řešení s doménou systému Windows.</span><span class="sxs-lookup"><span data-stu-id="84cf7-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="84cf7-152">Windows</span><span class="sxs-lookup"><span data-stu-id="84cf7-152">Windows</span></span>|<span data-ttu-id="84cf7-153">Používá integrované ověřování systému Windows.</span><span class="sxs-lookup"><span data-stu-id="84cf7-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="84cf7-154">certifikát</span><span class="sxs-lookup"><span data-stu-id="84cf7-154">Certificate</span></span>|<span data-ttu-id="84cf7-155">K ověření klienta používá certifikáty X.509.</span><span class="sxs-lookup"><span data-stu-id="84cf7-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84cf7-156">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="84cf7-156">Child Elements</span></span>  
 <span data-ttu-id="84cf7-157">Žádné</span><span class="sxs-lookup"><span data-stu-id="84cf7-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84cf7-158">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="84cf7-158">Parent Elements</span></span>  
  
|<span data-ttu-id="84cf7-159">Prvek</span><span class="sxs-lookup"><span data-stu-id="84cf7-159">Element</span></span>|<span data-ttu-id="84cf7-160">Popis</span><span class="sxs-lookup"><span data-stu-id="84cf7-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84cf7-161">\<zabezpečení ></span><span class="sxs-lookup"><span data-stu-id="84cf7-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="84cf7-162">Představuje možnosti zabezpečení [ \<– ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span><span class="sxs-lookup"><span data-stu-id="84cf7-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84cf7-163">Viz také</span><span class="sxs-lookup"><span data-stu-id="84cf7-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="84cf7-164">Zabezpečení služeb a klientů</span><span class="sxs-lookup"><span data-stu-id="84cf7-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="84cf7-165">Vazby</span><span class="sxs-lookup"><span data-stu-id="84cf7-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="84cf7-166">Konfigurace vazeb poskytovaných systémem</span><span class="sxs-lookup"><span data-stu-id="84cf7-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="84cf7-167">Používání vazeb ke konfiguraci služby Windows Communication Foundation a klienty</span><span class="sxs-lookup"><span data-stu-id="84cf7-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="84cf7-168">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="84cf7-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)