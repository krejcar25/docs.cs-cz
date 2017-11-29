---
title: "Jaký & č. 39; s ve Windows Identity Foundation 4.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b381f04-593b-471f-bd33-0362be1aade5
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 19116aba3049dce6612ca1a7170030f7ced6705e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="what39s-new-in-windows-identity-foundation-45"></a><span data-ttu-id="c4b13-102">Jaký & č. 39; s ve Windows Identity Foundation 4.5</span><span class="sxs-lookup"><span data-stu-id="c4b13-102">What&#39;s New in Windows Identity Foundation 4.5</span></span>
<span data-ttu-id="c4b13-103">První verze technologie Windows Identity Foundation (WIF) byla uvedena na trh jako samostatný produkt ke stažení a je známa pod označením WIF 3.5, protože byla uvedena ve stejném období jako technologie .NET 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="c4b13-103">The first version of Windows Identity Foundation (WIF) shipped as a standalone download and is known as WIF 3.5 because it was introduced in the .NET 3.5 SP1 timeframe.</span></span> <span data-ttu-id="c4b13-104">Počínaje verzí .NET 4.5 je technologie WIF součástí rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4b13-104">Starting with .NET 4.5, WIF is part of the .NET framework.</span></span> <span data-ttu-id="c4b13-105">S přímo k dispozici v rámci třídy WIF umožňuje mnohem hlubší integrace založené na deklaracích identity v rozhraní .NET, což usnadňuje používat deklarace identity.</span><span class="sxs-lookup"><span data-stu-id="c4b13-105">Having the WIF classes directly available in the framework allows for a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="c4b13-106">Aplikace napsané pro WIF 3.5 bude nutné upravit, aby bylo možné využívat výhod nového modelu; informace najdete v tématu [pokyny pro migraci aplikaci vytvořené pomocí WIF 3.5 na verzi WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).</span><span class="sxs-lookup"><span data-stu-id="c4b13-106">Applications written for WIF 3.5 will need to be modified in order to take advantage of the new model; for information, see [Guidelines for Migrating an Application Built Using WIF 3.5 to WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).</span></span>  
  
 <span data-ttu-id="c4b13-107">Následuje přehled některých hlavních změn.</span><span class="sxs-lookup"><span data-stu-id="c4b13-107">Below you can find some highlights of the main changes.</span></span>  
  
## <a name="wif-is-now-part-of-the-net-framework"></a><span data-ttu-id="c4b13-108">Technologie WIF je nyní součástí rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c4b13-108">WIF Is Now Part of the .NET Framework</span></span>  
 <span data-ttu-id="c4b13-109">WIF třídy jsou nyní rozloženy několik sestavení, hlavní těm, které jsou právě `mscorlib`, `System.IdentityModel`, `System.IdentityModel.Services`, a `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="c4b13-109">WIF classes are now spread across several assemblies, the main ones being `mscorlib`, `System.IdentityModel`, `System.IdentityModel.Services`, and `System.ServiceModel`.</span></span> <span data-ttu-id="c4b13-110">Podobně WIF třídy jsou rozloženy několik oborů názvů: <xref:System.Security.Claims?displayProperty=nameWithType>, několik [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) obory názvů, a <xref:System.ServiceModel.Security?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c4b13-110">Likewise, the WIF classes are spread across several namespaces: <xref:System.Security.Claims?displayProperty=nameWithType>, several [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) namespaces, and <xref:System.ServiceModel.Security?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c4b13-111"><xref:System.Security.Claims?displayProperty=nameWithType> Obor názvů obsahuje nové <xref:System.Security.Claims.ClaimsPrincipal> a <xref:System.Security.Claims.ClaimsIdentity> třídy (viz níže).</span><span class="sxs-lookup"><span data-stu-id="c4b13-111">The <xref:System.Security.Claims?displayProperty=nameWithType> namespace contains the new <xref:System.Security.Claims.ClaimsPrincipal> and <xref:System.Security.Claims.ClaimsIdentity> classes (see below).</span></span> <span data-ttu-id="c4b13-112">Všechny objekty zabezpečení v rozhraní .NET jsou odvozeny od <xref:System.Security.Claims.ClaimsPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="c4b13-112">All principals in .NET now derive from <xref:System.Security.Claims.ClaimsPrincipal>.</span></span> <span data-ttu-id="c4b13-113">Podrobné informace o WIF obory názvů a typy tříd, které obsahují, najdete v části [referenční dokumentace rozhraní API WIF](../../../docs/framework/security/wif-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c4b13-113">For more detailed information about the WIF namespaces and the kinds of classes that they contain, see [WIF API Reference](../../../docs/framework/security/wif-api-reference.md).</span></span> <span data-ttu-id="c4b13-114">Informace o tom, jak obory názvů mapování mezi WIF 3.5 a WIF 4.5 najdete v tématu [Namespace mapování mezi WIF 3.5 a WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).</span><span class="sxs-lookup"><span data-stu-id="c4b13-114">For information about how namespaces map between WIF 3.5 and WIF 4.5, see [Namespace Mapping between WIF 3.5 and WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).</span></span>  
  
## <a name="new-claims-model-and-principal-object"></a><span data-ttu-id="c4b13-115">Nový model a objekt zabezpečení založený na deklaracích</span><span class="sxs-lookup"><span data-stu-id="c4b13-115">New Claims Model and Principal Object</span></span>  
 <span data-ttu-id="c4b13-116">Deklarace jsou v samotném jádru rozhraní .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="c4b13-116">Claims are at the very core of the .NET Framework 4.5.</span></span> <span data-ttu-id="c4b13-117">Základní deklarace třídy (<xref:System.Security.Claims.Claim>, <xref:System.Security.Claims.ClaimsIdentity>, <xref:System.Security.Claims.ClaimsPrincipal>, <xref:System.Security.Claims.ClaimTypes>, a <xref:System.Security.Claims.ClaimValueTypes>) všechny live přímo v `mscorlib` v <xref:System.Security.Claims?displayProperty=nameWithType> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="c4b13-117">The base claim classes (<xref:System.Security.Claims.Claim>, <xref:System.Security.Claims.ClaimsIdentity>, <xref:System.Security.Claims.ClaimsPrincipal>, <xref:System.Security.Claims.ClaimTypes>, and <xref:System.Security.Claims.ClaimValueTypes>) all live directly in `mscorlib` in the <xref:System.Security.Claims?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="c4b13-118">Již není nutné k použití rozhraní, aby bylo možné zařadit deklarace identity do systému identity rozhraní .NET: <xref:System.Security.Principal.WindowsPrincipal>, <xref:System.Security.Principal.GenericPrincipal>, a <xref:System.Web.Security.RolePrincipal> nyní dědí <xref:System.Security.Claims.ClaimsPrincipal>; a <xref:System.Security.Principal.WindowsIdentity>, <xref:System.Security.Principal.GenericIdentity>, a <xref:System.Web.Security.FormsIdentity> nyní dědí. z <xref:System.Security.Claims.ClaimsIdentity>.</span><span class="sxs-lookup"><span data-stu-id="c4b13-118">It is no longer necessary to use interfaces in order to plug claims into the .NET identity system: <xref:System.Security.Principal.WindowsPrincipal>, <xref:System.Security.Principal.GenericPrincipal>, and <xref:System.Web.Security.RolePrincipal> now inherit from <xref:System.Security.Claims.ClaimsPrincipal>; and <xref:System.Security.Principal.WindowsIdentity>, <xref:System.Security.Principal.GenericIdentity>, and <xref:System.Web.Security.FormsIdentity> now inherit from <xref:System.Security.Claims.ClaimsIdentity>.</span></span> <span data-ttu-id="c4b13-119">Stručně řečeno, všechny třídy objektů zabezpečení nyní budou poskytovat deklarace.</span><span class="sxs-lookup"><span data-stu-id="c4b13-119">In short, every principal class will now serve claims.</span></span> <span data-ttu-id="c4b13-120">WIF 3.5 integrace třídy a rozhraní (`WindowsClaimsIdentity`, `WindowsClaimsPrincipal`, `IClaimsPrincipal`, `IClaimsIdentity`) proto byly odebrány.</span><span class="sxs-lookup"><span data-stu-id="c4b13-120">The WIF 3.5 integration classes and interfaces (`WindowsClaimsIdentity`, `WindowsClaimsPrincipal`, `IClaimsPrincipal`, `IClaimsIdentity`) have thus been removed.</span></span> <span data-ttu-id="c4b13-121">Kromě toho <xref:System.Security.Claims.ClaimsIdentity> třída teď zpřístupňuje metody, které usnadňují dotaz identitu deklarací kolekce.</span><span class="sxs-lookup"><span data-stu-id="c4b13-121">In addition, the <xref:System.Security.Claims.ClaimsIdentity> class now exposes methods which make it easier to query the identity’s claims collection.</span></span>  
  
## <a name="changes-to-the-wif-45-visual-studio-experience"></a><span data-ttu-id="c4b13-122">Změny v používání technologie WIF 4.5 v prostředí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4b13-122">Changes to the WIF 4.5 Visual Studio Experience</span></span>  
  
-   <span data-ttu-id="c4b13-123">**Přidat odkaz na službu tokenů zabezpečení...**</span><span class="sxs-lookup"><span data-stu-id="c4b13-123">The **Add STS Reference …**</span></span> <span data-ttu-id="c4b13-124">Funkci Visual Studio (nástroj cmdline FedUtil) již existuje; Místo toho můžete použít nové rozšíření sady Visual Studio **identita a přístup pro sadu Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="c4b13-124">Visual Studio functionality (cmdline utility FedUtil) no longer exists; instead you can use the new Visual Studio extension **Identity and Access Tool for Visual Studio 2012**.</span></span> <span data-ttu-id="c4b13-125">To umožňuje federaci s existující službou tokenů zabezpečení (STS). Svá řešení můžete také testovat s použitím místní služby tokenů zabezpečení LocalSTS.</span><span class="sxs-lookup"><span data-stu-id="c4b13-125">This allows you to federate with an existing STS or use LocalSTS to test your solutions.</span></span> <span data-ttu-id="c4b13-126">Po instalaci rozšíření můžete kliknout pravým tlačítkem na projekt a vyhledejte **identit a přístupu** v místní nabídce.</span><span class="sxs-lookup"><span data-stu-id="c4b13-126">After installing the extension you can right-click on your project and look for **Identity and Access** in the context menu.</span></span>  
  
-   <span data-ttu-id="c4b13-127">Šablony technologie ASP.NET a služby STS již nejsou k dispozici, protože deklarace je možné používat přímo v existujících šablonách projektů pro technologii ASP.NET, weby a technologii WCF.</span><span class="sxs-lookup"><span data-stu-id="c4b13-127">The ASP.NET and STS templates are no longer provided as claims can be used directly in existing project templates for ASP.Net, web sites, and WCF.</span></span>  
  
-   <span data-ttu-id="c4b13-128">Ovládací prvky v `Microsoft.IdentityModel.Web.Controls` obor názvů (`SignInControl`, `FederatedPassiveSignInControl`, a `FederatedPassiveSignInStatus`) nejsou přenášejí do WIF 4.5.</span><span class="sxs-lookup"><span data-stu-id="c4b13-128">The controls in the `Microsoft.IdentityModel.Web.Controls` namespace (`SignInControl`, `FederatedPassiveSignInControl`, and `FederatedPassiveSignInStatus`) are not carried over into WIF 4.5.</span></span>  
  
## <a name="changes-to-the-wif-45-api"></a><span data-ttu-id="c4b13-129">Změny v rozhraní API technologie WIF 4.5</span><span class="sxs-lookup"><span data-stu-id="c4b13-129">Changes to the WIF 4.5 API</span></span>  
  
-   <span data-ttu-id="c4b13-130">Obecně platí, související třídy deklarace identity jsou v <xref:System.Security.Claims?displayProperty=nameWithType> obor názvů; WCF související třídy – – služba měnící, kanály, objekty factory kanálu a hostitelé služeb, které se používají pro scénáře WS-Trust – <xref:System.ServiceModel.Security?displayProperty=nameWithType>; a všech ostatních WIF třídy jsou rozloženy různé [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) obory názvů – patří, například tříd, které představují WS-* a artefaktů SAML token obslužné rutiny a související třídy a třídy používané ve scénářích WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="c4b13-130">In general, claims related classes are in the <xref:System.Security.Claims?displayProperty=nameWithType> namespace; WCF related classes –- service contracts, channels, channel factories, and service hosts that are used for WS-Trust scenarios -- are in <xref:System.ServiceModel.Security?displayProperty=nameWithType>; and all other WIF classes are spread across various [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) namespaces – these include, for example, classes that represent WS-* and SAML artifacts, token handlers and related classes, and classes used in WS-Federation scenarios.</span></span> <span data-ttu-id="c4b13-131">Další informace najdete v tématu [Namespace mapování mezi WIF 3.5 a WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md) a [referenční dokumentace rozhraní API WIF](../../../docs/framework/security/wif-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c4b13-131">For more information, see [Namespace Mapping between WIF 3.5 and WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md) and [WIF API Reference](../../../docs/framework/security/wif-api-reference.md).</span></span>  
  
-   <span data-ttu-id="c4b13-132">Bylo povoleno používání klíče počítače v souborech cookie relací při používání webových farem.</span><span class="sxs-lookup"><span data-stu-id="c4b13-132">Machine key has been enabled for use in session cookies for web farm scenarios.</span></span> <span data-ttu-id="c4b13-133">Další informace najdete v tématu [WIF a webových farem](../../../docs/framework/security/wif-and-web-farms.md).</span><span class="sxs-lookup"><span data-stu-id="c4b13-133">For more information, see [WIF and Web Farms](../../../docs/framework/security/wif-and-web-farms.md).</span></span>  
  
-   <span data-ttu-id="c4b13-134">Teď deklarativně nakonfigurovat WIF pod [ \<system.identityModel >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) a [ \<system.identityModel.services >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) elementy.</span><span class="sxs-lookup"><span data-stu-id="c4b13-134">You now declaratively configure WIF under the [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) and [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) elements.</span></span> <span data-ttu-id="c4b13-135">Další informace o konfiguraci WIF najdete v tématu [referenci na konfigurační WIF](../../../docs/framework/security/wif-configuration-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c4b13-135">For more information about WIF configuration, see [WIF Configuration Reference](../../../docs/framework/security/wif-configuration-reference.md).</span></span>  
  
## <a name="other-notable-net-changes-or-features-that-are-caused-by-the-integration-of-wif-into-net"></a><span data-ttu-id="c4b13-136">Další významné změny technologie .NET nebo funkce způsobené začleněním technologie WIF do technologie .NET</span><span class="sxs-lookup"><span data-stu-id="c4b13-136">Other notable .NET changes or features that are caused by the integration of WIF into .NET</span></span>  
  
-   <span data-ttu-id="c4b13-137">Možnost autorizace na základě deklarované identity (CBAC) je nyní součástí rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4b13-137">The potential for performing claims-based authorization (CBAC) is now integral to the .NET framework.</span></span> <span data-ttu-id="c4b13-138">Můžete nakonfigurovat <xref:System.Security.Claims.ClaimsAuthorizationManager> objekt a potom pomocí <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> a <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> třídy k provádění kontrol imperativní a deklarativní přístup do vašeho kódu.</span><span class="sxs-lookup"><span data-stu-id="c4b13-138">You can configure a <xref:System.Security.Claims.ClaimsAuthorizationManager> object and then use the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> and <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classes to perform imperative and declarative access checks in your code.</span></span> <span data-ttu-id="c4b13-139">Autorizace CBAC poskytuje větší flexibilitu a přesnost než tradiční kontroly přístupu na základě rolí (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c4b13-139">CBAC provides more flexibility and greater granularity than traditional role-based access checks (RBAC).</span></span> <span data-ttu-id="c4b13-140">Umožňuje také větší oddělení zásad autorizace od obchodní logiky, protože obchodní logiky můžete základní kontrola přístupu na konkrétní deklarace identity nebo sadu deklarací identity a zásady autorizace pro tyto deklarace identity, lze nastavit deklarativně pod [ \<claimsAuthorizationManager >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element.</span><span class="sxs-lookup"><span data-stu-id="c4b13-140">It also allows greater separation of authorization policy from business logic because the business logic can base the access check on a specific claim or set of claims and the authorization policy for those claims can be configured declaratively under the [\<claimsAuthorizationManager>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element.</span></span>  
  
## <a name="wcf-changes-as-a-result-of-wif-integration"></a><span data-ttu-id="c4b13-141">Změny v technologii WCF v důsledku integrace technologie WIF:</span><span class="sxs-lookup"><span data-stu-id="c4b13-141">WCF changes as a result of WIF integration:</span></span>  
  
-   <span data-ttu-id="c4b13-142">Model deklarovaných identit technologie WCF je nahrazen technologií WIF.</span><span class="sxs-lookup"><span data-stu-id="c4b13-142">The WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="c4b13-143">To znamená, že třídy v <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, a <xref:System.IdentityModel.Selectors?displayProperty=nameWithType> obory názvů by se měly zahodit považuje pomocí třídy WIF.</span><span class="sxs-lookup"><span data-stu-id="c4b13-143">This means that classes in the <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType> namespaces should be dropped in favor of using WIF classes.</span></span>  
  
-   <span data-ttu-id="c4b13-144">WIF je teď povolené ve službě WCF zadáním `useIdentityConfiguration` atributu u `<system.serviceModel>` / `<behaviors>` / `<serviceBehaviors>` / `<serviceCredentials>` element jako následující kód XML:</span><span class="sxs-lookup"><span data-stu-id="c4b13-144">WIF is now enabled on a WCF service by specifying the `useIdentityConfiguration` attribute on the `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>` element as in the following XML:</span></span>  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
     <span data-ttu-id="c4b13-145">Při použití **identita a přístup pro sadu Visual Studio 2012** (najdete v části **změny prostředí Visual Studio** výše), nástroj přidá `<serviceCredentials>` element s `useIdentityConfiguration` atribut nastaven na konfigurační soubor pro vás.</span><span class="sxs-lookup"><span data-stu-id="c4b13-145">When you use the **Identity and Access Tool for Visual Studio 2012** (see **Changes to the Visual Studio Experience** above), the tool adds a `<serviceCredentials>` element with the `useIdentityConfiguration` attribute set to the configuration file for you.</span></span> <span data-ttu-id="c4b13-146">Také přidá odpovídající [ \<system.identityModel >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) element, který obsahuje konfigurační nastavení WIF a přidá vazbu a další nastavení, které jsou nezbytné pro externí ověřování pro vaši vybranou služby tokenů zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="c4b13-146">It also adds a corresponding [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) element that contains the WIF configuration settings and adds a binding and other settings necessary to outsource authentication to your chosen STS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b13-147">Viz také</span><span class="sxs-lookup"><span data-stu-id="c4b13-147">See Also</span></span>  
 [<span data-ttu-id="c4b13-148">Pokyny k migraci aplikace vyvíjené v WIF 3.5 na verzi WIF 4.5</span><span class="sxs-lookup"><span data-stu-id="c4b13-148">Guidelines for Migrating an Application Built Using WIF 3.5 to WIF 4.5</span></span>](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)  
 [<span data-ttu-id="c4b13-149">Namespace mapování mezi WIF 3.5 a WIF 4.5</span><span class="sxs-lookup"><span data-stu-id="c4b13-149">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)  
 [<span data-ttu-id="c4b13-150">Referenční dokumentace rozhraní API WIF</span><span class="sxs-lookup"><span data-stu-id="c4b13-150">WIF API Reference</span></span>](../../../docs/framework/security/wif-api-reference.md)  
 [<span data-ttu-id="c4b13-151">Referenci na konfigurační WIF</span><span class="sxs-lookup"><span data-stu-id="c4b13-151">WIF Configuration Reference</span></span>](../../../docs/framework/security/wif-configuration-reference.md)