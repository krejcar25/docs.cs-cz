---
title: "Převaděče typů a rozšíření značek pro jazyk XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], type converter services
- XAML [XAML Services], value converters
- XAML [XAML Services], markup extension services
- value converters for XAML [XAML Services]
- XAML [XAML Services], service context
ms.assetid: db07a952-05ce-4aa4-b6f9-aac7397d0326
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 149f293616cfc2aa7b68377964c14a7cfa9e3edf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="type-converters-and-markup-extensions-for-xaml"></a><span data-ttu-id="9b173-102">Převaděče typů a rozšíření značek pro jazyk XAML</span><span class="sxs-lookup"><span data-stu-id="9b173-102">Type Converters and Markup Extensions for XAML</span></span>
<span data-ttu-id="9b173-103">Převaděče typů a rozšíření značek jsou dvě techniky, které systémy typ jazyka XAML a XAML zapisovače použít ke generování součásti grafu objektu.</span><span class="sxs-lookup"><span data-stu-id="9b173-103">Type converters and markup extensions are two techniques that XAML type systems and XAML writers use to generate object graph components.</span></span> <span data-ttu-id="9b173-104">I když některé vlastnosti sdílejí, převaděče typů a rozšíření značek jsou reprezentované jinak v datový proud uzlu XAML.</span><span class="sxs-lookup"><span data-stu-id="9b173-104">Although they share some characteristics, type converters and markup extensions are represented differently in a XAML node stream.</span></span> <span data-ttu-id="9b173-105">V této dokumentaci sady, převaděčů typů, rozšíření značek a podobné konstrukce jsou někdy souhrnně označovány jako převodníky hodnot.</span><span class="sxs-lookup"><span data-stu-id="9b173-105">In this documentation set, type converters, markup extensions, and similar constructs are sometimes collectively referred to as value converters.</span></span>  
  
<a name="value_converters"></a>   
## <a name="value-converters"></a><span data-ttu-id="9b173-106">Převodníky hodnot</span><span class="sxs-lookup"><span data-stu-id="9b173-106">Value Converters</span></span>  
 <span data-ttu-id="9b173-107">V jazyce XAML se používají převodníky hodnot pro různé scénáře.</span><span class="sxs-lookup"><span data-stu-id="9b173-107">In XAML, value converters are used for various scenarios.</span></span> <span data-ttu-id="9b173-108">Následující seznam obsahuje různé typy převodníky hodnot v jazyce XAML:</span><span class="sxs-lookup"><span data-stu-id="9b173-108">The following list shows the different types of value converters in XAML:</span></span>  
  
-   <span data-ttu-id="9b173-109">převaděče typů</span><span class="sxs-lookup"><span data-stu-id="9b173-109">Type converter</span></span>  
  
-   <span data-ttu-id="9b173-110">– Rozšíření značek</span><span class="sxs-lookup"><span data-stu-id="9b173-110">Markup extension</span></span>  
  
-   <span data-ttu-id="9b173-111">Serializátor hodnota</span><span class="sxs-lookup"><span data-stu-id="9b173-111">Value serializer</span></span>  
  
-   <span data-ttu-id="9b173-112">Související nebo podporu třída, která poskytuje logiku pro textových syntaxi jazyka XAML</span><span class="sxs-lookup"><span data-stu-id="9b173-112">Related class or support class that provides the logic for a XAML text syntax</span></span>  
  
<a name="type_converters"></a>   
## <a name="type-converters"></a><span data-ttu-id="9b173-113">Převaděče typů</span><span class="sxs-lookup"><span data-stu-id="9b173-113">Type Converters</span></span>  
 <span data-ttu-id="9b173-114">V definici rozhraní .NET Framework XAML Services převaděče typů jsou třídy, které jsou odvozeny od CLR <xref:System.ComponentModel.TypeConverter> třídy.</span><span class="sxs-lookup"><span data-stu-id="9b173-114">In the .NET Framework XAML Services definition, type converters are classes that derive from the CLR <xref:System.ComponentModel.TypeConverter> class.</span></span> <span data-ttu-id="9b173-115"><xref:System.ComponentModel.TypeConverter>je třída, která byla v [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] dříve, než vznikla XAML.</span><span class="sxs-lookup"><span data-stu-id="9b173-115"><xref:System.ComponentModel.TypeConverter> is a class that was in the [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] before XAML existed.</span></span> <span data-ttu-id="9b173-116">Původnímu účelu se na podporu vlastnost windows a podobné úpravy metaphors založený na textu plody pro [!INCLUDE[TLA2#tla_ide](../../../includes/tla2sharptla-ide-md.md)] vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="9b173-116">Its original purpose was to support property windows and similar text-based editing metaphors for [!INCLUDE[TLA2#tla_ide](../../../includes/tla2sharptla-ide-md.md)] properties.</span></span> <span data-ttu-id="9b173-117">Zavedení XAML do rozhraní .NET Framework používá <xref:System.ComponentModel.TypeConverter> převést na objekt textových syntaxi (jak se nachází v hodnotě atributu nebo hodnotu uzlu XAML).</span><span class="sxs-lookup"><span data-stu-id="9b173-117">The introduction of XAML to .NET Framework uses <xref:System.ComponentModel.TypeConverter> to convert a text syntax (as found in an attribute value or a XAML value node) into an object.</span></span> <span data-ttu-id="9b173-118"><xref:System.ComponentModel.TypeConverter>Můžete také použít k serializaci hodnotu objektu na text syntaxe.</span><span class="sxs-lookup"><span data-stu-id="9b173-118"><xref:System.ComponentModel.TypeConverter> can also be used to serialize an object value to text syntax.</span></span> <span data-ttu-id="9b173-119"><xref:System.ComponentModel.TypeConverter>byla také použita v předchozích implementacích XAML konkrétní rozhraní v [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] a [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b173-119"><xref:System.ComponentModel.TypeConverter> was also used in previous framework-specific XAML implementations in [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] and [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)].</span></span> <span data-ttu-id="9b173-120">Další informace o <xref:System.ComponentModel.TypeConverter> v jazyce XAML, najdete v části [převaděčů typů pro jazyk XAML přehled](../../../docs/framework/xaml-services/type-converters-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9b173-120">For more information about the <xref:System.ComponentModel.TypeConverter> in XAML, see [Type Converters for XAML Overview](../../../docs/framework/xaml-services/type-converters-for-xaml-overview.md).</span></span>  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a><span data-ttu-id="9b173-121">Rozšíření značek</span><span class="sxs-lookup"><span data-stu-id="9b173-121">Markup Extensions</span></span>  
 <span data-ttu-id="9b173-122">Implementace rozhraní .NET Framework XAML Services rozšíření značek jsou třídy, které jsou odvozeny od <xref:System.Windows.Markup.MarkupExtension> třídy.</span><span class="sxs-lookup"><span data-stu-id="9b173-122">In the .NET Framework XAML Services implementation, markup extensions are classes that derive from the <xref:System.Windows.Markup.MarkupExtension> class.</span></span> <span data-ttu-id="9b173-123">Rozšíření značek jsou pojem, který v tomto formuláři je vytvořena podle jazyka XAML.</span><span class="sxs-lookup"><span data-stu-id="9b173-123">Markup extensions are a concept that in this form is originated by the XAML language.</span></span> <span data-ttu-id="9b173-124">Si můžete představit rozšíření značek, že je něco podobného jako extensible řídicí sekvencí, který zavolá třídu služby zajistit svou logikou.</span><span class="sxs-lookup"><span data-stu-id="9b173-124">You can think of a markup extension as being something like an extensible escape sequence that calls into a service class to provide its logic.</span></span> <span data-ttu-id="9b173-125">Z hlediska značek procesory XAML všeobecně rozpoznat rozšíření značek pořadí text, který začíná žádná levá složená závorka ({}) v textovém řetězci.</span><span class="sxs-lookup"><span data-stu-id="9b173-125">In terms of markup, XAML processors universally recognize a markup extension by a text sequence that starts with an opening brace ({) in a text string.</span></span>  
  
 <span data-ttu-id="9b173-126">Rozšíření značek se liší od převaděče typů.</span><span class="sxs-lookup"><span data-stu-id="9b173-126">Markup extensions differ from type converters.</span></span> <span data-ttu-id="9b173-127">Převaděče typů jsou obvykle spojené s typy nebo členy.</span><span class="sxs-lookup"><span data-stu-id="9b173-127">Type converters are typically associated with types or members.</span></span> <span data-ttu-id="9b173-128">Jsou vyvolány když vytvoření grafu objektu nebo serializace zaznamená syntaxe text, který je přidružen tyto entity.</span><span class="sxs-lookup"><span data-stu-id="9b173-128">They are invoked when an object graph creation or a serialization encounters text syntax that is associated with those entities.</span></span>  
  
 <span data-ttu-id="9b173-129">Rozšíření značek jsou spojeny s třídou, jeden podpůrné služby, ale můžete použít pro žádnou hodnotu člena.</span><span class="sxs-lookup"><span data-stu-id="9b173-129">Markup extensions are associated with a single supporting service class, but can be applied for any member value.</span></span> <span data-ttu-id="9b173-130">(Můžete ale implementovat vaše – rozšíření značek úmyslně omezení jeho použití na některé členy nebo cílové typy pomocí kontext služby.) Rozšíření značek můžete přepsat přidružení převaděče typu.</span><span class="sxs-lookup"><span data-stu-id="9b173-130">(However, you can implement your markup extension to deliberately restrict its use to certain members or destination types, by using service context.) Markup extensions can override a type converter association.</span></span> <span data-ttu-id="9b173-131">Nebo je můžete zadat hodnotu atributu pro členy, které by jinak podporují textových syntaxi.</span><span class="sxs-lookup"><span data-stu-id="9b173-131">Or you can use them to specify an attribute value for members that would not otherwise support a text syntax.</span></span>  
  
 <span data-ttu-id="9b173-132">Další informace o implementaci vzoru rozšíření značek pro jazyk XAML najdete v tématu [XAML přehled rozšíření značek pro](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9b173-132">For more information about the markup extension implementation pattern for XAML, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b173-133"><xref:System.Windows.Markup.MarkupExtension> a <xref:System.Windows.Markup.ValueSerializer> typy jsou oba seznamy v <xref:System.Windows.Markup> obor názvů a nikoli v <xref:System.Xaml> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="9b173-133">The <xref:System.Windows.Markup.MarkupExtension> and <xref:System.Windows.Markup.ValueSerializer> types are both in the <xref:System.Windows.Markup> namespace and not in the <xref:System.Xaml> namespace.</span></span> <span data-ttu-id="9b173-134">To neznamená, že tyto typy jsou specifické pro buď WPF nebo [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] technologie, které jinak naplnit CLR obory názvů, které obsahují řetězec `Windows`.</span><span class="sxs-lookup"><span data-stu-id="9b173-134">This does not imply that these types are specific to either the WPF or [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] technologies that otherwise populate CLR namespaces that contain the string `Windows`.</span></span> <span data-ttu-id="9b173-135"><xref:System.Windows.Markup.MarkupExtension>a <xref:System.Windows.Markup.ValueSerializer> jsou v sestavení System.Xaml a mít žádné konkrétní framework závislostí.</span><span class="sxs-lookup"><span data-stu-id="9b173-135"><xref:System.Windows.Markup.MarkupExtension> and <xref:System.Windows.Markup.ValueSerializer> are in the System.Xaml assembly and have no specific framework dependency.</span></span> <span data-ttu-id="9b173-136">Tyto typy existovalo v oboru názvů CLR pro [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] a zůstanou v oboru názvů CLR v [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] předejdete nejnovější odkazy ve existující projekty WPF.</span><span class="sxs-lookup"><span data-stu-id="9b173-136">These types existed in the CLR namespace for [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] and remain in the CLR namespace in [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] to avoid breaking references in existing WPF projects.</span></span> <span data-ttu-id="9b173-137">Další informace najdete v tématu [typy migrované z grafického subsystému WPF do oboru názvů System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="9b173-137">For more information, see [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md).</span></span>  
  
<a name="value_serializers"></a>   
## <a name="value-serializers"></a><span data-ttu-id="9b173-138">Hodnota Serializátorů</span><span class="sxs-lookup"><span data-stu-id="9b173-138">Value Serializers</span></span>  
 <span data-ttu-id="9b173-139">A <xref:System.Windows.Markup.ValueSerializer> se speciálním typem převaděč, která je optimalizovaná pro převod objekt na řetězec.</span><span class="sxs-lookup"><span data-stu-id="9b173-139">A <xref:System.Windows.Markup.ValueSerializer> is a specialized type converter that is optimized for converting an object to a string.</span></span> <span data-ttu-id="9b173-140">A <xref:System.Windows.Markup.ValueSerializer> pro XAML nemusí implementovat `ConvertFrom` metoda vůbec.</span><span class="sxs-lookup"><span data-stu-id="9b173-140">A <xref:System.Windows.Markup.ValueSerializer> for XAML might not implement the `ConvertFrom` method at all.</span></span> <span data-ttu-id="9b173-141">A <xref:System.Windows.Markup.ValueSerializer> získá služby způsobem, který je stejná jako implementace <xref:System.ComponentModel.TypeConverter> implementace.</span><span class="sxs-lookup"><span data-stu-id="9b173-141">A <xref:System.Windows.Markup.ValueSerializer> implementation obtains services in a manner that is like a <xref:System.ComponentModel.TypeConverter> implementation.</span></span> <span data-ttu-id="9b173-142">Virtuální metody poskytují vstup `context` parametr.</span><span class="sxs-lookup"><span data-stu-id="9b173-142">The virtual methods provide an input `context` parameter.</span></span> <span data-ttu-id="9b173-143">`context` Parametr je typu <xref:System.Windows.Markup.IValueSerializerContext>, který dědí z <xref:System.IServiceProvider> rozhraní a má <xref:System.IServiceProvider.GetService%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="9b173-143">The `context` parameter is of type <xref:System.Windows.Markup.IValueSerializerContext>, which inherits from the <xref:System.IServiceProvider> interface and has a <xref:System.IServiceProvider.GetService%2A> method.</span></span>  
  
 <span data-ttu-id="9b173-144">V systému typu XAML a pro implementace zapisovače XAML, které používají zpracování smyčky uzlu XAML pro serializaci převaděč hodnoty, který je přidružený typ nebo člen je hlášen vlastní <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="9b173-144">In the XAML type system and for XAML writer implementations that use XAML node loop processing for serialization, a value converter that is associated with a type or member is reported by its own <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="9b173-145">Význam do zapisovače XAML, které provádějí serializace je, že pokud <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> a <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> existuje, převaděče typů se má používat pro zatížení cesta a hodnota serializátoru, který má být použit pro uložení cestu.</span><span class="sxs-lookup"><span data-stu-id="9b173-145">The meaning to XAML writers that perform serialization is that if a <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> and <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> exist, the type converter should be used for the load path and the value serializer should be used for the save path.</span></span> <span data-ttu-id="9b173-146">Pokud <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> existuje, ale <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> je `null`, převaděče typů se taky používá pro uložení cestu.</span><span class="sxs-lookup"><span data-stu-id="9b173-146">If <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> exists but <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> is `null`, the type converter is also used for the save path.</span></span>  
  
<a name="other_value_converters"></a>   
## <a name="other-value-converters"></a><span data-ttu-id="9b173-147">Další převodníky hodnot</span><span class="sxs-lookup"><span data-stu-id="9b173-147">Other Value Converters</span></span>  
 <span data-ttu-id="9b173-148">Převaděč hodnoty je rozšiřitelný určité vzory převaděče typů nebo rozšíření značek.</span><span class="sxs-lookup"><span data-stu-id="9b173-148">A value converter is extensible beyond the specific patterns of a type converter or a markup extension.</span></span> <span data-ttu-id="9b173-149">Toto vlastní nastavení však by vyžadovaly předefinování systém typů XAML jako poskytované rozhraní .NET Framework XAML Services.</span><span class="sxs-lookup"><span data-stu-id="9b173-149">However, this customization would also require the redefinition of the XAML type system as provided by .NET Framework XAML Services.</span></span> <span data-ttu-id="9b173-150">Existující systém typů XAML má reprezentace a vytváření sestav systémy pro převaděče typů, rozšíření značek a serializátorů hodnotu, ale ne pro vlastní formy převod hodnoty.</span><span class="sxs-lookup"><span data-stu-id="9b173-150">The existing XAML type system has representations and reporting systems for type converters, markup extensions, and value serializers, but not for custom forms of value conversion.</span></span> <span data-ttu-id="9b173-151">Pokud chcete vytvořit vlastní hodnotu převaděče, použijte <xref:System.Xaml.Schema.XamlValueConverter%601> typu.</span><span class="sxs-lookup"><span data-stu-id="9b173-151">If you want to create custom value converters, use the <xref:System.Xaml.Schema.XamlValueConverter%601> type.</span></span>  
  
<a name="type_converters_and_markup_extensions_in_combination"></a>   
## <a name="type-converters-and-markup-extensions-in-combination"></a><span data-ttu-id="9b173-152">Převaděče typů a rozšíření značek v kombinaci</span><span class="sxs-lookup"><span data-stu-id="9b173-152">Type Converters and Markup Extensions in Combination</span></span>  
 <span data-ttu-id="9b173-153">Rozšíření a typ převaděče značek se používají pro různé situace v jazyce XAML.</span><span class="sxs-lookup"><span data-stu-id="9b173-153">Markup extensions and type converters are used for different situations in XAML.</span></span> <span data-ttu-id="9b173-154">I když kontext je k dispozici pro použití rozšíření značek, chování převodu typu vlastností, kde rozšíření značek poskytuje že hodnotu je obecně kontrolována v implementacích rozšíření značek.</span><span class="sxs-lookup"><span data-stu-id="9b173-154">Although context is available for markup extension usages, type conversion behavior of properties where a markup extension provides a value is generally is not checked in the markup extension implementations.</span></span> <span data-ttu-id="9b173-155">Jinými slovy i v případě, že rozšíření značek vrátí textový řetězec jako jeho `ProvideValue` výstupu typ převodu chování na tento řetězec jako použít pro určitou vlastnost nebo typ hodnoty vlastnosti není vyvolána.</span><span class="sxs-lookup"><span data-stu-id="9b173-155">In other words, even if a markup extension returns a text string as its `ProvideValue` output, type conversion behavior on that string as applied to a specific property or property value type is not invoked.</span></span> <span data-ttu-id="9b173-156">Obecně platí je účelem rozšíření značek zpracovat řetězec a vrátí objekt bez jakékoli převaděče typů související se situací.</span><span class="sxs-lookup"><span data-stu-id="9b173-156">Generally, the purpose of a markup extension is to process a string and return an object without any type converter involved.</span></span>  
  
<a name="service_context_for_a_value_converter"></a>   
## <a name="service-context-for-a-value-converter"></a><span data-ttu-id="9b173-157">Kontext služby pro převaděč hodnoty</span><span class="sxs-lookup"><span data-stu-id="9b173-157">Service Context for a Value Converter</span></span>  
 <span data-ttu-id="9b173-158">Pokud implementujete převaděč hodnoty, často potřebují přístup k kontext, ve kterém se použije převaděč hodnoty.</span><span class="sxs-lookup"><span data-stu-id="9b173-158">When you implement a value converter, you often need access to a context in which the value converter is applied.</span></span> <span data-ttu-id="9b173-159">Tento kontext se označuje jako kontext služby.</span><span class="sxs-lookup"><span data-stu-id="9b173-159">This context is known as the service context.</span></span> <span data-ttu-id="9b173-160">Kontext služby může obsahovat informace, jako je active kontext schématu XAML, přístup k systému mapování typu, který kontext schématu XAML a zapisovače objektu XAML zadejte a tak dále.</span><span class="sxs-lookup"><span data-stu-id="9b173-160">The service context might include information such as the active XAML schema context, access to the type mapping system that the XAML schema context and XAML object writer provide, and so on.</span></span> <span data-ttu-id="9b173-161">Další informace o kontexty služby dostupné pro převaděče hodnotu a postupy pro přístup ke službám, které může poskytovat kontext služby najdete v tématu [služby kontexty dostupné pro převaděče typů a rozšíření značek](../../../docs/framework/xaml-services/service-contexts-available-to-type-converters-and-markup-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="9b173-161">For more information about the service contexts available for a value converter and how to access the services that a service context might provide, see [Service Contexts Available to Type Converters and Markup Extensions](../../../docs/framework/xaml-services/service-contexts-available-to-type-converters-and-markup-extensions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b173-162">Viz také</span><span class="sxs-lookup"><span data-stu-id="9b173-162">See Also</span></span>  
 <xref:System.Windows.Markup.MarkupExtension>  
 <xref:System.Xaml.XamlObjectWriter>  
 [<span data-ttu-id="9b173-163">Rozšíření značek pro jazyk XAML – přehled</span><span class="sxs-lookup"><span data-stu-id="9b173-163">Markup Extensions for XAML Overview</span></span>](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)  
 [<span data-ttu-id="9b173-164">Převaděčů typů pro jazyk XAML – přehled</span><span class="sxs-lookup"><span data-stu-id="9b173-164">Type Converters for XAML Overview</span></span>](../../../docs/framework/xaml-services/type-converters-for-xaml-overview.md)  
 [<span data-ttu-id="9b173-165">Kontexty služby dostupné pro převaděče typů a rozšíření značek</span><span class="sxs-lookup"><span data-stu-id="9b173-165">Service Contexts Available to Type Converters and Markup Extensions</span></span>](../../../docs/framework/xaml-services/service-contexts-available-to-type-converters-and-markup-extensions.md)