---
title: "Kompatibilita a migrace zásad zabezpečení přístupu kódu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policy migration, compatibility
- CLR poliicy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29e81f5e83bc3cbf9467c7940ba6acfd0a8c99b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="ffacf-102">Kompatibilita a migrace zásad zabezpečení přístupu kódu</span><span class="sxs-lookup"><span data-stu-id="ffacf-102">Code Access Security Policy Compatibility and Migration</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="ffacf-103">Část zásad zabezpečení přístupu kódu (CAS) byly provedeny v zastaralé [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffacf-103">The policy portion of code access security (CAS) has been made obsolete in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="ffacf-104">V důsledku toho může dojít upozornění kompilace a výjimky za běhu při volání zastaralé typy a členy [explicitně](#explicit_use) nebo [implicitně](#implicit_use) (prostřednictvím jiných typů a členů).</span><span class="sxs-lookup"><span data-stu-id="ffacf-104">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>  
  
 <span data-ttu-id="ffacf-105">Buď se můžete vyhnout chyby a varování:</span><span class="sxs-lookup"><span data-stu-id="ffacf-105">You can avoid the warnings and errors by either:</span></span>  
  
-   <span data-ttu-id="ffacf-106">[Migrace](#migration) k [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] náhrady za zastaralé volání.</span><span class="sxs-lookup"><span data-stu-id="ffacf-106">[Migrating](#migration) to the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] replacements for the obsolete calls.</span></span>  
  
     <span data-ttu-id="ffacf-107">\-nebo –</span><span class="sxs-lookup"><span data-stu-id="ffacf-107">\- or -</span></span>  
  
-   <span data-ttu-id="ffacf-108">Pomocí [< NetFx40_LegacySecurityPolicy – > Konfigurace element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) se vyjádřit výslovný do starší verze chování zásad CAS.</span><span class="sxs-lookup"><span data-stu-id="ffacf-108">Using the [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>  
  
 <span data-ttu-id="ffacf-109">Toto téma obsahuje následující oddíly:</span><span class="sxs-lookup"><span data-stu-id="ffacf-109">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="ffacf-110">Explicitní použití</span><span class="sxs-lookup"><span data-stu-id="ffacf-110">Explicit Use</span></span>](#explicit_use)  
  
-   [<span data-ttu-id="ffacf-111">Implicitní použití</span><span class="sxs-lookup"><span data-stu-id="ffacf-111">Implicit Use</span></span>](#implicit_use)  
  
-   [<span data-ttu-id="ffacf-112">Chyby a upozornění</span><span class="sxs-lookup"><span data-stu-id="ffacf-112">Errors and Warnings</span></span>](#errors_and_warnings)  
  
-   [<span data-ttu-id="ffacf-113">Migrace: Nahrazení pro zastaralé volání</span><span class="sxs-lookup"><span data-stu-id="ffacf-113">Migration: Replacement for Obsolete Calls</span></span>](#migration)  
  
-   [<span data-ttu-id="ffacf-114">Kompatibilita: Pomocí možnosti starší zásadu CAS</span><span class="sxs-lookup"><span data-stu-id="ffacf-114">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)  
  
<a name="explicit_use"></a>   
## <a name="explicit-use"></a><span data-ttu-id="ffacf-115">Explicitní použití</span><span class="sxs-lookup"><span data-stu-id="ffacf-115">Explicit Use</span></span>  
 <span data-ttu-id="ffacf-116">Členové, které přímo upravit zásady zabezpečení nebo vyžadují zásadu CAS do izolovaného prostoru jsou zastaralé a vygeneruje chyby ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="ffacf-116">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>  
  
 <span data-ttu-id="ffacf-117">Tyto příklady:</span><span class="sxs-lookup"><span data-stu-id="ffacf-117">Examples of these are:</span></span>  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>  
  
<a name="implicit_use"></a>   
## <a name="implicit-use"></a><span data-ttu-id="ffacf-118">Implicitní použití</span><span class="sxs-lookup"><span data-stu-id="ffacf-118">Implicit Use</span></span>  
 <span data-ttu-id="ffacf-119">Několik přetížení načítání sestavení produkuje chyby kvůli implicitně používají certifikační Autority zásad.</span><span class="sxs-lookup"><span data-stu-id="ffacf-119">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="ffacf-120">Tato přetížení používají <xref:System.Security.Policy.Evidence> parametr, který se používá k vyřešení zásad CAS a poskytnout oprávnění udělit sada pro sestavení.</span><span class="sxs-lookup"><span data-stu-id="ffacf-120">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>  
  
 <span data-ttu-id="ffacf-121">Zde jsou některé příklady.</span><span class="sxs-lookup"><span data-stu-id="ffacf-121">Here are some examples.</span></span> <span data-ttu-id="ffacf-122">Zastaralá přetížení jsou ty, které provést <xref:System.Security.Policy.Evidence> jako parametr:</span><span class="sxs-lookup"><span data-stu-id="ffacf-122">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
<a name="errors_and_warnings"></a>   
## <a name="errors-and-warnings"></a><span data-ttu-id="ffacf-123">Chyby a upozornění</span><span class="sxs-lookup"><span data-stu-id="ffacf-123">Errors and Warnings</span></span>  
 <span data-ttu-id="ffacf-124">Zastaralé typy a členy vytvořit následující chybové zprávy, když se používají.</span><span class="sxs-lookup"><span data-stu-id="ffacf-124">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="ffacf-125">Všimněte si, že <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> vlastní typ není zastaralá.</span><span class="sxs-lookup"><span data-stu-id="ffacf-125">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>  
  
 <span data-ttu-id="ffacf-126">Kompilace upozornění:</span><span class="sxs-lookup"><span data-stu-id="ffacf-126">Compile-time warning:</span></span>  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`  
  
 <span data-ttu-id="ffacf-127">Výjimka:</span><span class="sxs-lookup"><span data-stu-id="ffacf-127">Run-time exception:</span></span>  
  
 <span data-ttu-id="ffacf-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="ffacf-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>  
  
<a name="migration"></a>   
## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="ffacf-129">Migrace: Nahrazení pro zastaralé volání</span><span class="sxs-lookup"><span data-stu-id="ffacf-129">Migration: Replacement for Obsolete Calls</span></span>  
  
### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="ffacf-130">Určení úrovně důvěryhodnosti sestavení</span><span class="sxs-lookup"><span data-stu-id="ffacf-130">Determining an Assembly’s Trust Level</span></span>  
 <span data-ttu-id="ffacf-131">Zásady CAS se často používá k určení sestavení nebo doménu aplikace oprávnění udělit sady nebo úroveň důvěryhodnosti.</span><span class="sxs-lookup"><span data-stu-id="ffacf-131">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="ffacf-132">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] Zpřístupňuje následující užitečné vlastnosti, které není potřeba řešit zásady zabezpečení:</span><span class="sxs-lookup"><span data-stu-id="ffacf-132">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes the following useful properties that do not need to resolve security policy:</span></span>  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
### <a name="application-domain-sandboxing"></a><span data-ttu-id="ffacf-133">Sandboxing domény aplikace</span><span class="sxs-lookup"><span data-stu-id="ffacf-133">Application Domain Sandboxing</span></span>  
 <span data-ttu-id="ffacf-134"><xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> Metoda se obvykle používá pro sandboxing sestavení v doméně aplikace.</span><span class="sxs-lookup"><span data-stu-id="ffacf-134">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="ffacf-135">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] Zveřejňuje členy, které nemají používat <xref:System.Security.Policy.PolicyLevel> pro tento účel.</span><span class="sxs-lookup"><span data-stu-id="ffacf-135">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="ffacf-136">Další informace najdete v tématu [postupy: spuštění částečně důvěryhodného kódu v izolovaném prostoru](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="ffacf-136">For more information, see [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>  
  
### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="ffacf-137">Určení sady bezpečné nebo přiměřené oprávnění pro částečně důvěryhodný kód</span><span class="sxs-lookup"><span data-stu-id="ffacf-137">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>  
 <span data-ttu-id="ffacf-138">Hostitelé často potřebují, určují oprávnění, které jsou vhodné pro hostovaný kód sandboxing.</span><span class="sxs-lookup"><span data-stu-id="ffacf-138">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="ffacf-139">Před [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], certifikační Autority zásady poskytují způsob, jak to provést pomocí <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="ffacf-139">Before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ffacf-140">Jako náhrada [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] poskytuje <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> metodu, která vrací bezpečnou standardní oprávnění nastavit pro zadaný důkaz.</span><span class="sxs-lookup"><span data-stu-id="ffacf-140">As a replacement, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>  
  
### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="ffacf-141">Non-Sandboxing scénáře: Přetížení pro načtení sestavení</span><span class="sxs-lookup"><span data-stu-id="ffacf-141">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>  
 <span data-ttu-id="ffacf-142">Pokud chcete používat parametry, které jinak nejsou k dispozici místo sandboxing sestavení může být z důvodu pro používání přetížení načtení sestavení.</span><span class="sxs-lookup"><span data-stu-id="ffacf-142">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="ffacf-143">Od verze [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], přetížení načtení sestavení, které nevyžadují <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> objekt jako parametr, například <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, povolit tento scénář.</span><span class="sxs-lookup"><span data-stu-id="ffacf-143">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>  
  
 <span data-ttu-id="ffacf-144">Pokud chcete izolovat sestavení, použijte <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> přetížení.</span><span class="sxs-lookup"><span data-stu-id="ffacf-144">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
<a name="compatibility"></a>   
## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="ffacf-145">Kompatibilita: Pomocí možnosti starší zásadu CAS</span><span class="sxs-lookup"><span data-stu-id="ffacf-145">Compatibility: Using the CAS Policy Legacy Option</span></span>  
 <span data-ttu-id="ffacf-146">[< NetFx40_LegacySecurityPolicy – > Konfigurace element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) umožňuje určit, který proces nebo knihovna používá starší zásadu CAS.</span><span class="sxs-lookup"><span data-stu-id="ffacf-146">The [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="ffacf-147">Když povolíte tento element, zásady a důkaz přetížení bude fungovat stejně jako v předchozích verzích rozhraní.</span><span class="sxs-lookup"><span data-stu-id="ffacf-147">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffacf-148">Chování zásad CAS je zadán na základě verze modulu runtime, takže úprava zásad CAS pro jednu verzi modulu runtime neovlivní zásady CAS jinou verzi.</span><span class="sxs-lookup"><span data-stu-id="ffacf-148">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffacf-149">Viz také</span><span class="sxs-lookup"><span data-stu-id="ffacf-149">See Also</span></span>  
 [<span data-ttu-id="ffacf-150">Postupy: spuštění částečně důvěryhodného kódu v izolovaném prostoru</span><span class="sxs-lookup"><span data-stu-id="ffacf-150">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)