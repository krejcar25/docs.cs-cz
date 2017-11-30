---
title: Element &lt;Namespace&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 014dc690d034c27f0f004172fb8108249bb5c89b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltnamespacegt-element-net-native"></a><span data-ttu-id="42192-102">Element &lt;Namespace&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="42192-102">&lt;Namespace&gt; Element (.NET Native)</span></span>
<span data-ttu-id="42192-103">Modul runtime reflexe zásad platí pro všechny typy v určeném oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="42192-103">Applies runtime reflection policy to all the types in a specified namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42192-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="42192-104">Syntax</span></span>  
  
```xml  
<Namespace Name="namespace_name"   
           Activate="policy_type"   
           Browse="policy_type" />  
           Dynamic="policy_setting"  
           Serialize="policy_setting"  
           DataContractSerializer="policy_setting"  
           DataContractJsonSerializer="policy_setting"  
           XmlSerializer="policy_setting"  
           MarshalObject="policy_setting"  
           MarshalDelegate="policy_setting"  
           MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42192-105">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="42192-105">Attributes and Elements</span></span>  
 <span data-ttu-id="42192-106">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="42192-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42192-107">Atributy</span><span class="sxs-lookup"><span data-stu-id="42192-107">Attributes</span></span>  
  
|<span data-ttu-id="42192-108">Atribut</span><span class="sxs-lookup"><span data-stu-id="42192-108">Attribute</span></span>|<span data-ttu-id="42192-109">Typ atributu</span><span class="sxs-lookup"><span data-stu-id="42192-109">Attribute type</span></span>|<span data-ttu-id="42192-110">Popis</span><span class="sxs-lookup"><span data-stu-id="42192-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="42192-111">Obecné</span><span class="sxs-lookup"><span data-stu-id="42192-111">General</span></span>|<span data-ttu-id="42192-112">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-112">Required attribute.</span></span> <span data-ttu-id="42192-113">Určuje název oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="42192-113">Specifies the name of the namespace.</span></span>|  
|`Activate`|<span data-ttu-id="42192-114">Reflexe</span><span class="sxs-lookup"><span data-stu-id="42192-114">Reflection</span></span>|<span data-ttu-id="42192-115">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-115">Optional attribute.</span></span> <span data-ttu-id="42192-116">Ovládací prvky runtime přístup k konstruktory povolit aktivace instancí.</span><span class="sxs-lookup"><span data-stu-id="42192-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="42192-117">Reflexe</span><span class="sxs-lookup"><span data-stu-id="42192-117">Reflection</span></span>|<span data-ttu-id="42192-118">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-118">Optional attribute.</span></span> <span data-ttu-id="42192-119">Ovládací prvky dotazování na informace o programu elementů, ale nepovolí žádné přístup k modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="42192-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="42192-120">Reflexe</span><span class="sxs-lookup"><span data-stu-id="42192-120">Reflection</span></span>|<span data-ttu-id="42192-121">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-121">Optional attribute.</span></span> <span data-ttu-id="42192-122">Řídí přístup k modulu runtime pro všechny členy typu, včetně konstruktory, metody, polí, vlastnosti a události, chcete-li povolit dynamické programování.</span><span class="sxs-lookup"><span data-stu-id="42192-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="42192-123">Serializace</span><span class="sxs-lookup"><span data-stu-id="42192-123">Serialization</span></span>|<span data-ttu-id="42192-124">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-124">Optional attribute.</span></span> <span data-ttu-id="42192-125">Ovládací prvky runtime přístup k konstruktory, pole a vlastnosti, aby instance typu serializovat a deserializovat pomocí knihovny například serializátor Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="42192-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="42192-126">Serializace</span><span class="sxs-lookup"><span data-stu-id="42192-126">Serialization</span></span>|<span data-ttu-id="42192-127">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-127">Optional attribute.</span></span> <span data-ttu-id="42192-128">Zásady pro serializaci, který používá ovládací prvky <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="42192-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="42192-129">Serializace</span><span class="sxs-lookup"><span data-stu-id="42192-129">Serialization</span></span>|<span data-ttu-id="42192-130">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-130">Optional attribute.</span></span> <span data-ttu-id="42192-131">Zásady pro serializaci JSON, který používá ovládací prvky <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="42192-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="42192-132">Serializace</span><span class="sxs-lookup"><span data-stu-id="42192-132">Serialization</span></span>|<span data-ttu-id="42192-133">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-133">Optional attribute.</span></span> <span data-ttu-id="42192-134">Zásady pro serializaci XML, který používá ovládací prvky <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="42192-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="42192-135">Zprostředkovatel komunikace s objekty</span><span class="sxs-lookup"><span data-stu-id="42192-135">Interop</span></span>|<span data-ttu-id="42192-136">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-136">Optional attribute.</span></span> <span data-ttu-id="42192-137">Ovládací prvky zásady pro zařazování odkazové typy prostředí Windows Runtime a COM.</span><span class="sxs-lookup"><span data-stu-id="42192-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="42192-138">Zprostředkovatel komunikace s objekty</span><span class="sxs-lookup"><span data-stu-id="42192-138">Interop</span></span>|<span data-ttu-id="42192-139">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-139">Optional attribute.</span></span> <span data-ttu-id="42192-140">Ovládací prvky zásady pro zařazování delegáta typy jako ukazatelů na funkce do nativního kódu.</span><span class="sxs-lookup"><span data-stu-id="42192-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="42192-141">Zprostředkovatel komunikace s objekty</span><span class="sxs-lookup"><span data-stu-id="42192-141">Interop</span></span>|<span data-ttu-id="42192-142">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="42192-142">Optional attribute.</span></span> <span data-ttu-id="42192-143">Ovládací prvky zásady pro zařazování struktur nativního kódu.</span><span class="sxs-lookup"><span data-stu-id="42192-143">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="42192-144">Atribut Name.</span><span class="sxs-lookup"><span data-stu-id="42192-144">Name attribute</span></span>  
  
|<span data-ttu-id="42192-145">Hodnota</span><span class="sxs-lookup"><span data-stu-id="42192-145">Value</span></span>|<span data-ttu-id="42192-146">Popis</span><span class="sxs-lookup"><span data-stu-id="42192-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="42192-147">*namespace_name*</span><span class="sxs-lookup"><span data-stu-id="42192-147">*namespace_name*</span></span>|<span data-ttu-id="42192-148">Název oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="42192-148">The namespace name.</span></span> <span data-ttu-id="42192-149">Pokud \<Namespace > elementu je podřízená [ \<aplikace >](../../../docs/framework/net-native/application-element-net-native.md), [ \<Knihovna >](../../../docs/framework/net-native/library-element-net-native.md), nebo [ \<sestavení >](../../../docs/framework/net-native/assembly-element-net-native.md) elementu *namespace_name* musí být obor názvů plně kvalifikovaný název.</span><span class="sxs-lookup"><span data-stu-id="42192-149">If the \<Namespace> element is a child of an [\<Application>](../../../docs/framework/net-native/application-element-net-native.md), [\<Library>](../../../docs/framework/net-native/library-element-net-native.md), or [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) element, *namespace_name* must be a fully qualified namespace name.</span></span> <span data-ttu-id="42192-150">Pokud \<Namespace > elementu je podřízená jiné \<Namespace > elementu *namespace_name* musí být název relativní oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="42192-150">If the \<Namespace> element is a child of another \<Namespace> element, *namespace_name* must be a relative namespace name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="42192-151">Všechny ostatní atributy</span><span class="sxs-lookup"><span data-stu-id="42192-151">All other attributes</span></span>  
  
|<span data-ttu-id="42192-152">Hodnota</span><span class="sxs-lookup"><span data-stu-id="42192-152">Value</span></span>|<span data-ttu-id="42192-153">Popis</span><span class="sxs-lookup"><span data-stu-id="42192-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="42192-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="42192-154">*policy_setting*</span></span>|<span data-ttu-id="42192-155">Nastavení, které chcete použít pro tento typ zásad pro všechny typy v oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="42192-155">The setting to apply to this policy type for all types in the namespace.</span></span> <span data-ttu-id="42192-156">Možné hodnoty jsou `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, a `Required All`.</span><span class="sxs-lookup"><span data-stu-id="42192-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="42192-157">Další informace najdete v tématu [nastavení zásad direktivy modulu Runtime](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="42192-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42192-158">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="42192-158">Child Elements</span></span>  
  
|<span data-ttu-id="42192-159">Prvek</span><span class="sxs-lookup"><span data-stu-id="42192-159">Element</span></span>|<span data-ttu-id="42192-160">Popis</span><span class="sxs-lookup"><span data-stu-id="42192-160">Description</span></span>|  
|-------------|-----------------|  
|`<Namespace>`|<span data-ttu-id="42192-161">Platí pro všechny typy v oboru názvů nadřazené zásady reflexe modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="42192-161">Applies runtime reflection policy to all types in a parent namespace.</span></span>|  
|[<span data-ttu-id="42192-162">\<Typ ></span><span class="sxs-lookup"><span data-stu-id="42192-162">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="42192-163">Reflexe zásada se vztahuje na typ.</span><span class="sxs-lookup"><span data-stu-id="42192-163">Applies reflection policy to a type.</span></span>|  
|[<span data-ttu-id="42192-164">\<TypeInstantiation ></span><span class="sxs-lookup"><span data-stu-id="42192-164">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="42192-165">Reflexe zásada se vztahuje na vytvořený obecného typu.</span><span class="sxs-lookup"><span data-stu-id="42192-165">Applies reflection policy to a constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42192-166">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="42192-166">Parent Elements</span></span>  
  
|<span data-ttu-id="42192-167">Prvek</span><span class="sxs-lookup"><span data-stu-id="42192-167">Element</span></span>|<span data-ttu-id="42192-168">Popis</span><span class="sxs-lookup"><span data-stu-id="42192-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42192-169">\<Aplikace ></span><span class="sxs-lookup"><span data-stu-id="42192-169">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="42192-170">Slouží jako kontejner pro celou aplikaci typy a členy typu jejichž metadata jsou k dispozici pro reflexi za běhu.</span><span class="sxs-lookup"><span data-stu-id="42192-170">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="42192-171">[ \<Aplikace >](../../../docs/framework/net-native/application-element-net-native.md) element může obsahovat nula, jednu nebo více [ \<sestavení >](../../../docs/framework/net-native/assembly-element-net-native.md) elementy.</span><span class="sxs-lookup"><span data-stu-id="42192-171">The [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element can have zero, one, or more [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) elements.</span></span>|  
|[<span data-ttu-id="42192-172">\<Sestavení ></span><span class="sxs-lookup"><span data-stu-id="42192-172">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="42192-173">Modul runtime reflexe zásad platí pro všechny typy v zadaném sestavení.</span><span class="sxs-lookup"><span data-stu-id="42192-173">Applies runtime reflection policy to all the types in a specified assembly.</span></span>|  
|[<span data-ttu-id="42192-174">\<Knihovna ></span><span class="sxs-lookup"><span data-stu-id="42192-174">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="42192-175">Definuje sestavení, které obsahuje typy a členy typu jejichž metadata jsou k dispozici pro reflexi za běhu.</span><span class="sxs-lookup"><span data-stu-id="42192-175">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="42192-176">[ \<Knihovna >](../../../docs/framework/net-native/library-element-net-native.md) element může obsahovat nula nebo jedna [ \<sestavení >](../../../docs/framework/net-native/assembly-element-net-native.md) element.</span><span class="sxs-lookup"><span data-stu-id="42192-176">The [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) element can have zero or one [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) element.</span></span>|  
|`<Namespace>`|<span data-ttu-id="42192-177">Reflexe zásad platí pro všechny typy v oboru názvů nadřazené.</span><span class="sxs-lookup"><span data-stu-id="42192-177">Applies reflection policy to all types in a parent namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42192-178">Poznámky</span><span class="sxs-lookup"><span data-stu-id="42192-178">Remarks</span></span>  
 <span data-ttu-id="42192-179">`Activate`, `Browse`, `Dynamic`, A `Serialize` atributy jsou nepovinné.</span><span class="sxs-lookup"><span data-stu-id="42192-179">The `Activate`, `Browse`, `Dynamic`, and `Serialize` attributes are all optional.</span></span> <span data-ttu-id="42192-180">Pokud žádný není přítomen `<Namespace>` element slouží pouze jako kontejner pro podřízené elementy.</span><span class="sxs-lookup"><span data-stu-id="42192-180">If none are present, the `<Namespace>` element serves only as a container for child elements.</span></span> <span data-ttu-id="42192-181">Pokud jsou přítomna, `<Namespace>` element platí zásady reflexe modulu runtime pro všechny typy v určeném oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="42192-181">If they are present, the `<Namespace>` element applies runtime reflection policy to all the types in the specified namespace.</span></span>  
  
 <span data-ttu-id="42192-182">Pokud je podřízený [ \<sestavení >](../../../docs/framework/net-native/assembly-element-net-native.md) elementu, `<Namespace>` element přednost před zásadami reflexe runtime definované [ \<sestavení >](../../../docs/framework/net-native/assembly-element-net-native.md) element.</span><span class="sxs-lookup"><span data-stu-id="42192-182">When it is a child of the [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) element, the `<Namespace>` element overrides the runtime reflection policy defined by the  [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42192-183">Viz také</span><span class="sxs-lookup"><span data-stu-id="42192-183">See Also</span></span>  
 [<span data-ttu-id="42192-184">Nastavení zásad direktivy modulu runtime</span><span class="sxs-lookup"><span data-stu-id="42192-184">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="42192-185">Odkaz na soubor konfigurace modulu runtime direktivy (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="42192-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="42192-186">Elementy direktivy modulu runtime</span><span class="sxs-lookup"><span data-stu-id="42192-186">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)