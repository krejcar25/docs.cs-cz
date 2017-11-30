---
title: '&lt;serviceTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 06e871ee31880a219d9105ff4ce667618bfb78f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="22c40-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="22c40-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="22c40-103">Zaregistruje překladač tokenu služby, který je používán obslužné rutiny v kolekci obslužná rutina tokenu.</span><span class="sxs-lookup"><span data-stu-id="22c40-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="22c40-104">Překladač tokenu služby se používá k překladu šifrování tokenu na příchozí tokeny a zprávy.</span><span class="sxs-lookup"><span data-stu-id="22c40-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="22c40-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="22c40-105">\<system.identityModel></span></span>  
<span data-ttu-id="22c40-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="22c40-106">\<identityConfiguration></span></span>  
<span data-ttu-id="22c40-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="22c40-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="22c40-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="22c40-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="22c40-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="22c40-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c40-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="22c40-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22c40-111">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="22c40-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22c40-112">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="22c40-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22c40-113">Atributy</span><span class="sxs-lookup"><span data-stu-id="22c40-113">Attributes</span></span>  
  
|<span data-ttu-id="22c40-114">Atribut</span><span class="sxs-lookup"><span data-stu-id="22c40-114">Attribute</span></span>|<span data-ttu-id="22c40-115">Popis</span><span class="sxs-lookup"><span data-stu-id="22c40-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22c40-116">– typ</span><span class="sxs-lookup"><span data-stu-id="22c40-116">type</span></span>|<span data-ttu-id="22c40-117">Určuje typ tokenu překladače služby.</span><span class="sxs-lookup"><span data-stu-id="22c40-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="22c40-118">Buď <xref:System.IdentityModel.Selectors.SecurityTokenResolver> typu nebo typu, která je odvozena z <xref:System.IdentityModel.Selectors.SecurityTokenResolver> třídy.</span><span class="sxs-lookup"><span data-stu-id="22c40-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="22c40-119">Další informace o tom, jak zadat `type` atributů najdete v tématu [odkazy na vlastní typ].</span><span class="sxs-lookup"><span data-stu-id="22c40-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="22c40-120">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="22c40-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22c40-121">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="22c40-121">Child Elements</span></span>  
 <span data-ttu-id="22c40-122">Žádné</span><span class="sxs-lookup"><span data-stu-id="22c40-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22c40-123">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="22c40-123">Parent Elements</span></span>  
  
|<span data-ttu-id="22c40-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="22c40-124">Element</span></span>|<span data-ttu-id="22c40-125">Popis</span><span class="sxs-lookup"><span data-stu-id="22c40-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22c40-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="22c40-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="22c40-127">Poskytuje konfigurace pro kolekci zabezpečení tokenu obslužné rutiny.</span><span class="sxs-lookup"><span data-stu-id="22c40-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22c40-128">Poznámky</span><span class="sxs-lookup"><span data-stu-id="22c40-128">Remarks</span></span>  
 <span data-ttu-id="22c40-129">Překladač tokenu služby lze použít k vyřešení šifrování tokenu na příchozí tokeny a zprávy.</span><span class="sxs-lookup"><span data-stu-id="22c40-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="22c40-130">Umožňuje načíst klíč, který se má použít k dešifrování tokenů, příchozí.</span><span class="sxs-lookup"><span data-stu-id="22c40-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="22c40-131">Je nutné zadat `type` atribut.</span><span class="sxs-lookup"><span data-stu-id="22c40-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="22c40-132">Zadaný typ může být buď <xref:System.IdentityModel.Selectors.SecurityTokenResolver> nebo vlastního typu, který je odvozen od <xref:System.IdentityModel.Selectors.SecurityTokenResolver> třídy.</span><span class="sxs-lookup"><span data-stu-id="22c40-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="22c40-133">Některé tokenu obslužné rutiny umožňují určit nastavení tokenu překladače služby v konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="22c40-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="22c40-134">Nastavení na jednotlivých tokenu obslužné rutiny potlačit platformám zadaným v kolekci obslužná rutina tokenu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="22c40-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22c40-135">Určení `<serviceTokenResolver>` prvku jako podřízeného prvku [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elementu se už nepoužívá, ale je stále podporováno pro zpětnou kompatibilitu.</span><span class="sxs-lookup"><span data-stu-id="22c40-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="22c40-136">Nastavení na `<securityTokenHandlerConfiguration>` element přepíšou na `<identityConfiguration>` elementu.</span><span class="sxs-lookup"><span data-stu-id="22c40-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22c40-137">Příklad</span><span class="sxs-lookup"><span data-stu-id="22c40-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```