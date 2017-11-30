---
title: Element &lt;peerAuthentication&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3cc625f5fdb20505f2e36c5a2d37fca0676bbb37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeerauthenticationgt-element"></a><span data-ttu-id="a1f97-102">Element &lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="a1f97-102">&lt;peerAuthentication&gt; Element</span></span>
<span data-ttu-id="a1f97-103">Určuje možnosti ověřování pro klienty peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="a1f97-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="a1f97-104">programování, viz peer-to-peer [Peer-to-Peer sítě](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="a1f97-104"> peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="a1f97-105">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a1f97-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a1f97-106">\<chování ></span><span class="sxs-lookup"><span data-stu-id="a1f97-106">\<behaviors></span></span>  
<span data-ttu-id="a1f97-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a1f97-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="a1f97-108">\<chování ></span><span class="sxs-lookup"><span data-stu-id="a1f97-108">\<behavior></span></span>  
<span data-ttu-id="a1f97-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="a1f97-109">\<clientCredentials></span></span>  
<span data-ttu-id="a1f97-110">\<sdílené ></span><span class="sxs-lookup"><span data-stu-id="a1f97-110">\<peer></span></span>  
<span data-ttu-id="a1f97-111">\<PeerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="a1f97-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f97-112">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a1f97-112">Syntax</span></span>  
  
```xml  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1f97-113">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="a1f97-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a1f97-114">Následující části popisují nadřazené elementy, atributy a podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="a1f97-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1f97-115">Atributy</span><span class="sxs-lookup"><span data-stu-id="a1f97-115">Attributes</span></span>  
  
|<span data-ttu-id="a1f97-116">Atribut</span><span class="sxs-lookup"><span data-stu-id="a1f97-116">Attribute</span></span>|<span data-ttu-id="a1f97-117">Popis</span><span class="sxs-lookup"><span data-stu-id="a1f97-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="a1f97-118">Volitelný řetězec.</span><span class="sxs-lookup"><span data-stu-id="a1f97-118">Optional string.</span></span> <span data-ttu-id="a1f97-119">Typ a sestavení, které slouží k ověření vlastního typu.</span><span class="sxs-lookup"><span data-stu-id="a1f97-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="a1f97-120">Tento atribut musí být nastaven při `certificateValidationMode` je nastaven na `Custom`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="a1f97-121">Volitelné výčtu.</span><span class="sxs-lookup"><span data-stu-id="a1f97-121">Optional enumeration.</span></span> <span data-ttu-id="a1f97-122">Určuje jeden ze tří režimů slouží k ověření přihlašovacích údajů.</span><span class="sxs-lookup"><span data-stu-id="a1f97-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="a1f97-123">Pokud nastavena na `Custom`, pak `customCertificateValidator` musí být uveden také.</span><span class="sxs-lookup"><span data-stu-id="a1f97-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="a1f97-124">Výchozí hodnota je `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="a1f97-125">Volitelné výčtu.</span><span class="sxs-lookup"><span data-stu-id="a1f97-125">Optional enumeration.</span></span> <span data-ttu-id="a1f97-126">Jeden z režimů používá k ověření pro seznamy odvolaných certifikátů (CRL).</span><span class="sxs-lookup"><span data-stu-id="a1f97-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="a1f97-127">Výchozí hodnota je `Online`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="a1f97-128">Volitelné výčtu.</span><span class="sxs-lookup"><span data-stu-id="a1f97-128">Optional enumeration.</span></span> <span data-ttu-id="a1f97-129">Jedno z umístění úložiště dvě systému: `LocalMachine` nebo `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a1f97-130">Tato hodnota se používá, když je klientovi vyjednal certifikát služby.</span><span class="sxs-lookup"><span data-stu-id="a1f97-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="a1f97-131">Ověření se provádí před **důvěryhodné osoby** uložit do umístění zadaného úložiště.</span><span class="sxs-lookup"><span data-stu-id="a1f97-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="a1f97-132">Výchozí hodnota je `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="a1f97-133">customCertificateValidatorType atribut</span><span class="sxs-lookup"><span data-stu-id="a1f97-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="a1f97-134">Hodnota</span><span class="sxs-lookup"><span data-stu-id="a1f97-134">Value</span></span>|<span data-ttu-id="a1f97-135">Popis</span><span class="sxs-lookup"><span data-stu-id="a1f97-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1f97-136">String</span><span class="sxs-lookup"><span data-stu-id="a1f97-136">String</span></span>|<span data-ttu-id="a1f97-137">Určuje název typu a sestavení a další data použít k vyhledání typu.</span><span class="sxs-lookup"><span data-stu-id="a1f97-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="a1f97-138">Název oboru názvů a typ se minimálně, vyžadují.</span><span class="sxs-lookup"><span data-stu-id="a1f97-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="a1f97-139">Volitelné informace zahrnují: název sestavení, číslo verze, jazykové verze a tokenu veřejného klíče.</span><span class="sxs-lookup"><span data-stu-id="a1f97-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="a1f97-140">certificateValidationMode atribut</span><span class="sxs-lookup"><span data-stu-id="a1f97-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="a1f97-141">Hodnota</span><span class="sxs-lookup"><span data-stu-id="a1f97-141">Value</span></span>|<span data-ttu-id="a1f97-142">Popis</span><span class="sxs-lookup"><span data-stu-id="a1f97-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1f97-143">Výčet</span><span class="sxs-lookup"><span data-stu-id="a1f97-143">Enumeration</span></span>|<span data-ttu-id="a1f97-144">Jeden z následujících hodnot: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="a1f97-145">Výchozí hodnota je `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="a1f97-146">Další informace najdete v tématu [práce s certifikáty](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a1f97-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="a1f97-147">revocationMode atribut</span><span class="sxs-lookup"><span data-stu-id="a1f97-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="a1f97-148">Hodnota</span><span class="sxs-lookup"><span data-stu-id="a1f97-148">Value</span></span>|<span data-ttu-id="a1f97-149">Popis</span><span class="sxs-lookup"><span data-stu-id="a1f97-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1f97-150">Výčet</span><span class="sxs-lookup"><span data-stu-id="a1f97-150">Enumeration</span></span>|<span data-ttu-id="a1f97-151">Jeden z následujících hodnot: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="a1f97-152">Výchozí hodnota je `Online`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="a1f97-153">Další informace najdete v tématu [práce s certifikáty](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a1f97-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="a1f97-154">trustedStoreLocation atribut</span><span class="sxs-lookup"><span data-stu-id="a1f97-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="a1f97-155">Hodnota</span><span class="sxs-lookup"><span data-stu-id="a1f97-155">Value</span></span>|<span data-ttu-id="a1f97-156">Popis</span><span class="sxs-lookup"><span data-stu-id="a1f97-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1f97-157">Výčet</span><span class="sxs-lookup"><span data-stu-id="a1f97-157">Enumeration</span></span>|<span data-ttu-id="a1f97-158">Jeden z následujících hodnot: `LocalMachine` nebo `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a1f97-159">Výchozí hodnota je `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="a1f97-160">Pokud klientská aplikace běží pod účtem systému pak certifikát je obvykle v části `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="a1f97-161">Pokud klientská aplikace běží pod účtem uživatele, pak tento certifikát je obvykle v `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1f97-162">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="a1f97-162">Child Elements</span></span>  
 <span data-ttu-id="a1f97-163">Žádné</span><span class="sxs-lookup"><span data-stu-id="a1f97-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1f97-164">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="a1f97-164">Parent Elements</span></span>  
  
|<span data-ttu-id="a1f97-165">Prvek</span><span class="sxs-lookup"><span data-stu-id="a1f97-165">Element</span></span>|<span data-ttu-id="a1f97-166">Popis</span><span class="sxs-lookup"><span data-stu-id="a1f97-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1f97-167">\<sdílené ></span><span class="sxs-lookup"><span data-stu-id="a1f97-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="a1f97-168">Určí pověření používaná pro ověřování klienta do sdílené služby.</span><span class="sxs-lookup"><span data-stu-id="a1f97-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1f97-169">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a1f97-169">Remarks</span></span>  
 <span data-ttu-id="a1f97-170">`<authentication>` Element odpovídá <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> třídy.</span><span class="sxs-lookup"><span data-stu-id="a1f97-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="a1f97-171">Tento element určuje validátor, která se vyvolá při ověřování sousedním sousedním v mřížce.</span><span class="sxs-lookup"><span data-stu-id="a1f97-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="a1f97-172">Když se nové sdílené pokusí navázat připojení sousedním, předá vlastní pověření na odpovídá partnera.</span><span class="sxs-lookup"><span data-stu-id="a1f97-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="a1f97-173">Validátor odpovídající partner je vyvolána k ověření pověření vzdálené strany.</span><span class="sxs-lookup"><span data-stu-id="a1f97-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="a1f97-174">Při každém navázání připojení sdílené v mřížce, oba partneři jsou vzájemně ověřeni, jsou vyvolány význam validátory na obou koncích.</span><span class="sxs-lookup"><span data-stu-id="a1f97-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1f97-175">Příklad</span><span class="sxs-lookup"><span data-stu-id="a1f97-175">Example</span></span>  
 <span data-ttu-id="a1f97-176">Následující kód nastaví režim ověření certifikátu na `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a1f97-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
     <peerAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
     <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1f97-177">Viz také</span><span class="sxs-lookup"><span data-stu-id="a1f97-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="a1f97-178">Práce s certifikáty</span><span class="sxs-lookup"><span data-stu-id="a1f97-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="a1f97-179">Sítě peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="a1f97-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="a1f97-180">Ověřování zpráv rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="a1f97-180">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="a1f97-181">Vlastní ověřování rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="a1f97-181">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="a1f97-182">Zabezpečení aplikací rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="a1f97-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)