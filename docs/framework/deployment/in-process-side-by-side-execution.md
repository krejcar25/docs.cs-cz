---
title: "Vnitroprocesové souběžné provádění"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fa65be2eee481e20231bacb5d0861fa3d2c03f92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="in-process-side-by-side-execution"></a><span data-ttu-id="4f502-102">Vnitroprocesové souběžné provádění</span><span class="sxs-lookup"><span data-stu-id="4f502-102">In-Process Side-by-Side Execution</span></span>
<span data-ttu-id="4f502-103">Od verze [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], můžete použít v procesu souběžného hostování spustit více verzí common language runtime (CLR) v jediném procesu.</span><span class="sxs-lookup"><span data-stu-id="4f502-103">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use in-process side-by-side hosting to run multiple versions of the common language runtime (CLR) in a single process.</span></span> <span data-ttu-id="4f502-104">Ve výchozím nastavení spravované komponenty COM s verzí rozhraní .NET Framework, které byly vytvořené s nástroji, bez ohledu na verzi rozhraní .NET Framework, který je načten pro proces spustit.</span><span class="sxs-lookup"><span data-stu-id="4f502-104">By default, managed COM components run with the .NET Framework version they were built with, regardless of the .NET Framework version that is loaded for the process.</span></span>  
  
## <a name="background"></a><span data-ttu-id="4f502-105">Pozadí</span><span class="sxs-lookup"><span data-stu-id="4f502-105">Background</span></span>  
 <span data-ttu-id="4f502-106">Rozhraní .NET Framework má vždy zadaná vedle sebe hostování pro spravovaný kód aplikace, ale předtím, než [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], neposkytl této funkce pro spravované COM – součásti.</span><span class="sxs-lookup"><span data-stu-id="4f502-106">The .NET Framework has always provided side-by-side hosting for managed code applications, but before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], it did not provide that functionality for managed COM components.</span></span> <span data-ttu-id="4f502-107">V minulosti spravované komponenty modelu COM, které byly načteny do procesu spustili verzi modulu runtime, která již byla načtena nebo s nainstalovanou verzí rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f502-107">In the past, managed COM components that were loaded into a process ran either with the version of the runtime that was already loaded or with the latest installed version of the .NET Framework.</span></span> <span data-ttu-id="4f502-108">Pokud byla tato verze není kompatibilní s komponenty modelu COM, skončí s chybou komponentu.</span><span class="sxs-lookup"><span data-stu-id="4f502-108">If this version was not compatible with the COM component, the component would fail.</span></span>  
  
 <span data-ttu-id="4f502-109">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] Poskytuje nový přístup k hostování vedle sebe, který zajišťuje následující:</span><span class="sxs-lookup"><span data-stu-id="4f502-109">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] provides a new approach to side-by-side hosting that ensures the following:</span></span>  
  
-   <span data-ttu-id="4f502-110">Instalace nové verze rozhraní .NET Framework nemá žádný vliv na stávající aplikace.</span><span class="sxs-lookup"><span data-stu-id="4f502-110">Installing a new version of the .NET Framework has no effect on existing applications.</span></span>  
  
-   <span data-ttu-id="4f502-111">Aplikace spustit pro verzi rozhraní .NET Framework, které byly vytvořené s nástroji.</span><span class="sxs-lookup"><span data-stu-id="4f502-111">Applications run against the version of the .NET Framework that they were built with.</span></span> <span data-ttu-id="4f502-112">Nepoužívají novou verzi rozhraní .NET Framework pokud výslovně směrované Uděláte to tak.</span><span class="sxs-lookup"><span data-stu-id="4f502-112">They do not use the new version of the .NET Framework unless expressly directed to do so.</span></span> <span data-ttu-id="4f502-113">Je však snazší pro aplikace pro přechod na novou verzi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f502-113">However, it is easier for applications to transition to using a new version of the .NET Framework.</span></span>  
  
## <a name="effects-on-users-and-developers"></a><span data-ttu-id="4f502-114">Dopady na uživatelů a vývojářů</span><span class="sxs-lookup"><span data-stu-id="4f502-114">Effects on Users and Developers</span></span>  
  
-   <span data-ttu-id="4f502-115">**Koncovým uživatelům a správcům systému**.</span><span class="sxs-lookup"><span data-stu-id="4f502-115">**End users and system administrators**.</span></span> <span data-ttu-id="4f502-116">Tito uživatelé nyní může mít větší jistotu, že při instalaci nové verze modulu runtime nezávisle nebo s aplikací, bude mít žádný vliv na svých počítačích.</span><span class="sxs-lookup"><span data-stu-id="4f502-116">These users can now have greater confidence that when they install a new version of the runtime, either independently or with an application, it will have no impact on their computers.</span></span> <span data-ttu-id="4f502-117">Existující aplikace bude nadále spouštět jako před.</span><span class="sxs-lookup"><span data-stu-id="4f502-117">Existing applications will continue to run as they did before.</span></span>  
  
-   <span data-ttu-id="4f502-118">**Vývojáři aplikací**.</span><span class="sxs-lookup"><span data-stu-id="4f502-118">**Application developers**.</span></span> <span data-ttu-id="4f502-119">Souběžně sdílená hostování nemá téměř žádný vliv na vývojáře aplikace.</span><span class="sxs-lookup"><span data-stu-id="4f502-119">Side-by-side hosting has almost no effect on application developers.</span></span> <span data-ttu-id="4f502-120">Ve výchozím nastavení aplikace vždy spouštění verzi rozhraní .NET Framework, které byly vytvořené na; To se nezměnilo.</span><span class="sxs-lookup"><span data-stu-id="4f502-120">By default, applications always run against the version of the .NET Framework they were built on; this has not changed.</span></span> <span data-ttu-id="4f502-121">Vývojáři můžou, ale toto chování potlačit a přímé aplikace spuštěna v novější verzi rozhraní .NET Framework (viz [scénář 2](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="4f502-121">However, developers can override this behavior and direct the application to run under a newer version of the .NET Framework (see [scenario 2](#scenarios)).</span></span>  
  
-   <span data-ttu-id="4f502-122">**Vývojáři knihoven a spotřebitelé**.</span><span class="sxs-lookup"><span data-stu-id="4f502-122">**Library developers and consumers**.</span></span> <span data-ttu-id="4f502-123">Souběžně sdílená hostování nevyřeší problémy s kompatibilitou vzhled vývojáři této knihovny.</span><span class="sxs-lookup"><span data-stu-id="4f502-123">Side-by-side hosting does not solve the compatibility problems that library developers face.</span></span> <span data-ttu-id="4f502-124">Do knihovny, která je přímo zavedená aplikací – buď prostřednictvím přímý odkaz, nebo prostřednictvím <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> volání – budou nadále používat modul runtime <xref:System.AppDomain> je načten do.</span><span class="sxs-lookup"><span data-stu-id="4f502-124">A library that is directly loaded by an application -- either through a direct reference or through an <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> call -- continues to use the runtime of the <xref:System.AppDomain> it is loaded into.</span></span> <span data-ttu-id="4f502-125">Měli byste otestovat knihovnách proti všechny verze rozhraní .NET Framework, která chcete podporovat.</span><span class="sxs-lookup"><span data-stu-id="4f502-125">You should test your libraries against all versions of the .NET Framework that you want to support.</span></span> <span data-ttu-id="4f502-126">Pokud aplikace kompiluje pomocí [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] runtime ale obsahuje knihovnu, který byl vytvořený pomocí dřívější modul runtime, budou používat tuto knihovnu [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] runtime také.</span><span class="sxs-lookup"><span data-stu-id="4f502-126">If an application is compiled using the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] runtime but includes a library that was built using an earlier runtime, that library will use the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] runtime as well.</span></span> <span data-ttu-id="4f502-127">Ale pokud máte aplikaci, která byla vytvořena pomocí dřívější runtime a knihovny, který byl vytvořený pomocí [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], musíte vynutit aplikace také pomocí [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] (najdete v části [scénář 3](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="4f502-127">However, if you have an application that was built using an earlier runtime and a library that was built using the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], you must force your application to also use the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] (see [scenario 3](#scenarios)).</span></span>  
  
-   <span data-ttu-id="4f502-128">**Spravované vývojáři komponent COM**.</span><span class="sxs-lookup"><span data-stu-id="4f502-128">**Managed COM component developers**.</span></span> <span data-ttu-id="4f502-129">V minulosti spravované součásti COM automaticky proběhla za použití nejnovější verzi modulu runtime v počítači nainstalována.</span><span class="sxs-lookup"><span data-stu-id="4f502-129">In the past, managed COM components automatically ran using the latest version of the runtime installed on the computer.</span></span> <span data-ttu-id="4f502-130">COM – součásti proti verzi modulu runtime, které byly vytvořené s můžete nyní spustit.</span><span class="sxs-lookup"><span data-stu-id="4f502-130">You can now execute COM components against the version of the runtime they were built with.</span></span>  
  
     <span data-ttu-id="4f502-131">Jak je uvedeno v následující tabulce, můžete spustit součásti, které byly vytvořeny s rozhraním .NET Framework verze 1.1 node souběžně s součásti verze 4, ale nebudou moct spustit verze 2.0, 3.0 nebo 3.5 součásti, protože není k dispozici pro ty hostování vedle sebe verze.</span><span class="sxs-lookup"><span data-stu-id="4f502-131">As shown by the following table, components that were built with the .NET Framework version 1.1 can run side by side with version 4 components, but they cannot run with version 2.0, 3.0, or 3.5 components, because side-by-side hosting is not available for those versions.</span></span>  
  
    |<span data-ttu-id="4f502-132">Verze rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4f502-132">.NET Framework version</span></span>|<span data-ttu-id="4f502-133">1.1</span><span class="sxs-lookup"><span data-stu-id="4f502-133">1.1</span></span>|<span data-ttu-id="4f502-134">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="4f502-134">2.0 - 3.5</span></span>|<span data-ttu-id="4f502-135">4</span><span class="sxs-lookup"><span data-stu-id="4f502-135">4</span></span>|  
    |----------------------------|---------|----------------|-------|  
    |<span data-ttu-id="4f502-136">1.1</span><span class="sxs-lookup"><span data-stu-id="4f502-136">1.1</span></span>|<span data-ttu-id="4f502-137">Nelze použít</span><span class="sxs-lookup"><span data-stu-id="4f502-137">Not applicable</span></span>|<span data-ttu-id="4f502-138">Ne</span><span class="sxs-lookup"><span data-stu-id="4f502-138">No</span></span>|<span data-ttu-id="4f502-139">Ano</span><span class="sxs-lookup"><span data-stu-id="4f502-139">Yes</span></span>|  
    |<span data-ttu-id="4f502-140">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="4f502-140">2.0 - 3.5</span></span>|<span data-ttu-id="4f502-141">Ne</span><span class="sxs-lookup"><span data-stu-id="4f502-141">No</span></span>|<span data-ttu-id="4f502-142">Nelze použít</span><span class="sxs-lookup"><span data-stu-id="4f502-142">Not applicable</span></span>|<span data-ttu-id="4f502-143">Ano</span><span class="sxs-lookup"><span data-stu-id="4f502-143">Yes</span></span>|  
    |<span data-ttu-id="4f502-144">4</span><span class="sxs-lookup"><span data-stu-id="4f502-144">4</span></span>|<span data-ttu-id="4f502-145">Ano</span><span class="sxs-lookup"><span data-stu-id="4f502-145">Yes</span></span>|<span data-ttu-id="4f502-146">Ano</span><span class="sxs-lookup"><span data-stu-id="4f502-146">Yes</span></span>|<span data-ttu-id="4f502-147">Nelze použít</span><span class="sxs-lookup"><span data-stu-id="4f502-147">Not applicable</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4f502-148">Verze rozhraní .NET framework 3.0 a 3.5 jsou postupně vytvořeny na verze 2.0 a není nutné spustit souběžně.</span><span class="sxs-lookup"><span data-stu-id="4f502-148">.NET Framework versions 3.0 and 3.5 are built incrementally on version 2.0, and do not need to run side by side.</span></span> <span data-ttu-id="4f502-149">Toto jsou ze své podstaty stejnou verzi.</span><span class="sxs-lookup"><span data-stu-id="4f502-149">These are inherently the same version.</span></span>  
  
<a name="scenarios"></a>   
## <a name="common-side-by-side-hosting-scenarios"></a><span data-ttu-id="4f502-150">Běžné scénáře hostování vedle sebe</span><span class="sxs-lookup"><span data-stu-id="4f502-150">Common Side-by-Side Hosting Scenarios</span></span>  
  
-   <span data-ttu-id="4f502-151">**Scénář 1:** nativní aplikaci, která používá komponenty modelu COM, které jsou vytvořené ve starších verzích rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f502-151">**Scenario 1:** Native application that uses COM components built with earlier versions of the .NET Framework.</span></span>  
  
     <span data-ttu-id="4f502-152">Nainstalovaná verze rozhraní .NET framework: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] a všech ostatních verzí rozhraní .NET Framework používané komponenty COM.</span><span class="sxs-lookup"><span data-stu-id="4f502-152">.NET Framework versions installed: The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] and all other versions of the .NET Framework used by the COM components.</span></span>  
  
     <span data-ttu-id="4f502-153">Co dělat: V tomto scénáři nic nestane.</span><span class="sxs-lookup"><span data-stu-id="4f502-153">What to do: In this scenario, do nothing.</span></span> <span data-ttu-id="4f502-154">Komponenty COM se spustí s verzí rozhraní .NET Framework byla zaregistrována.</span><span class="sxs-lookup"><span data-stu-id="4f502-154">The COM components will run with the version of the .NET Framework they were registered with.</span></span>  
  
-   <span data-ttu-id="4f502-155">**Scénář 2**: spravované aplikace vytvořené s nástroji [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] , ve kterém by se spouští s [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)], ale chcete spustit na [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] Pokud není k dispozici verze 2.0.</span><span class="sxs-lookup"><span data-stu-id="4f502-155">**Scenario 2**: Managed application built with the [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] that you would prefer to run with the [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)], but are willing to run on the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] if version 2.0 is not present.</span></span>  
  
     <span data-ttu-id="4f502-156">Nainstalovaná verze rozhraní .NET framework: dřívější verzi rozhraní .NET Framework a [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f502-156">.NET Framework versions installed: An earlier version of the .NET Framework and the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
     <span data-ttu-id="4f502-157">Co dělat: V [konfigurační soubor aplikace](../../../docs/framework/configure-apps/index.md) v adresáři aplikace používat [ \<spuštění > element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) a [ \<supportedRuntime > Element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) nastavit takto:</span><span class="sxs-lookup"><span data-stu-id="4f502-157">What to do: In the [application configuration file](../../../docs/framework/configure-apps/index.md) in the application directory, use the [\<startup> element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) and the [\<supportedRuntime> element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="4f502-158">**Scénář 3:** nativní aplikaci, která používá komponenty modelu COM, které jsou vytvořené ve starších verzích rozhraní .NET Framework, který chcete spustit s [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f502-158">**Scenario 3:** Native application that uses COM components built with earlier versions of the .NET Framework that you want to run with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
     <span data-ttu-id="4f502-159">Nainstalovaná verze rozhraní .NET framework: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f502-159">.NET Framework versions installed: The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
     <span data-ttu-id="4f502-160">Co dělat: V konfiguračním souboru aplikace v adresáři aplikace, použijte `<startup>` element s `useLegacyV2RuntimeActivationPolicy` atribut nastaven na `true` a `<supportedRuntime>` element nastavit takto:</span><span class="sxs-lookup"><span data-stu-id="4f502-160">What to do: In the application configuration file in the application directory, use the `<startup>` element with the `useLegacyV2RuntimeActivationPolicy` attribute set to `true` and the `<supportedRuntime>` element set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="4f502-161">Příklad</span><span class="sxs-lookup"><span data-stu-id="4f502-161">Example</span></span>  
 <span data-ttu-id="4f502-162">Následující příklad ukazuje nespravované modelu COM hostitele se systémem spravované komponenty modelu COM pomocí verzi rozhraní .NET Framework, kompilovanou pro komponentu použít.</span><span class="sxs-lookup"><span data-stu-id="4f502-162">The following example demonstrates an unmanaged COM host that is running a managed COM component by using the version of the .NET Framework that the component was compiled to use.</span></span>  
  
 <span data-ttu-id="4f502-163">Spusťte následující příklad, kompilace a zaregistrovat následující spravovaných pomocí součásti COM [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f502-163">To run the following example, compile and register the following managed COM component using the [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].</span></span> <span data-ttu-id="4f502-164">Zaregistrovat komponentu, na **projektu** nabídky, klikněte na tlačítko **vlastnosti**, klikněte na tlačítko **sestavení** a pak vyberte **zaregistrovat zprostředkovatel komunikace s objekty COM**zaškrtávací políčko.</span><span class="sxs-lookup"><span data-stu-id="4f502-164">To register the component, on the **Project** menu, click **Properties**, click the **Build** tab, and then select the **Register for COM interop** check box.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="4f502-165">Zkompilujte následující nespravovaná aplikace C++, která aktivuje objektu COM, který byl vytvořený v předchozím příkladu.</span><span class="sxs-lookup"><span data-stu-id="4f502-165">Compile the following unmanaged C++ application, which activates the COM object that is created by the previous example.</span></span>  
  
```  
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");   
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f502-166">Viz také</span><span class="sxs-lookup"><span data-stu-id="4f502-166">See Also</span></span>  
 [<span data-ttu-id="4f502-167">\<spuštění > elementu</span><span class="sxs-lookup"><span data-stu-id="4f502-167">\<startup> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
 [<span data-ttu-id="4f502-168">\<supportedRuntime > elementu</span><span class="sxs-lookup"><span data-stu-id="4f502-168">\<supportedRuntime> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)