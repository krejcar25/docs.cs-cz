---
title: Element &lt;serviceAuthorization&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cdbe676fa73c040737c947902d64b2c0e689e2a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltserviceauthorizationgt-element"></a><span data-ttu-id="f2cc1-102">Element &lt;serviceAuthorization&gt;</span><span class="sxs-lookup"><span data-stu-id="f2cc1-102">&lt;serviceAuthorization&gt; element</span></span>
<span data-ttu-id="f2cc1-103">Určuje nastavení, které zajistí autorizaci přístupu k operacím služby</span><span class="sxs-lookup"><span data-stu-id="f2cc1-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="f2cc1-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f2cc1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f2cc1-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="f2cc1-105">\<behaviors></span></span>  
<span data-ttu-id="f2cc1-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f2cc1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f2cc1-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="f2cc1-107">\<behavior></span></span>  
<span data-ttu-id="f2cc1-108">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="f2cc1-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cc1-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f2cc1-109">Syntax</span></span>  
  
```xml  
<serviceAuthorization  
     impersonateCallerForAllOperations="Boolean"  
      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"  
      roleProviderName="String"  
      serviceAuthorizationManagerType="String" />  
      <authorizationPolicies>  
         <add policyType="String" />  
      </authorizationPolicies>  
</serviceAuthorization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2cc1-110">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="f2cc1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f2cc1-111">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2cc1-112">Atributy</span><span class="sxs-lookup"><span data-stu-id="f2cc1-112">Attributes</span></span>  
  
|<span data-ttu-id="f2cc1-113">Atribut</span><span class="sxs-lookup"><span data-stu-id="f2cc1-113">Attribute</span></span>|<span data-ttu-id="f2cc1-114">Popis</span><span class="sxs-lookup"><span data-stu-id="f2cc1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2cc1-115">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="f2cc1-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="f2cc1-116">Logická hodnota, která určuje, pokud všechny operace ve službě zosobnit volající.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="f2cc1-117">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="f2cc1-118">Pokud konkrétní operaci služby zosobňuje volající, kontext přístup z více vláken je přepnout do kontextu volající před provedením zadaná služba.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="f2cc1-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="f2cc1-119">principalPermissionMode</span></span>|<span data-ttu-id="f2cc1-120">Nastaví objekt se používá k provádění operací na serveru.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="f2cc1-121">Následující hodnoty:</span><span class="sxs-lookup"><span data-stu-id="f2cc1-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="f2cc1-122">-None</span><span class="sxs-lookup"><span data-stu-id="f2cc1-122">-   None</span></span><br /><span data-ttu-id="f2cc1-123">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="f2cc1-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="f2cc1-124">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="f2cc1-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="f2cc1-125">-Vlastní</span><span class="sxs-lookup"><span data-stu-id="f2cc1-125">-   Custom</span></span><br /><br /> <span data-ttu-id="f2cc1-126">Výchozí hodnota je UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="f2cc1-127">Hodnota je typu <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="f2cc1-128">Další informace o použití tohoto atributu naleznete v části [postupy: omezení přístupu pomocí třídy PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="f2cc1-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="f2cc1-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="f2cc1-129">roleProviderName</span></span>|<span data-ttu-id="f2cc1-130">Řetězec, který určuje název zprostředkovatele rolí, která poskytuje informace o rolích pro aplikaci Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f2cc1-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f2cc1-131">Výchozí hodnota je prázdný řetězec.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="f2cc1-132">Třída ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="f2cc1-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="f2cc1-133">Řetězec obsahující typ Správce autorizací služby.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="f2cc1-134">Další informace naleznete v tématu <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2cc1-135">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="f2cc1-135">Child Elements</span></span>  
  
|<span data-ttu-id="f2cc1-136">Prvek</span><span class="sxs-lookup"><span data-stu-id="f2cc1-136">Element</span></span>|<span data-ttu-id="f2cc1-137">Popis</span><span class="sxs-lookup"><span data-stu-id="f2cc1-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2cc1-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="f2cc1-138">authorizationPolicies</span></span>|<span data-ttu-id="f2cc1-139">Obsahuje kolekci typů zásad autorizace, které lze přidat pomocí `add` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="f2cc1-140">Každá zásada autorizace obsahuje jediný požadované `policyType` atribut, který obsahuje řetězec.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="f2cc1-141">Atribut určuje zásad autorizace, která umožňuje transformace jednu sadu vstupních deklarací identity na jinou sadu deklarací identity.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="f2cc1-142">Řízení přístupu může být povolen nebo odepřen, na základě.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="f2cc1-143">Další informace naleznete v tématu <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2cc1-144">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="f2cc1-144">Parent Elements</span></span>  
  
|<span data-ttu-id="f2cc1-145">Prvek</span><span class="sxs-lookup"><span data-stu-id="f2cc1-145">Element</span></span>|<span data-ttu-id="f2cc1-146">Popis</span><span class="sxs-lookup"><span data-stu-id="f2cc1-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2cc1-147">\<chování ></span><span class="sxs-lookup"><span data-stu-id="f2cc1-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f2cc1-148">Obsahuje kolekci nastavení pro chování služby.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2cc1-149">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f2cc1-149">Remarks</span></span>  
 <span data-ttu-id="f2cc1-150">Tato část obsahuje prvky, které mají vliv na ověřování, vlastní roli zprostředkovatele a zosobnění.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="f2cc1-151">`principalPermissionMode` Atribut určuje skupiny uživatelů pro použití při použití chráněná metoda autorizace.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="f2cc1-152">Výchozí hodnota je `UseWindowsGroups` a určuje skupiny systému Windows, jako je například "Administrators" nebo "Uživatelé," se vyhledávají identity pokusu o přístup k prostředku.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="f2cc1-153">Můžete také zadat `UseAspNetRoles` používat vlastní roli zprostředkovatele, který je nakonfigurovaný pod \<system.web > elementu, jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
```xml  
<system.web>  
  <membership defaultProvider="SqlProvider"   
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add   
          name="SqlProvider"   
          type="System.Web.Security.SqlMembershipProvider"   
          connectionStringName="SqlConn"  
          applicationName="MembershipProvider"  
          enablePasswordRetrieval="false"  
          enablePasswordReset="false"  
          requiresQuestionAndAnswer="false"  
          requiresUniqueEmail="true"  
          passwordFormat="Hashed" />  
     </providers>  
   </membership>  
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 <span data-ttu-id="f2cc1-154">Následující kód ukazuje `roleProviderName` použít s `principalPermissionMode` atribut.</span><span class="sxs-lookup"><span data-stu-id="f2cc1-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>  
   <behavior name="ServiceBehaviour">  
     <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                           roleProviderName ="SqlProvider" />  
   </behavior>   
<!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
 <span data-ttu-id="f2cc1-155">Podrobný příklad použití tohoto elementu konfigurace najdete v tématu [autorizace přístupu k operacím služby](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) a [zásad autorizace](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f2cc1-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cc1-156">Viz také</span><span class="sxs-lookup"><span data-stu-id="f2cc1-156">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 [<span data-ttu-id="f2cc1-157">Chování zabezpečení</span><span class="sxs-lookup"><span data-stu-id="f2cc1-157">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="f2cc1-158">Autorizace přístupu k operacím služby</span><span class="sxs-lookup"><span data-stu-id="f2cc1-158">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="f2cc1-159">Postupy: vytvoření vlastního Správce autorizací pro službu</span><span class="sxs-lookup"><span data-stu-id="f2cc1-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="f2cc1-160">Postupy: omezení přístupu pomocí třídy PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="f2cc1-160">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 [<span data-ttu-id="f2cc1-161">Zásady autorizace</span><span class="sxs-lookup"><span data-stu-id="f2cc1-161">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)