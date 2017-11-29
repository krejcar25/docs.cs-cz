---
title: "Stínové kopírování sestavení"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], shadow copying
- application domains, shadow copying assemblies
- shadow copying assemblies
ms.assetid: de8b8759-fca7-4260-896b-5a4973157672
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2eb71e1d03da16581ee25bf972be51ee2f63f585
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="shadow-copying-assemblies"></a><span data-ttu-id="cf42d-102">Stínové kopírování sestavení</span><span class="sxs-lookup"><span data-stu-id="cf42d-102">Shadow Copying Assemblies</span></span>
<span data-ttu-id="cf42d-103">Stínové kopírování sestavení povoluje, které se používají v doméně aplikace aktualizovat bez uvolnění domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="cf42d-103">Shadow copying enables assemblies that are used in an application domain to be updated without unloading the application domain.</span></span> <span data-ttu-id="cf42d-104">To je zvlášť užitečné pro aplikace, které musí být k dispozici nepřetržitě, jako je například weby technologie ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cf42d-104">This is particularly useful for applications that must be available continuously, such as ASP.NET sites.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf42d-105">Stínové kopírování sestavení není podporována v [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="cf42d-105">Shadow copying is not supported in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 <span data-ttu-id="cf42d-106">Modul common language runtime uzamkne soubor sestavení, když je sestavení načíst, takže soubor nelze aktualizovat, dokud sestavení je odpojen.</span><span class="sxs-lookup"><span data-stu-id="cf42d-106">The common language runtime locks an assembly file when the assembly is loaded, so the file cannot be updated until the assembly is unloaded.</span></span> <span data-ttu-id="cf42d-107">Jediný způsob, jak uvolnit sestavení z domény aplikace je uvolnění domény aplikace, takže za normálních podmínek sestavení nelze aktualizovat, na disku dokud všechny domény aplikace, které používají ho byly odstraněny.</span><span class="sxs-lookup"><span data-stu-id="cf42d-107">The only way to unload an assembly from an application domain is by unloading the application domain, so under normal circumstances, an assembly cannot be updated on disk until all the application domains that are using it have been unloaded.</span></span>  
  
 <span data-ttu-id="cf42d-108">Pokud domény aplikace je nakonfigurovaná pro stínové kopie souborů, sestavení z cesta k aplikaci zkopírovány do jiného umístění a načíst z tohoto umístění.</span><span class="sxs-lookup"><span data-stu-id="cf42d-108">When an application domain is configured to shadow copy files, assemblies from the application path are copied to another location and loaded from that location.</span></span> <span data-ttu-id="cf42d-109">Kopie uzamčeno, ale původní soubor sestavení je odemčený a může být aktualizován.</span><span class="sxs-lookup"><span data-stu-id="cf42d-109">The copy is locked, but the original assembly file is unlocked and can be updated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf42d-110">Pouze sestavení, které mohou být stínové kopie jsou ty, uložené v adresáři aplikace nebo jeho podadresářů, určeného <xref:System.AppDomainSetup.ApplicationBase%2A> a <xref:System.AppDomainSetup.PrivateBinPath%2A> vlastnosti při konfiguraci domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="cf42d-110">The only assemblies that can be shadow copied are those stored in the application directory or its subdirectories, specified by the <xref:System.AppDomainSetup.ApplicationBase%2A> and <xref:System.AppDomainSetup.PrivateBinPath%2A> properties when the application domain is configured.</span></span> <span data-ttu-id="cf42d-111">Sestavení, které jsou uložené v globální mezipaměti sestavení nejsou stínové kopie.</span><span class="sxs-lookup"><span data-stu-id="cf42d-111">Assemblies stored in the global assembly cache are not shadow copied.</span></span>  
  
 <span data-ttu-id="cf42d-112">Tento článek obsahuje následující části:</span><span class="sxs-lookup"><span data-stu-id="cf42d-112">This article contains the following sections:</span></span>  
  
-   <span data-ttu-id="cf42d-113">[Povolení a používání stínové kopírování sestavení](#EnablingAndUsing) popisuje základní použití a možnosti, které jsou k dispozici pro stínové kopírování sestavení.</span><span class="sxs-lookup"><span data-stu-id="cf42d-113">[Enabling and Using Shadow Copying](#EnablingAndUsing) describes the basic use and the options that are available for shadow copying.</span></span>  
  
-   <span data-ttu-id="cf42d-114">[Výkon při spouštění](#StartupPerformance) popisuje změny, které jsou vytvářeny stínovém kopírování v [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ke zlepšení výkonu spuštění a jak se vrátit k chování starší verze.</span><span class="sxs-lookup"><span data-stu-id="cf42d-114">[Startup Performance](#StartupPerformance) describes the changes that are made to shadow copying in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] to improve startup performance, and how to revert to the behavior of earlier versions.</span></span>  
  
-   <span data-ttu-id="cf42d-115">[Zastaralé metody](#ObsoleteMethods) popisuje změny, které byly provedeny vlastnosti a metody, které řídí stínové kopírování v [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf42d-115">[Obsolete Methods](#ObsoleteMethods) describes the changes that were made to the properties and methods that control shadow copying in the [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)].</span></span>  
  
<a name="EnablingAndUsing"></a>   
## <a name="enabling-and-using-shadow-copying"></a><span data-ttu-id="cf42d-116">Povolení a používání stínové kopírování sestavení</span><span class="sxs-lookup"><span data-stu-id="cf42d-116">Enabling and Using Shadow Copying</span></span>  
 <span data-ttu-id="cf42d-117">Můžete použít vlastnosti <xref:System.AppDomainSetup> třídy následujícím způsobem, aby konfigurace domény aplikace pro stínové kopírování sestavení:</span><span class="sxs-lookup"><span data-stu-id="cf42d-117">You can use the properties of the <xref:System.AppDomainSetup> class as follows to configure an application domain for shadow copying:</span></span>  
  
-   <span data-ttu-id="cf42d-118">Povolte stínové kopírování nastavením <xref:System.AppDomainSetup.ShadowCopyFiles%2A> vlastnost na hodnotu řetězce `"true"`.</span><span class="sxs-lookup"><span data-stu-id="cf42d-118">Enable shadow copying by setting the <xref:System.AppDomainSetup.ShadowCopyFiles%2A> property to the string value `"true"`.</span></span>  
  
     <span data-ttu-id="cf42d-119">Ve výchozím nastavení toto nastavení způsobí, že všechna sestavení v cestě aplikace před načtením zkopírovány do mezipaměti pro stahování.</span><span class="sxs-lookup"><span data-stu-id="cf42d-119">By default, this setting causes all assemblies in the application path to be copied to a download cache before they are loaded.</span></span> <span data-ttu-id="cf42d-120">Toto je stejný mezipaměti udržované modul common language runtime ukládat soubory stahované z jiných počítačů a modul common language runtime automaticky odstraní soubory, když už nejsou potřeba.</span><span class="sxs-lookup"><span data-stu-id="cf42d-120">This is the same cache maintained by the common language runtime to store files downloaded from other computers, and the common language runtime automatically deletes the files when they are no longer needed.</span></span>  
  
-   <span data-ttu-id="cf42d-121">Volitelně můžete nastavit vlastní umístění souborů služby stínové kopie vytvořené pomocí <xref:System.AppDomainSetup.CachePath%2A> vlastnost a <xref:System.AppDomainSetup.ApplicationName%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="cf42d-121">Optionally set a custom location for shadow copied files by using the <xref:System.AppDomainSetup.CachePath%2A> property and the <xref:System.AppDomainSetup.ApplicationName%2A> property.</span></span>  
  
     <span data-ttu-id="cf42d-122">Základní cesta pro umístění je tvořena zřetězením <xref:System.AppDomainSetup.ApplicationName%2A> vlastnost, která má <xref:System.AppDomainSetup.CachePath%2A> jako podadresáře.</span><span class="sxs-lookup"><span data-stu-id="cf42d-122">The base path for the location is formed by concatenating the <xref:System.AppDomainSetup.ApplicationName%2A> property to the <xref:System.AppDomainSetup.CachePath%2A> property as a subdirectory.</span></span> <span data-ttu-id="cf42d-123">Sestavení jsou zkopírována do podadresáře této cesty, ne pro samotné základní cesty.</span><span class="sxs-lookup"><span data-stu-id="cf42d-123">Assemblies are shadow copied to subdirectories of this path, not to the base path itself.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf42d-124">Pokud <xref:System.AppDomainSetup.ApplicationName%2A> není vlastnost nastavena, <xref:System.AppDomainSetup.CachePath%2A> vlastnost je ignorována a je použita mezipaměť pro stahování.</span><span class="sxs-lookup"><span data-stu-id="cf42d-124">If the <xref:System.AppDomainSetup.ApplicationName%2A> property is not set, the <xref:System.AppDomainSetup.CachePath%2A> property is ignored and the download cache is used.</span></span> <span data-ttu-id="cf42d-125">Nedojde k výjimce.</span><span class="sxs-lookup"><span data-stu-id="cf42d-125">No exception is thrown.</span></span>  
  
     <span data-ttu-id="cf42d-126">Pokud zadáte do vlastního umístění, jsou zodpovědní za vyčištění adresářů a zkopírovat soubory, když už nejsou potřeba.</span><span class="sxs-lookup"><span data-stu-id="cf42d-126">If you specify a custom location, you are responsible for cleaning up the directories and copied files when they are no longer needed.</span></span> <span data-ttu-id="cf42d-127">Nejsou automaticky odstraněny.</span><span class="sxs-lookup"><span data-stu-id="cf42d-127">They are not deleted automatically.</span></span>  
  
     <span data-ttu-id="cf42d-128">Existuje několik důvodů, proč můžete chtít nastavit vlastní umístění pro soubory stínové kopie.</span><span class="sxs-lookup"><span data-stu-id="cf42d-128">There are a few reasons why you might want to set a custom location for shadow copied files.</span></span> <span data-ttu-id="cf42d-129">Můžete chtít nastavit vlastní umístění pro soubory stínové kopie, pokud vaše aplikace generuje velký počet kopií.</span><span class="sxs-lookup"><span data-stu-id="cf42d-129">You might want to set a custom location for shadow copied files if your application generates a large number of copies.</span></span> <span data-ttu-id="cf42d-130">Mezipaměť pro stahování je omezená, velikost, nikoli životnost, takže je možné, že bude modul common language runtime pokusu o odstranění souboru, který je stále používáno.</span><span class="sxs-lookup"><span data-stu-id="cf42d-130">The download cache is limited by size, not by lifetime, so it is possible that the common language runtime will attempt to delete a file that is still in use.</span></span> <span data-ttu-id="cf42d-131">Dalším důvodem pro nastavení vlastního umístění je při spuštění aplikace uživatelé nebudou mít přístup pro zápis k umístění adresáře, který používá modul common language runtime pro mezipaměť pro stahování.</span><span class="sxs-lookup"><span data-stu-id="cf42d-131">Another reason to set a custom location is when users running your application do not have write access to the directory location the common language runtime uses for the download cache.</span></span>  
  
-   <span data-ttu-id="cf42d-132">Volitelně můžete omezit sestavení, které jsou stínové kopie pomocí <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="cf42d-132">Optionally limit the assemblies that are shadow copied by using the <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> property.</span></span>  
  
     <span data-ttu-id="cf42d-133">Když povolíte stínové kopírování sestavení pro doménu aplikace, ve výchozím nastavení se zkopírovat všechna sestavení v cesta k aplikaci – to znamená adresáře určené pomocí <xref:System.AppDomainSetup.ApplicationBase%2A> a <xref:System.AppDomainSetup.PrivateBinPath%2A> vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="cf42d-133">When you enable shadow copying for an application domain, the default is to copy all assemblies in the application path — that is, in the directories specified by the <xref:System.AppDomainSetup.ApplicationBase%2A> and <xref:System.AppDomainSetup.PrivateBinPath%2A> properties.</span></span> <span data-ttu-id="cf42d-134">Můžete omezit kopírování na vybrané adresáře vytvořením řetězec, který obsahuje pouze adresáře, které chcete stínové kopie a přiřadit řetězec, který má <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="cf42d-134">You can limit the copying to selected directories by creating a string that contains only those directories you want to shadow copy, and assigning the string to the <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> property.</span></span> <span data-ttu-id="cf42d-135">Adresáře oddělte středníky.</span><span class="sxs-lookup"><span data-stu-id="cf42d-135">Separate the directories with semicolons.</span></span> <span data-ttu-id="cf42d-136">Pouze sestavení, které jsou stínové kopie jsou zadány ve vybraných složkách.</span><span class="sxs-lookup"><span data-stu-id="cf42d-136">The only assemblies that are shadow copied are the ones in the selected directories.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf42d-137">Pokud nepřiřadíte řetězec tak, aby <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> vlastnost, nebo pokud tuto vlastnost nastavíte na `null`, všechna sestavení v adresáři určeného <xref:System.AppDomainSetup.ApplicationBase%2A> a <xref:System.AppDomainSetup.PrivateBinPath%2A> vlastnosti jsou stínové kopie.</span><span class="sxs-lookup"><span data-stu-id="cf42d-137">If you don’t assign a string to the <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> property, or if you set this property to `null`, all assemblies in the directories specified by the <xref:System.AppDomainSetup.ApplicationBase%2A> and <xref:System.AppDomainSetup.PrivateBinPath%2A> properties are shadow copied.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cf42d-138">Cesty k adresáři nesmí obsahovat středníky, protože je středník oddělovací znak.</span><span class="sxs-lookup"><span data-stu-id="cf42d-138">Directory paths must not contain semicolons, because the semicolon is the delimiter character.</span></span> <span data-ttu-id="cf42d-139">Neexistuje žádný řídicí znak pro středníky.</span><span class="sxs-lookup"><span data-stu-id="cf42d-139">There is no escape character for semicolons.</span></span>  
  
<a name="StartupPerformance"></a>   
## <a name="startup-performance"></a><span data-ttu-id="cf42d-140">Výkon při spouštění</span><span class="sxs-lookup"><span data-stu-id="cf42d-140">Startup Performance</span></span>  
 <span data-ttu-id="cf42d-141">Když se spustí doménu aplikace, která používá stínové kopírování sestavení, dochází ke zpoždění při sestavení v adresáři aplikace jsou zkopírovány do adresáře stínové kopie nebo ověřit, zda jsou již v tomto umístění.</span><span class="sxs-lookup"><span data-stu-id="cf42d-141">When an application domain that uses shadow copying starts, there is a delay while assemblies in the application directory are copied to the shadow copy directory, or verified if they are already in that location.</span></span> <span data-ttu-id="cf42d-142">Před [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], všechny sestavení, které byly zkopírovány do dočasného adresáře.</span><span class="sxs-lookup"><span data-stu-id="cf42d-142">Before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], all assemblies were copied to a temporary directory.</span></span> <span data-ttu-id="cf42d-143">Každé sestavení bylo otevřeno pro ověření název sestavení a byl ověřen silný název.</span><span class="sxs-lookup"><span data-stu-id="cf42d-143">Each assembly was opened to verify the assembly name, and the strong name was validated.</span></span> <span data-ttu-id="cf42d-144">Každé sestavení zkontroloval se zda bylo aktualizováno později, než kopie v adresáři stínové kopie.</span><span class="sxs-lookup"><span data-stu-id="cf42d-144">Each assembly was checked to see whether it had been updated more recently than the copy in the shadow copy directory.</span></span> <span data-ttu-id="cf42d-145">Pokud ano, byl zkopírován do adresáře stínové kopie.</span><span class="sxs-lookup"><span data-stu-id="cf42d-145">If so, it was copied to the shadow copy directory.</span></span> <span data-ttu-id="cf42d-146">Nakonec dočasná kopie byly zrušeny.</span><span class="sxs-lookup"><span data-stu-id="cf42d-146">Finally, the temporary copies were discarded.</span></span>  
  
 <span data-ttu-id="cf42d-147">Od verze [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], výchozí chování při spuštění je přímo porovnat soubor datum a čas každé sestavení v adresáři aplikace s souboru datum a čas kopie v adresáři stínové kopie.</span><span class="sxs-lookup"><span data-stu-id="cf42d-147">Beginning with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], the default startup behavior is to directly compare the file date and time of each assembly in the application directory with the file date and time of the copy in the shadow copy directory.</span></span> <span data-ttu-id="cf42d-148">Pokud sestavení byl aktualizován, se zkopíruje pomocí stejného postupu jako v předchozích verzích rozhraní .NET Framework; jinak je načten kopie v adresáři stínové kopie.</span><span class="sxs-lookup"><span data-stu-id="cf42d-148">If the assembly has been updated, it is copied by using the same procedure as in earlier versions of the .NET Framework; otherwise, the copy in the shadow copy directory is loaded.</span></span>  
  
 <span data-ttu-id="cf42d-149">Výsledné zlepšení výkonu je největší pro aplikace, ve kterých sestavení často nemění a změny jsou obvykle prováděny v malou podmnožinu sestavení.</span><span class="sxs-lookup"><span data-stu-id="cf42d-149">The resulting performance improvement is largest for applications in which assemblies do not change frequently and changes usually occur in a small subset of assemblies.</span></span> <span data-ttu-id="cf42d-150">Pokud se většina sestavení v o změnu aplikace často, nové výchozí chování může způsobit snížení výkonu.</span><span class="sxs-lookup"><span data-stu-id="cf42d-150">If a majority of assemblies in an application change frequently, the new default behavior might cause a performance regression.</span></span> <span data-ttu-id="cf42d-151">Chování při spuštění z předchozí verze rozhraní .NET Framework můžete obnovit tak, že přidáte [ \<shadowCopyVerifyByTimestamp > element](../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md) do konfiguračního souboru s `enabled="false"`.</span><span class="sxs-lookup"><span data-stu-id="cf42d-151">You can restore the startup behavior of previous versions of the .NET Framework by adding the [\<shadowCopyVerifyByTimestamp> element](../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md) to the configuration file, with `enabled="false"`.</span></span>  
  
<a name="ObsoleteMethods"></a>   
## <a name="obsolete-methods"></a><span data-ttu-id="cf42d-152">Zastaralé metody</span><span class="sxs-lookup"><span data-stu-id="cf42d-152">Obsolete Methods</span></span>  
 <span data-ttu-id="cf42d-153"><xref:System.AppDomain> Třída obsahuje několik metod, jako například <xref:System.AppDomain.SetShadowCopyFiles%2A> a <xref:System.AppDomain.ClearShadowCopyPath%2A>, který lze použít k řízení stínové kopírování na doménu aplikace, ale tyto byly označeny jako zastaralé v rozhraní .NET Framework verze 2.0.</span><span class="sxs-lookup"><span data-stu-id="cf42d-153">The <xref:System.AppDomain> class has several methods, such as <xref:System.AppDomain.SetShadowCopyFiles%2A> and <xref:System.AppDomain.ClearShadowCopyPath%2A>, that can be used to control shadow copying on an application domain, but these have been marked obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="cf42d-154">Doporučený způsob konfigurace domény aplikace pro stínové kopírování sestavení je použití vlastnosti <xref:System.AppDomainSetup> třídy.</span><span class="sxs-lookup"><span data-stu-id="cf42d-154">The recommended way to configure an application domain for shadow copying is to use the properties of the <xref:System.AppDomainSetup> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf42d-155">Viz také</span><span class="sxs-lookup"><span data-stu-id="cf42d-155">See Also</span></span>  
 <xref:System.AppDomainSetup.ShadowCopyFiles%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.CachePath%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.ApplicationName%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.ShadowCopyDirectories%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="cf42d-156">\<shadowCopyVerifyByTimestamp > elementu</span><span class="sxs-lookup"><span data-stu-id="cf42d-156">\<shadowCopyVerifyByTimestamp> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)