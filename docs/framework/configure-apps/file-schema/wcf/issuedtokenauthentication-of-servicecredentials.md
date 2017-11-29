---
title: "&lt;issuedTokenAuthentication&gt; – &lt;serviceCredentials&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d8e3c7df0108c6f8656827c6c0795dcb9fe3a9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuedtokenauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="9f6c0-102">&lt;issuedTokenAuthentication&gt; – &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="9f6c0-102">&lt;issuedTokenAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="9f6c0-103">Určuje vlastní tokenem vydaným jako přihlašovací údaje služby.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-103">Specifies a custom token issued as a service credential.</span></span>  
  
 <span data-ttu-id="9f6c0-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9f6c0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9f6c0-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="9f6c0-105">\<behaviors></span></span>  
<span data-ttu-id="9f6c0-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9f6c0-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9f6c0-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="9f6c0-107">\<behavior></span></span>  
<span data-ttu-id="9f6c0-108">\<– serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="9f6c0-108">\<serviceCredentials></span></span>  
<span data-ttu-id="9f6c0-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="9f6c0-109">\<issuedTokenAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f6c0-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9f6c0-110">Syntax</span></span>  
  
```xml  
<issuedTokenAuthentication   
   allowUntrustedRsaIssuers="Boolean"  
   audienceUriMode="Always/BearerKeyOnly/Never"  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   samlSerializer="String"  
    trustedStoreLocation="CurrentUser/LocalMachine">  
      <allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
      </allowedAudienceUris>  
      <knownCertificates>   
         <add findValue="String"  
                 storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
      </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f6c0-111">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="9f6c0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9f6c0-112">Následující části popisují nadřazené elementy, atributy a podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="9f6c0-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f6c0-113">Atributy</span><span class="sxs-lookup"><span data-stu-id="9f6c0-113">Attributes</span></span>  
  
|<span data-ttu-id="9f6c0-114">Atribut</span><span class="sxs-lookup"><span data-stu-id="9f6c0-114">Attribute</span></span>|<span data-ttu-id="9f6c0-115">Popis</span><span class="sxs-lookup"><span data-stu-id="9f6c0-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="9f6c0-116">Získá sadu cíle identifikátory URI pro kterou <xref:System.IdentityModel.Tokens.SamlSecurityToken> token zabezpečení je možné cílit pro Chcete-li být považován za platný podle <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-116">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="9f6c0-117">Další informace o použití tohoto atributu naleznete v části <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="9f6c0-118">Logická hodnota, která určuje, jestli jsou povolená nedůvěryhodné vystavitelů certifikátů RSA.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-118">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="9f6c0-119">Certifikáty jsou podepsané certifikační autority (CA) k ověření pravosti.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-119">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="9f6c0-120">Nedůvěryhodné vystavitele je certifikační Autorita, která není zadán důvěru k podepisování certifikátů.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-120">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="9f6c0-121">Získá hodnotu, která určuje, zda <xref:System.IdentityModel.Tokens.SamlSecurityToken> token zabezpečení <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> má být ověřen.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-121">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="9f6c0-122">Tato hodnota je typu <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-122">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="9f6c0-123">Další informace o použití tohoto atributu naleznete v části <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-123">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="9f6c0-124">Nastaví režim ověření certifikátu.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-124">Sets the certificate validation mode.</span></span> <span data-ttu-id="9f6c0-125">Mezi platné hodnoty <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-125">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="9f6c0-126">Pokud nastavena na `Custom`, pak `customCertificateValidator` musí být uveden také.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-126">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="9f6c0-127">Výchozí hodnota je `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-127">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="9f6c0-128">Volitelný řetězec.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-128">Optional string.</span></span> <span data-ttu-id="9f6c0-129">Typ a sestavení, které slouží k ověření vlastního typu.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-129">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="9f6c0-130">Tento atribut musí být nastaven při `certificateValidationMode` je nastaven na `Custom`.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-130">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="9f6c0-131">Nastaví režim odvolaných certifikátů, který určuje, zda dojde k kontrolu odvolaných certifikátů, a pokud probíhá online nebo offline.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-131">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="9f6c0-132">Tento atribut je typu <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-132">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="9f6c0-133">Atribut volitelný řetězec, který určuje typ SamlSerializer, který se používá pro přihlašovací údaje služby.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-133">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="9f6c0-134">Výchozí hodnota je prázdný řetězec.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-134">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="9f6c0-135">Volitelné výčtu.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-135">Optional enumeration.</span></span> <span data-ttu-id="9f6c0-136">Jedno z umístění úložiště dvě systému: `LocalMachine` nebo `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f6c0-137">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="9f6c0-137">Child Elements</span></span>  
  
|<span data-ttu-id="9f6c0-138">Prvek</span><span class="sxs-lookup"><span data-stu-id="9f6c0-138">Element</span></span>|<span data-ttu-id="9f6c0-139">Popis</span><span class="sxs-lookup"><span data-stu-id="9f6c0-139">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="9f6c0-140">Určuje kolekci <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> prvky, které určuje důvěryhodných vystavitelů pro přihlašovací údaje služby.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-140">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9f6c0-141">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="9f6c0-141">Parent Elements</span></span>  
  
|<span data-ttu-id="9f6c0-142">Prvek</span><span class="sxs-lookup"><span data-stu-id="9f6c0-142">Element</span></span>|<span data-ttu-id="9f6c0-143">Popis</span><span class="sxs-lookup"><span data-stu-id="9f6c0-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f6c0-144">\<– serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="9f6c0-144">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="9f6c0-145">Určuje pověření, která se použije v ověřování služby a nastavení související s ověření pověření klienta.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-145">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f6c0-146">Poznámky</span><span class="sxs-lookup"><span data-stu-id="9f6c0-146">Remarks</span></span>  
 <span data-ttu-id="9f6c0-147">Vystavený token scénář má tři fáze.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-147">The issued token scenario has three stages.</span></span> <span data-ttu-id="9f6c0-148">V první fázi se klient pokouší o přístup ke službě označuje *služby tokenů zabezpečení*.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-148">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="9f6c0-149">Službu tokenů zabezpečení pak ověřuje klienta a následně vydá klienta token, obvykle token zabezpečení kontrolní výrazy Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="9f6c0-149">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="9f6c0-150">Klient pak vrátí ke službě pomocí tokenu.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-150">The client then returns to the service with the token.</span></span> <span data-ttu-id="9f6c0-151">Služba prověří token pro data, která umožňuje službě ověření tokenu a proto klienta.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-151">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="9f6c0-152">K ověření tokenu, certifikátu používá zabezpečené tokenu služby musí být známo ke službě.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-152">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="9f6c0-153">Tento element má úložiště pro všechny zabezpečené služby tokenů certifikáty.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-153">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="9f6c0-154">Chcete-li přidat certifikáty, použijte [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="9f6c0-154">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="9f6c0-155">Vložit [ \<Přidat >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) pro každý certifikát, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-155">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthorization>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="9f6c0-156">Ve výchozím nastavení musí získat certifikáty ze služby tokenu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-156">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="9f6c0-157">Tyto "známé" certifikáty, ujistěte se, že který pouze oprávněné klientů můžete přístup ke službě.</span><span class="sxs-lookup"><span data-stu-id="9f6c0-157">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="9f6c0-158">Další informace o použití tohoto elementu konfigurace najdete v tématu [postupy: Konfigurace pověření ve službě Federation](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="9f6c0-158">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f6c0-159">Viz také</span><span class="sxs-lookup"><span data-stu-id="9f6c0-159">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
 [<span data-ttu-id="9f6c0-160">Zabezpečení služeb a klientů</span><span class="sxs-lookup"><span data-stu-id="9f6c0-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9f6c0-161">Postupy: Konfigurace pověření ve službě Federation</span><span class="sxs-lookup"><span data-stu-id="9f6c0-161">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)