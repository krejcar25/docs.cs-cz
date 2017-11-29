---
title: "Přenositelné a nepřenositelné typy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b05d77df28b560b9236e467a914229c0fa9ae7e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="blittable-and-non-blittable-types"></a><span data-ttu-id="9533a-102">Přenositelné a nepřenositelné typy</span><span class="sxs-lookup"><span data-stu-id="9533a-102">Blittable and Non-Blittable Types</span></span>
<span data-ttu-id="9533a-103">Většina typy dat mají společné reprezentaci v spravované i nespravované paměti a nevyžadují žádná zvláštní zpracování pomocí zprostředkovatele komunikace s objekty vláken.</span><span class="sxs-lookup"><span data-stu-id="9533a-103">Most data types have a common representation in both managed and unmanaged memory and do not require special handling by the interop marshaler.</span></span> <span data-ttu-id="9533a-104">Tyto typy jsou označovány jako *přenositelné typy* vzhledem k tomu, že jsou předávány mezi nevyžadují převodu spravovaných a nespravovaných kódu.</span><span class="sxs-lookup"><span data-stu-id="9533a-104">These types are called *blittable types* because they do not require conversion when they are passed between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="9533a-105">Struktury, které jsou vráceny z platformy vyvolat volání musí být přenositelné typy.</span><span class="sxs-lookup"><span data-stu-id="9533a-105">Structures that are returned from platform invoke calls must be blittable types.</span></span> <span data-ttu-id="9533a-106">Vyvolání platformy nepodporuje nepřenositelné struktury jako návratové typy.</span><span class="sxs-lookup"><span data-stu-id="9533a-106">Platform invoke does not support non-blittable structures as return types.</span></span>  
  
 <span data-ttu-id="9533a-107">Následující typy z <xref:System> obor názvů jsou přenositelné typy:</span><span class="sxs-lookup"><span data-stu-id="9533a-107">The following types from the <xref:System> namespace are blittable types:</span></span>  
  
-   <xref:System.Byte?displayProperty=nameWithType>  
  
-   <xref:System.SByte?displayProperty=nameWithType>  
  
-   <xref:System.Int16?displayProperty=nameWithType>  
  
-   <xref:System.UInt16?displayProperty=nameWithType>  
  
-   <xref:System.Int32?displayProperty=nameWithType>  
  
-   <xref:System.UInt32?displayProperty=nameWithType>  
  
-   <xref:System.Int64?displayProperty=nameWithType>  
  
-   <xref:System.UInt64?displayProperty=nameWithType>  
  
-   <xref:System.IntPtr?displayProperty=nameWithType>  
  
-   <xref:System.UIntPtr?displayProperty=nameWithType>  
  
-   <xref:System.Single?displayProperty=nameWithType>  
  
-   <xref:System.Double?displayProperty=nameWithType>  
  
 <span data-ttu-id="9533a-108">Přenositelné typy jsou také následující komplexní typy:</span><span class="sxs-lookup"><span data-stu-id="9533a-108">The following complex types are also blittable types:</span></span>  
  
-   <span data-ttu-id="9533a-109">Jednorozměrná pole přenositelné typy, jako je například pole celých čísel.</span><span class="sxs-lookup"><span data-stu-id="9533a-109">One-dimensional arrays of blittable types, such as an array of integers.</span></span> <span data-ttu-id="9533a-110">Typ, který obsahuje proměnné pole přenositelné typy není však samotné přenositelné.</span><span class="sxs-lookup"><span data-stu-id="9533a-110">However, a type that contains a variable array of blittable types is not itself blittable.</span></span>  
  
-   <span data-ttu-id="9533a-111">Formátovaná hodnota typů, které obsahují pouze přenositelné typy (a třídy, pokud jsou zařazené jako formátovaný typy).</span><span class="sxs-lookup"><span data-stu-id="9533a-111">Formatted value types that contain only blittable types (and classes if they are marshaled as formatted types).</span></span> <span data-ttu-id="9533a-112">Další informace o typech formátovanou hodnotu najdete v tématu [výchozí zařazování pro typy hodnot](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a).</span><span class="sxs-lookup"><span data-stu-id="9533a-112">For more information about formatted value types, see [Default Marshaling for Value Types](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a).</span></span>  
  
 <span data-ttu-id="9533a-113">Odkazy na objekty nejsou typu blittable.</span><span class="sxs-lookup"><span data-stu-id="9533a-113">Object references are not blittable.</span></span> <span data-ttu-id="9533a-114">To zahrnuje pole odkazy na objekty, které jsou přenositelné samy o sobě.</span><span class="sxs-lookup"><span data-stu-id="9533a-114">This includes an array of references to objects that are blittable by themselves.</span></span> <span data-ttu-id="9533a-115">Například můžete definovat strukturu, která je typu blittable, ale nelze definovat typu blittable, který obsahuje řadu odkazů na tyto struktury.</span><span class="sxs-lookup"><span data-stu-id="9533a-115">For example, you can define a structure that is blittable, but you cannot define a blittable type that contains an array of references to those structures.</span></span>  
  
 <span data-ttu-id="9533a-116">Jako optimalizace, pole přenositelné typy a tříd, které obsahují pouze přenositelné členové jsou [připnutý](../../../docs/framework/interop/copying-and-pinning.md) místo zkopírovaných při zařazování.</span><span class="sxs-lookup"><span data-stu-id="9533a-116">As an optimization, arrays of blittable types and classes that contain only blittable members are [pinned](../../../docs/framework/interop/copying-and-pinning.md) instead of copied during marshaling.</span></span> <span data-ttu-id="9533a-117">Tyto typy se může zobrazit být zařazena jako vstupně -výstupní parametry, pokud jsou volající a volaný ve stejném typu apartment.</span><span class="sxs-lookup"><span data-stu-id="9533a-117">These types can appear to be marshaled as In/Out parameters when the caller and callee are in the same apartment.</span></span> <span data-ttu-id="9533a-118">Ale tyto typy jsou ve skutečnosti zařazené jako parametry, a je nutné použít <xref:System.Runtime.InteropServices.InAttribute> a <xref:System.Runtime.InteropServices.OutAttribute> atributy, pokud chcete zařazování argument jako ve vstupně -výstupnímu parametru.</span><span class="sxs-lookup"><span data-stu-id="9533a-118">However, these types are actually marshaled as In parameters, and you must apply the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes if you want to marshal the argument as an In/Out parameter.</span></span>  
  
 <span data-ttu-id="9533a-119">Některé spravované datové typy vyžadují různé reprezentace v nespravované prostředí.</span><span class="sxs-lookup"><span data-stu-id="9533a-119">Some managed data types require a different representation in an unmanaged environment.</span></span> <span data-ttu-id="9533a-120">Tyto datové typy nepřenositelné musí být převedeny na formulář, který může být zařazen.</span><span class="sxs-lookup"><span data-stu-id="9533a-120">These non-blittable data types must be converted into a form that can be marshaled.</span></span> <span data-ttu-id="9533a-121">Například spravované řetězce jsou nepřenositelné typy, protože se musí před převést do řetězce objekty může být zařazeno.</span><span class="sxs-lookup"><span data-stu-id="9533a-121">For example, managed strings are non-blittable types because they must be converted into string objects before they can be marshaled.</span></span>  
  
 <span data-ttu-id="9533a-122">Následující tabulka uvádí nepřenositelné typy z <xref:System> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="9533a-122">The following table lists non-blittable types from the <xref:System> namespace.</span></span> <span data-ttu-id="9533a-123">[Delegáti](http://msdn.microsoft.com/en-us/d176ee76-f982-494b-b03d-92e4118896e2), které jsou datové struktury, které odkazují na statickou metodu nebo instanci třídy jsou také nepřenositelné.</span><span class="sxs-lookup"><span data-stu-id="9533a-123">[Delegates](http://msdn.microsoft.com/en-us/d176ee76-f982-494b-b03d-92e4118896e2), which are data structures that refer to a static method or to a class instance, are also non-blittable.</span></span>  
  
|<span data-ttu-id="9533a-124">Přenositelné bez typu</span><span class="sxs-lookup"><span data-stu-id="9533a-124">Non-blittable type</span></span>|<span data-ttu-id="9533a-125">Popis</span><span class="sxs-lookup"><span data-stu-id="9533a-125">Description</span></span>|  
|-------------------------|-----------------|  
|[<span data-ttu-id="9533a-126">System.Array</span><span class="sxs-lookup"><span data-stu-id="9533a-126">System.Array</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="9533a-127">Převede pole stylu jazyka C nebo `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="9533a-127">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="9533a-128">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="9533a-128">System.Boolean</span></span>](http://msdn.microsoft.com/en-us/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|<span data-ttu-id="9533a-129">Převede na 1, 2 nebo 4 bajtů hodnotu s `true` -1 nebo 1.</span><span class="sxs-lookup"><span data-stu-id="9533a-129">Converts to a 1, 2, or 4-byte value with `true` as 1 or -1.</span></span>|  
|[<span data-ttu-id="9533a-130">System.Char</span><span class="sxs-lookup"><span data-stu-id="9533a-130">System.Char</span></span>](http://msdn.microsoft.com/en-us/cecc87c1-075e-4cde-aa56-33d189f66feb)|<span data-ttu-id="9533a-131">Převede na znak Unicode nebo ANSI.</span><span class="sxs-lookup"><span data-stu-id="9533a-131">Converts to a Unicode or ANSI character.</span></span>|  
|[<span data-ttu-id="9533a-132">System.Class</span><span class="sxs-lookup"><span data-stu-id="9533a-132">System.Class</span></span>](http://msdn.microsoft.com/en-us/fe334af5-0123-43d8-be84-26f6f023ddb6)|<span data-ttu-id="9533a-133">Převede na třídu rozhraní.</span><span class="sxs-lookup"><span data-stu-id="9533a-133">Converts to a class interface.</span></span>|  
|[<span data-ttu-id="9533a-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="9533a-134">System.Object</span></span>](../../../docs/framework/interop/default-marshaling-for-objects.md)|<span data-ttu-id="9533a-135">Převede hodnotu typu variant nebo rozhraní.</span><span class="sxs-lookup"><span data-stu-id="9533a-135">Converts to a variant or an interface.</span></span>|  
|[<span data-ttu-id="9533a-136">System.Mdarray</span><span class="sxs-lookup"><span data-stu-id="9533a-136">System.Mdarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="9533a-137">Převede pole stylu jazyka C nebo `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="9533a-137">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="9533a-138">System.String</span><span class="sxs-lookup"><span data-stu-id="9533a-138">System.String</span></span>](../../../docs/framework/interop/default-marshaling-for-strings.md)|<span data-ttu-id="9533a-139">Převede řetězec ukončuje v odkaz s hodnotou null nebo BSTR.</span><span class="sxs-lookup"><span data-stu-id="9533a-139">Converts to a string terminating in a null reference or to a BSTR.</span></span>|  
|[<span data-ttu-id="9533a-140">Typ System.Valuetype</span><span class="sxs-lookup"><span data-stu-id="9533a-140">System.Valuetype</span></span>](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a)|<span data-ttu-id="9533a-141">Převede na struktura s pevnou paměti rozložení.</span><span class="sxs-lookup"><span data-stu-id="9533a-141">Converts to a structure with a fixed memory layout.</span></span>|  
|[<span data-ttu-id="9533a-142">System.Szarray</span><span class="sxs-lookup"><span data-stu-id="9533a-142">System.Szarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="9533a-143">Převede pole stylu jazyka C nebo `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="9533a-143">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
  
 <span data-ttu-id="9533a-144">Typy tříd a objektů jsou podporovány pouze zprostředkovatel komunikace s objekty COM.</span><span class="sxs-lookup"><span data-stu-id="9533a-144">Class and object types are supported only by COM interop.</span></span> <span data-ttu-id="9533a-145">Pro odpovídající typy v [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# a C++, najdete [– přehled knihovny tříd](../../../docs/standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9533a-145">For corresponding types in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++, see the [Class Library Overview](../../../docs/standard/class-library-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9533a-146">Viz také</span><span class="sxs-lookup"><span data-stu-id="9533a-146">See Also</span></span>  
 [<span data-ttu-id="9533a-147">Výchozí chování zařazování</span><span class="sxs-lookup"><span data-stu-id="9533a-147">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)