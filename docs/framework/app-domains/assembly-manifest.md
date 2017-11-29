---
title: "Manifest sestavení"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest
- dynamic assemblies, assembly manifest
- metadata, assembly manifest
- culture, assembly manifest
- assemblies [.NET Framework], metadata
ms.assetid: 8e40fab9-549d-4731-aec2-ffa47a382de0
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1df64129a0ae15b5bad387a62ca60bb4b1b92f7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-manifest"></a><span data-ttu-id="3c803-102">Manifest sestavení</span><span class="sxs-lookup"><span data-stu-id="3c803-102">Assembly Manifest</span></span>
<span data-ttu-id="3c803-103">Všechna sestavení, zda statickou nebo dynamickou, obsahuje kolekci dat, která popisuje, jak elementů v sestavení vztahují k sobě navzájem.</span><span class="sxs-lookup"><span data-stu-id="3c803-103">Every assembly, whether static or dynamic, contains a collection of data that describes how the elements in the assembly relate to each other.</span></span> <span data-ttu-id="3c803-104">Manifest sestavení obsahuje tato metadata sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-104">The assembly manifest contains this assembly metadata.</span></span> <span data-ttu-id="3c803-105">Manifest sestavení obsahuje všechna metadata potřebná pro určení požadavky verze sestavení a zabezpečení identity a všechny metadata potřebná k definování oboru sestavení a odkazy na prostředky a třídy.</span><span class="sxs-lookup"><span data-stu-id="3c803-105">An assembly manifest contains all the metadata needed to specify the assembly's version requirements and security identity, and all metadata needed to define the scope of the assembly and resolve references to resources and classes.</span></span> <span data-ttu-id="3c803-106">Manifest sestavení může být uložená v buď PE soubor (příponou .exe nebo .dll) s kódem (MSIL intermediate language) Microsoft nebo v samostatný soubor PE, která obsahuje jenom manifestu informace o sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-106">The assembly manifest can be stored in either a PE file (an .exe or .dll) with Microsoft intermediate language (MSIL) code or in a standalone PE file that contains only assembly manifest information.</span></span>  
  
 <span data-ttu-id="3c803-107">Následující obrázek znázorňuje, že mohou být uloženy různé způsoby manifest.</span><span class="sxs-lookup"><span data-stu-id="3c803-107">The following illustration shows the different ways the manifest can be stored.</span></span>  
  
 <span data-ttu-id="3c803-108">![Jediný & č. 45; soubor sestavení](../../../docs/framework/app-domains/media/assemblytypes.gif "assemblytypes")</span><span class="sxs-lookup"><span data-stu-id="3c803-108">![A single&#45;file assembly](../../../docs/framework/app-domains/media/assemblytypes.gif "assemblytypes")</span></span>  
<span data-ttu-id="3c803-109">Typy sestavení</span><span class="sxs-lookup"><span data-stu-id="3c803-109">Types of assemblies</span></span>  
  
 <span data-ttu-id="3c803-110">Manifest pro sestavení s jeden přidružený soubor, je součástí souboru PE a vytváří jeden soubor sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-110">For an assembly with one associated file, the manifest is incorporated into the PE file to form a single-file assembly.</span></span> <span data-ttu-id="3c803-111">Vícesouborového sestavení můžete vytvořit samostatný soubor manifestu nebo s manifest začleněná do jednoho ze souborů PE v sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-111">You can create a multifile assembly with a standalone manifest file or with the manifest incorporated into one of the PE files in the assembly.</span></span>  
  
 <span data-ttu-id="3c803-112">Každý manifest sestavení provádí následující funkce:</span><span class="sxs-lookup"><span data-stu-id="3c803-112">Each assembly's manifest performs the following functions:</span></span>  
  
-   <span data-ttu-id="3c803-113">Vytvoří výčet soubory, které tvoří sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-113">Enumerates the files that make up the assembly.</span></span>  
  
-   <span data-ttu-id="3c803-114">Řídí, jak odkazy na sestavení typů a prostředků, mapování na soubory, které obsahují jejich deklarace a implementaci.</span><span class="sxs-lookup"><span data-stu-id="3c803-114">Governs how references to the assembly's types and resources map to the files that contain their declarations and implementations.</span></span>  
  
-   <span data-ttu-id="3c803-115">Vytvoří výčet ostatních sestavení, na kterých závisí sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-115">Enumerates other assemblies on which the assembly depends.</span></span>  
  
-   <span data-ttu-id="3c803-116">Poskytuje úroveň dereference mezi spotřebiteli sestavení a podrobnosti implementace je sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-116">Provides a level of indirection between consumers of the assembly and the assembly's implementation details.</span></span>  
  
-   <span data-ttu-id="3c803-117">Vykreslí sestavení popisující samy sebe.</span><span class="sxs-lookup"><span data-stu-id="3c803-117">Renders the assembly self-describing.</span></span>  
  
## <a name="assembly-manifest-contents"></a><span data-ttu-id="3c803-118">Obsah manifestu sestavení</span><span class="sxs-lookup"><span data-stu-id="3c803-118">Assembly Manifest Contents</span></span>  
 <span data-ttu-id="3c803-119">V následující tabulce jsou uvedeny informace obsažené v manifestu sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-119">The following table shows the information contained in the assembly manifest.</span></span> <span data-ttu-id="3c803-120">První čtyři položky – název sestavení, číslo verze, jazykovou verzi a informace silný název – tvoří identity sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-120">The first four items—the assembly name, version number, culture, and strong name information—make up the assembly's identity.</span></span>  
  
|<span data-ttu-id="3c803-121">Informace o</span><span class="sxs-lookup"><span data-stu-id="3c803-121">Information</span></span>|<span data-ttu-id="3c803-122">Popis</span><span class="sxs-lookup"><span data-stu-id="3c803-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3c803-123">Název sestavení</span><span class="sxs-lookup"><span data-stu-id="3c803-123">Assembly name</span></span>|<span data-ttu-id="3c803-124">Textový řetězec určující název sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-124">A text string specifying the assembly's name.</span></span>|  
|<span data-ttu-id="3c803-125">Číslo verze</span><span class="sxs-lookup"><span data-stu-id="3c803-125">Version number</span></span>|<span data-ttu-id="3c803-126">Hlavní verze a podverze číslo a číslo revize a sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-126">A major and minor version number, and a revision and build number.</span></span> <span data-ttu-id="3c803-127">Modul CLR používá tato čísla k vynucení zásad správy verzí.</span><span class="sxs-lookup"><span data-stu-id="3c803-127">The common language runtime uses these numbers to enforce version policy.</span></span>|  
|<span data-ttu-id="3c803-128">Jazyková verze</span><span class="sxs-lookup"><span data-stu-id="3c803-128">Culture</span></span>|<span data-ttu-id="3c803-129">Informace o jazykové verzi nebo jazyka sestavení podporuje.</span><span class="sxs-lookup"><span data-stu-id="3c803-129">Information on the culture or language the assembly supports.</span></span> <span data-ttu-id="3c803-130">Tyto informace slouží jenom k označení sestavení jako satelitní sestavení obsahující informace o konkrétní jazykové verze nebo jazyk.</span><span class="sxs-lookup"><span data-stu-id="3c803-130">This information should be used only to designate an assembly as a satellite assembly containing culture- or language-specific information.</span></span> <span data-ttu-id="3c803-131">(Sestavení s informací o jazykové verzi se automaticky předpokládá být satelitní sestavení.)</span><span class="sxs-lookup"><span data-stu-id="3c803-131">(An assembly with culture information is automatically assumed to be a satellite assembly.)</span></span>|  
|<span data-ttu-id="3c803-132">Informace o silným názvem</span><span class="sxs-lookup"><span data-stu-id="3c803-132">Strong name information</span></span>|<span data-ttu-id="3c803-133">Veřejný klíč od vydavatele, pokud nebyla zadána sestavení silným názvem.</span><span class="sxs-lookup"><span data-stu-id="3c803-133">The public key from the publisher if the assembly has been given a strong name.</span></span>|  
|<span data-ttu-id="3c803-134">Seznam všech souborů v sestavení</span><span class="sxs-lookup"><span data-stu-id="3c803-134">List of all files in the assembly</span></span>|<span data-ttu-id="3c803-135">Hodnota hash jednotlivých souborů obsažených v sestavení a název souboru.</span><span class="sxs-lookup"><span data-stu-id="3c803-135">A hash of each file contained in the assembly and a file name.</span></span> <span data-ttu-id="3c803-136">Všimněte si, že všechny soubory, které tvoří sestavení musí být ve stejném adresáři jako soubor obsahuje manifest sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-136">Note that all files that make up the assembly must be in the same directory as the file containing the assembly manifest.</span></span>|  
|<span data-ttu-id="3c803-137">Informace o typu odkazu</span><span class="sxs-lookup"><span data-stu-id="3c803-137">Type reference information</span></span>|<span data-ttu-id="3c803-138">Informace slouží k mapování typu odkaz na soubor, který obsahuje jeho deklaraci a implementaci modulem runtime.</span><span class="sxs-lookup"><span data-stu-id="3c803-138">Information used by the runtime to map a type reference to the file that contains its declaration and implementation.</span></span> <span data-ttu-id="3c803-139">Používá se pro typy, které byly exportovány z sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-139">This is used for types that are exported from the assembly.</span></span>|  
|<span data-ttu-id="3c803-140">Informace v odkazovaných sestaveních</span><span class="sxs-lookup"><span data-stu-id="3c803-140">Information on referenced assemblies</span></span>|<span data-ttu-id="3c803-141">Seznam ostatních sestavení, které jsou staticky odkazuje sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-141">A list of other assemblies that are statically referenced by the assembly.</span></span> <span data-ttu-id="3c803-142">Každý odkaz obsahuje název závislého sestavení, metadata sestavení (verze, jazykové verze, operačního systému atd.) a veřejný klíč, pokud je silné název sestavení.</span><span class="sxs-lookup"><span data-stu-id="3c803-142">Each reference includes the dependent assembly's name, assembly metadata (version, culture, operating system, and so on), and public key, if the assembly is strong named.</span></span>|  
  
 <span data-ttu-id="3c803-143">Můžete přidat nebo změnit některé informace v manifestu sestavení pomocí atributů sestavení v kódu.</span><span class="sxs-lookup"><span data-stu-id="3c803-143">You can add or change some information in the assembly manifest by using assembly attributes in your code.</span></span> <span data-ttu-id="3c803-144">Můžete změnit informace o verzi a informační atributů, včetně ochranné známky, Copyright, produktu, společnosti a informační verze.</span><span class="sxs-lookup"><span data-stu-id="3c803-144">You can change version information and informational attributes, including Trademark, Copyright, Product, Company, and Informational Version.</span></span> <span data-ttu-id="3c803-145">Úplný seznam atributů sestavení, najdete v části [nastavení atributů sestavení](../../../docs/framework/app-domains/set-assembly-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="3c803-145">For a complete list of assembly attributes, see [Setting Assembly Attributes](../../../docs/framework/app-domains/set-assembly-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c803-146">Viz také</span><span class="sxs-lookup"><span data-stu-id="3c803-146">See Also</span></span>  
 [<span data-ttu-id="3c803-147">Obsah sestavení</span><span class="sxs-lookup"><span data-stu-id="3c803-147">Assembly Contents</span></span>](../../../docs/framework/app-domains/assembly-contents.md)  
 [<span data-ttu-id="3c803-148">Správa verzí sestavení</span><span class="sxs-lookup"><span data-stu-id="3c803-148">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 [<span data-ttu-id="3c803-149">Vytváření satelitních sestavení</span><span class="sxs-lookup"><span data-stu-id="3c803-149">Creating Satellite Assemblies</span></span>](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)  
 [<span data-ttu-id="3c803-150">Sestavení se silným názvem</span><span class="sxs-lookup"><span data-stu-id="3c803-150">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)