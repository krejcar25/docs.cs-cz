---
title: "&lt;generatePublisherEvidence&gt; – Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 78293c396687f9c0c99ffdfbe94cf1f3c548289d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltgeneratepublisherevidencegt-element"></a><span data-ttu-id="3a516-102">&lt;generatePublisherEvidence&gt; – Element</span><span class="sxs-lookup"><span data-stu-id="3a516-102">&lt;generatePublisherEvidence&gt; Element</span></span>
<span data-ttu-id="3a516-103">Určuje, zda modul runtime vytvoří <xref:System.Security.Policy.Publisher> důkaz pro zabezpečení přístupu kódu (CAS).</span><span class="sxs-lookup"><span data-stu-id="3a516-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="3a516-104">\<Konfigurace ></span><span class="sxs-lookup"><span data-stu-id="3a516-104">\<configuration></span></span>  
<span data-ttu-id="3a516-105">\<modul runtime ></span><span class="sxs-lookup"><span data-stu-id="3a516-105">\<runtime></span></span>  
<span data-ttu-id="3a516-106">\<generatePublisherEvidence ></span><span class="sxs-lookup"><span data-stu-id="3a516-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a516-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3a516-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a516-108">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="3a516-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3a516-109">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="3a516-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a516-110">Atributy</span><span class="sxs-lookup"><span data-stu-id="3a516-110">Attributes</span></span>  
  
|<span data-ttu-id="3a516-111">Atribut</span><span class="sxs-lookup"><span data-stu-id="3a516-111">Attribute</span></span>|<span data-ttu-id="3a516-112">Popis</span><span class="sxs-lookup"><span data-stu-id="3a516-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3a516-113">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="3a516-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3a516-114">Určuje, zda modul runtime vytvoří <xref:System.Security.Policy.Publisher> důkaz.</span><span class="sxs-lookup"><span data-stu-id="3a516-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3a516-115">Atribut enabled</span><span class="sxs-lookup"><span data-stu-id="3a516-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3a516-116">Hodnota</span><span class="sxs-lookup"><span data-stu-id="3a516-116">Value</span></span>|<span data-ttu-id="3a516-117">Popis</span><span class="sxs-lookup"><span data-stu-id="3a516-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3a516-118">Nevytváří <xref:System.Security.Policy.Publisher> důkaz.</span><span class="sxs-lookup"><span data-stu-id="3a516-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="3a516-119">Vytvoří <xref:System.Security.Policy.Publisher> důkaz.</span><span class="sxs-lookup"><span data-stu-id="3a516-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="3a516-120">Toto nastavení je výchozí.</span><span class="sxs-lookup"><span data-stu-id="3a516-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a516-121">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="3a516-121">Child Elements</span></span>  
 <span data-ttu-id="3a516-122">Žádné</span><span class="sxs-lookup"><span data-stu-id="3a516-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a516-123">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="3a516-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3a516-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="3a516-124">Element</span></span>|<span data-ttu-id="3a516-125">Popis</span><span class="sxs-lookup"><span data-stu-id="3a516-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3a516-126">Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a516-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3a516-127">Obsahuje informace o možnostech inicializace modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="3a516-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a516-128">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3a516-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a516-129">V [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] a později tento element nemá žádný vliv na časů načtení sestavení.</span><span class="sxs-lookup"><span data-stu-id="3a516-129">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="3a516-130">Další informace najdete v části "Zjednodušení zásad zabezpečení" v [změny zabezpečení](../../../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="3a516-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="3a516-131">Modul CLR (CLR) pokusí se ověřit podpis Authenticode při načítání, chcete-li vytvořit <xref:System.Security.Policy.Publisher> důkaz pro sestavení.</span><span class="sxs-lookup"><span data-stu-id="3a516-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="3a516-132">Nicméně ve výchozím nastavení, většina aplikací není nutné <xref:System.Security.Policy.Publisher> důkaz.</span><span class="sxs-lookup"><span data-stu-id="3a516-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="3a516-133">Standardní zásady certifikační Autority na nespoléhá se <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="3a516-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="3a516-134">Neměli byste nepotřebné spuštění náklady spojené s ověření podpisu vydavatele, pokud vaše aplikace spustí na počítači s vlastní zásadu CAS nebo je hodláte splňují požadavky pro <xref:System.Security.Permissions.PublisherIdentityPermission> v prostředí s částečným vztahem důvěryhodnosti.</span><span class="sxs-lookup"><span data-stu-id="3a516-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="3a516-135">(Požadavky pro oprávnění identity vždy úspěšné v prostředí plné důvěryhodnosti.)</span><span class="sxs-lookup"><span data-stu-id="3a516-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a516-136">Doporučujeme, který služeb pomocí `<generatePublisherEvidence>` elementu, který chcete zvýšit výkon při spouštění.</span><span class="sxs-lookup"><span data-stu-id="3a516-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="3a516-137">Pomocí tohoto elementu může také pomoci zabránit zpoždění, které může způsobit, že vypršení časového limitu a zrušení spuštění služby.</span><span class="sxs-lookup"><span data-stu-id="3a516-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="3a516-138">Konfigurační soubor</span><span class="sxs-lookup"><span data-stu-id="3a516-138">Configuration File</span></span>  
 <span data-ttu-id="3a516-139">Tento element může použít pouze v konfiguračním souboru aplikace.</span><span class="sxs-lookup"><span data-stu-id="3a516-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a516-140">Příklad</span><span class="sxs-lookup"><span data-stu-id="3a516-140">Example</span></span>  
 <span data-ttu-id="3a516-141">Následující příklad ukazuje způsob použití `<generatePublisherEvidence>` elementu, který chcete zakázat zjišťování certifikační Autority zásad vydavatele pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="3a516-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a516-142">Viz také</span><span class="sxs-lookup"><span data-stu-id="3a516-142">See Also</span></span>  
 [<span data-ttu-id="3a516-143">Schéma nastavení běhového prostředí</span><span class="sxs-lookup"><span data-stu-id="3a516-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="3a516-144">Schéma konfiguračního souboru</span><span class="sxs-lookup"><span data-stu-id="3a516-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)