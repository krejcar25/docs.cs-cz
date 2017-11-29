---
title: "ICorRuntimeHost – rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost
helpviewer_keywords: ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 844648cd2cfafc561e27bea870703ee3a55fb404
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="46b5a-102">ICorRuntimeHost – rozhraní</span><span class="sxs-lookup"><span data-stu-id="46b5a-102">ICorRuntimeHost Interface</span></span>
<span data-ttu-id="46b5a-103">Poskytuje metody, které umožní hostitele spuštění a zastavení common language runtime (CLR) explicitně, vytvořte a nakonfigurujte aplikační domény, pro přístup k výchozí doméně a chcete získat výčet všech domén, které jsou spuštěné v procesu.</span><span class="sxs-lookup"><span data-stu-id="46b5a-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="46b5a-104">V rozhraní .NET Framework verze 2.0, toto rozhraní oprávněni [iclrruntimehost –](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).</span><span class="sxs-lookup"><span data-stu-id="46b5a-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="46b5a-105">Metody</span><span class="sxs-lookup"><span data-stu-id="46b5a-105">Methods</span></span>  
  
|<span data-ttu-id="46b5a-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-106">Method</span></span>|<span data-ttu-id="46b5a-107">Popis</span><span class="sxs-lookup"><span data-stu-id="46b5a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="46b5a-108">Closeenum – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-108">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|<span data-ttu-id="46b5a-109">Obnoví enumerátor domény zpět na začátek seznamu domény.</span><span class="sxs-lookup"><span data-stu-id="46b5a-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="46b5a-110">CreateDomain – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-110">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|<span data-ttu-id="46b5a-111">Vytvoří doménu aplikace.</span><span class="sxs-lookup"><span data-stu-id="46b5a-111">Creates an application domain.</span></span> <span data-ttu-id="46b5a-112">Volající obdrží ukazatele rozhraní typu <xref:System._AppDomain> na instanci typu <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="46b5a-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="46b5a-113">Createdomainex – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-113">CreateDomainEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|<span data-ttu-id="46b5a-114">Vytvoří doménu aplikace.</span><span class="sxs-lookup"><span data-stu-id="46b5a-114">Creates an application domain.</span></span> <span data-ttu-id="46b5a-115">Tato metoda umožňuje volajícímu předat instanci iappdomainsetup – Chcete-li konfigurovat další funkce vrácený <xref:System._AppDomain> instance.</span><span class="sxs-lookup"><span data-stu-id="46b5a-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="46b5a-116">Createdomainsetup – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-116">CreateDomainSetup Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="46b5a-117">Získá ukazatele rozhraní typu `IAppDomainSetup` k <xref:System.AppDomainSetup> instance.</span><span class="sxs-lookup"><span data-stu-id="46b5a-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="46b5a-118">`IAppDomainSetup`poskytuje metody pro konfiguraci aspektů domény aplikace předtím, než se vytvoří.</span><span class="sxs-lookup"><span data-stu-id="46b5a-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="46b5a-119">Createevidence – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-119">CreateEvidence Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|<span data-ttu-id="46b5a-120">Získá ukazatele rozhraní typu <xref:System.Security.Principal.IIdentity>, což umožňuje na hostiteli a poté vytvořit důkaz zabezpečení mají být předány [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) nebo [createdomainex –](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).</span><span class="sxs-lookup"><span data-stu-id="46b5a-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="46b5a-121">Createlogicalthreadstate – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-121">CreateLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="46b5a-122">Nepoužívejte.</span><span class="sxs-lookup"><span data-stu-id="46b5a-122">Do not use.</span></span>|  
|[<span data-ttu-id="46b5a-123">CurrentDomain – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-123">CurrentDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|<span data-ttu-id="46b5a-124">Získá ukazatele rozhraní typu <xref:System._AppDomain> představující domény načtené na aktuální vlákno.</span><span class="sxs-lookup"><span data-stu-id="46b5a-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="46b5a-125">Deletelogicalthreadstate – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-125">DeleteLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="46b5a-126">Nepoužívejte.</span><span class="sxs-lookup"><span data-stu-id="46b5a-126">Do not use.</span></span>|  
|[<span data-ttu-id="46b5a-127">Enumdomains – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-127">EnumDomains Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|<span data-ttu-id="46b5a-128">Získá enumerátor pro domény v aktuálním procesu.</span><span class="sxs-lookup"><span data-stu-id="46b5a-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="46b5a-129">Getconfiguration – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-129">GetConfiguration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="46b5a-130">Získá objekt, který umožňuje na hostiteli a poté zadejte konfiguraci zpětného volání modulu CLR.</span><span class="sxs-lookup"><span data-stu-id="46b5a-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="46b5a-131">Getdefaultdomain – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-131">GetDefaultDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="46b5a-132">Získá ukazatele rozhraní typu <xref:System._AppDomain> představující výchozí doménu pro aktuální proces.</span><span class="sxs-lookup"><span data-stu-id="46b5a-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="46b5a-133">Locksheldbylogicalthread – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-133">LocksHeldByLogicalThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="46b5a-134">Nepoužívejte.</span><span class="sxs-lookup"><span data-stu-id="46b5a-134">Do not use.</span></span>|  
|[<span data-ttu-id="46b5a-135">MapFile – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-135">MapFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|<span data-ttu-id="46b5a-136">Mapuje zadaný soubor do paměti.</span><span class="sxs-lookup"><span data-stu-id="46b5a-136">Maps the specified file into memory.</span></span> <span data-ttu-id="46b5a-137">Tato metoda je zastaralá.</span><span class="sxs-lookup"><span data-stu-id="46b5a-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="46b5a-138">Nextdomain – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-138">NextDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|<span data-ttu-id="46b5a-139">Získá ukazatele rozhraní do další domény ve výčtu.</span><span class="sxs-lookup"><span data-stu-id="46b5a-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="46b5a-140">Start – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-140">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|<span data-ttu-id="46b5a-141">Spuštění modulu CLR.</span><span class="sxs-lookup"><span data-stu-id="46b5a-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="46b5a-142">Stop – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-142">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|<span data-ttu-id="46b5a-143">Zastaví spuštění kódu v modulu runtime pro aktuální proces.</span><span class="sxs-lookup"><span data-stu-id="46b5a-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="46b5a-144">Switchinlogicalthreadstate – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-144">SwitchInLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="46b5a-145">Nepoužívejte.</span><span class="sxs-lookup"><span data-stu-id="46b5a-145">Do not use.</span></span>|  
|[<span data-ttu-id="46b5a-146">Switchoutlogicalthreadstate – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-146">SwitchOutLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="46b5a-147">Nepoužívejte.</span><span class="sxs-lookup"><span data-stu-id="46b5a-147">Do not use.</span></span>|  
|[<span data-ttu-id="46b5a-148">Unloaddomain – metoda</span><span class="sxs-lookup"><span data-stu-id="46b5a-148">UnloadDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="46b5a-149">Uvolní doménu zadané aplikace z aktuální proces.</span><span class="sxs-lookup"><span data-stu-id="46b5a-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46b5a-150">Požadavky</span><span class="sxs-lookup"><span data-stu-id="46b5a-150">Requirements</span></span>  
 <span data-ttu-id="46b5a-151">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46b5a-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46b5a-152">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="46b5a-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46b5a-153">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46b5a-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46b5a-154">**Verze rozhraní .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="46b5a-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b5a-155">Viz také</span><span class="sxs-lookup"><span data-stu-id="46b5a-155">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="46b5a-156">Hostování</span><span class="sxs-lookup"><span data-stu-id="46b5a-156">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="46b5a-157">Iclrruntimehost – rozhraní</span><span class="sxs-lookup"><span data-stu-id="46b5a-157">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="46b5a-158">Modulu runtime</span><span class="sxs-lookup"><span data-stu-id="46b5a-158">Runtime Hosts</span></span>](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [<span data-ttu-id="46b5a-159">Rozhraní hostování</span><span class="sxs-lookup"><span data-stu-id="46b5a-159">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="46b5a-160">Corruntimehost – třída typu Coclass</span><span class="sxs-lookup"><span data-stu-id="46b5a-160">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)