---
title: "Implementace vzoru ovládacích prvků hodnota pro automatizaci uživatelského rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
caps.latest.revision: "25"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 23e71c4ce230221f82172a0e5429fc362379869c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-value-control-pattern"></a><span data-ttu-id="ec185-102">Implementace vzoru ovládacích prvků hodnota pro automatizaci uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="ec185-102">Implementing the UI Automation Value Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="ec185-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="ec185-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ec185-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="ec185-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ec185-105">Toto téma představuje pokyny a konvence pro implementaci <xref:System.Windows.Automation.Provider.IValueProvider>, včetně informací o vlastnostech a události.</span><span class="sxs-lookup"><span data-stu-id="ec185-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IValueProvider>, including information on events and properties.</span></span> <span data-ttu-id="ec185-106">Na konci tohoto tématu jsou uvedeny odkazy na další odkazy.</span><span class="sxs-lookup"><span data-stu-id="ec185-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="ec185-107"><xref:System.Windows.Automation.ValuePattern> – Vzor ovládacích prvků se používá pro podporu ovládací prvky, které mají vnitřní hodnotu není pokrývání uzlů rozsah a který může být reprezentován jako řetězec.</span><span class="sxs-lookup"><span data-stu-id="ec185-107">The <xref:System.Windows.Automation.ValuePattern> control pattern is used to support controls that have an intrinsic value not spanning a range and that can be represented as a string.</span></span> <span data-ttu-id="ec185-108">Tento řetězec lze upravovat, v závislosti na ovládací prvek a jeho nastavení.</span><span class="sxs-lookup"><span data-stu-id="ec185-108">This string can be editable, depending on the control and its settings.</span></span> <span data-ttu-id="ec185-109">Příklady ovládacích prvků, které implementují tento vzor najdete v tématu [řízení vzor mapování pro klienty automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ec185-109">For examples of controls that implement this pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ec185-110">Postup implementace a konvence</span><span class="sxs-lookup"><span data-stu-id="ec185-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="ec185-111">Když implementace vzoru ovládacích prvků hodnota, poznamenejte si následující pokyny a konvence:</span><span class="sxs-lookup"><span data-stu-id="ec185-111">When implementing the Value control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="ec185-112">Ovládací prvky jako například <xref:System.Windows.Automation.ControlType.ListItem> a <xref:System.Windows.Automation.ControlType.TreeItem> musí podporovat <xref:System.Windows.Automation.ValuePattern> Pokud hodnota některou z položek upravovat, bez ohledu na aktuální režim úprav ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="ec185-112">Controls such as <xref:System.Windows.Automation.ControlType.ListItem> and <xref:System.Windows.Automation.ControlType.TreeItem> must support <xref:System.Windows.Automation.ValuePattern> if the value of any of the items is editable, regardless of the current edit mode of the control.</span></span> <span data-ttu-id="ec185-113">Nadřazeného ovládacího prvku musí také podporovat <xref:System.Windows.Automation.ValuePattern> Pokud podřízené položky se upravovat.</span><span class="sxs-lookup"><span data-stu-id="ec185-113">The parent control must also support <xref:System.Windows.Automation.ValuePattern> if the child items are editable.</span></span>  
  
 <span data-ttu-id="ec185-114">![Položky seznamu upravovat. ] (../../../docs/framework/ui-automation/media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")</span><span class="sxs-lookup"><span data-stu-id="ec185-114">![Editable list item.](../../../docs/framework/ui-automation/media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")</span></span>  
<span data-ttu-id="ec185-115">Příklad položky seznamu upravovat</span><span class="sxs-lookup"><span data-stu-id="ec185-115">Example of an Editable List Item</span></span>  
  
-   <span data-ttu-id="ec185-116">Ovládacích prvcích pro úpravy jeden řádek podporují programový přístup k jejich obsah implementací <xref:System.Windows.Automation.Provider.IValueProvider>.</span><span class="sxs-lookup"><span data-stu-id="ec185-116">Single-line edit controls support programmatic access to their contents by implementing <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span> <span data-ttu-id="ec185-117">Ale ovládacích prvcích pro úpravy Víceřádkový neimplementují <xref:System.Windows.Automation.Provider.IValueProvider>; místo toho poskytují přístup k jejich obsahu implementací <xref:System.Windows.Automation.Provider.ITextProvider>.</span><span class="sxs-lookup"><span data-stu-id="ec185-117">However, multi-line edit controls do not implement <xref:System.Windows.Automation.Provider.IValueProvider>; instead they provide access to their content by implementing <xref:System.Windows.Automation.Provider.ITextProvider>.</span></span>  
  
-   <span data-ttu-id="ec185-118">Můžete načíst textový obsah ovládacího prvku Víceřádkový úpravy, musí implementovat řízení <xref:System.Windows.Automation.Provider.ITextProvider>.</span><span class="sxs-lookup"><span data-stu-id="ec185-118">To retrieve the textual contents of a multi-line edit control, the control must implement <xref:System.Windows.Automation.Provider.ITextProvider>.</span></span> <span data-ttu-id="ec185-119">Ale <xref:System.Windows.Automation.Provider.ITextProvider> nepodporuje nastavení hodnoty ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="ec185-119">However, <xref:System.Windows.Automation.Provider.ITextProvider> does not support setting the value of a control.</span></span>  
  
-   <span data-ttu-id="ec185-120"><xref:System.Windows.Automation.Provider.IValueProvider>nepodporuje načtení formátování informace nebo podřetězcem hodnoty.</span><span class="sxs-lookup"><span data-stu-id="ec185-120"><xref:System.Windows.Automation.Provider.IValueProvider> does not support the retrieval of formatting information or substring values.</span></span> <span data-ttu-id="ec185-121">Implementace <xref:System.Windows.Automation.Provider.ITextProvider> v těchto scénářích.</span><span class="sxs-lookup"><span data-stu-id="ec185-121">Implement <xref:System.Windows.Automation.Provider.ITextProvider> in these scenarios.</span></span>  
  
-   <span data-ttu-id="ec185-122"><xref:System.Windows.Automation.Provider.IValueProvider>musí být implementované ovládací prvky, jako **volby barev** ovládacího prvku pro výběr z [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (ilustrované níže), který podporuje řetězec mapování mezi hodnotu barvu (například "žlutý") a ekvivalentní interní [!INCLUDE[TLA#tla_rgb](../../../includes/tlasharptla-rgb-md.md)]struktura.</span><span class="sxs-lookup"><span data-stu-id="ec185-122"><xref:System.Windows.Automation.Provider.IValueProvider> must be implemented by controls such as the **Color Picker** selection control from [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (illustrated below), which supports string mapping between a color value (for example, "yellow") and an equivalent internal [!INCLUDE[TLA#tla_rgb](../../../includes/tlasharptla-rgb-md.md)] structure.</span></span>  
  
 <span data-ttu-id="ec185-123">![Výběr barvy s žlutý zvýrazněná. ] (../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span><span class="sxs-lookup"><span data-stu-id="ec185-123">![Color picker with yellow highlighted.](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span></span>  
<span data-ttu-id="ec185-124">Příklad mapování řetězec vzorníku barev</span><span class="sxs-lookup"><span data-stu-id="ec185-124">Example of Color Swatch String Mapping</span></span>  
  
-   <span data-ttu-id="ec185-125">Ovládacího prvku by měl mít jeho <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> nastavena na `true` a jeho <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> nastavena na `false` před povolením volání <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="ec185-125">A control should have its <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> set to `true` and its <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> set to `false` before allowing a call to <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-ivalueprovider"></a><span data-ttu-id="ec185-126">Požadované členy pro IValueProvider</span><span class="sxs-lookup"><span data-stu-id="ec185-126">Required Members for IValueProvider</span></span>  
 <span data-ttu-id="ec185-127">Následující vlastnosti a metody jsou požadovány pro implementaci <xref:System.Windows.Automation.Provider.IValueProvider>.</span><span class="sxs-lookup"><span data-stu-id="ec185-127">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span>  
  
|<span data-ttu-id="ec185-128">Požadované členy</span><span class="sxs-lookup"><span data-stu-id="ec185-128">Required members</span></span>|<span data-ttu-id="ec185-129">Typ člena</span><span class="sxs-lookup"><span data-stu-id="ec185-129">Member type</span></span>|<span data-ttu-id="ec185-130">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ec185-130">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|<span data-ttu-id="ec185-131">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="ec185-131">Property</span></span>|<span data-ttu-id="ec185-132">Žádné</span><span class="sxs-lookup"><span data-stu-id="ec185-132">None</span></span>|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|<span data-ttu-id="ec185-133">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="ec185-133">Property</span></span>|<span data-ttu-id="ec185-134">Žádné</span><span class="sxs-lookup"><span data-stu-id="ec185-134">None</span></span>|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|<span data-ttu-id="ec185-135">Metoda</span><span class="sxs-lookup"><span data-stu-id="ec185-135">Method</span></span>|<span data-ttu-id="ec185-136">Žádné</span><span class="sxs-lookup"><span data-stu-id="ec185-136">None</span></span>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="ec185-137">Výjimky</span><span class="sxs-lookup"><span data-stu-id="ec185-137">Exceptions</span></span>  
 <span data-ttu-id="ec185-138">Zprostředkovatelé musí throw následující výjimky.</span><span class="sxs-lookup"><span data-stu-id="ec185-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="ec185-139">Typ výjimky</span><span class="sxs-lookup"><span data-stu-id="ec185-139">Exception type</span></span>|<span data-ttu-id="ec185-140">Podmínka</span><span class="sxs-lookup"><span data-stu-id="ec185-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="ec185-141">– Pokud informace specifické pro národní prostředí je předán do ovládacího prvku v nesprávném formátu jako je například datum nesprávně formátovaný.</span><span class="sxs-lookup"><span data-stu-id="ec185-141">-   If locale-specific information is passed to a control in an incorrect format such as an incorrectly formatted date.</span></span>|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="ec185-142">– Pokud nová hodnota nelze převést z řetězce do formátu rozpozná ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="ec185-142">-   If a new value cannot be converted from a string to a format the control recognizes.</span></span>|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="ec185-143">– Když je proveden pokus o k manipulaci s ovládacího prvku, který není povolen.</span><span class="sxs-lookup"><span data-stu-id="ec185-143">-   When an attempt is made to manipulate a control that is not enabled.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec185-144">Viz také</span><span class="sxs-lookup"><span data-stu-id="ec185-144">See Also</span></span>  
 [<span data-ttu-id="ec185-145">Přehled vzorů ovládacích prvků automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="ec185-145">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="ec185-146">Podpora vzorů ovládacích prvků u zprostředkovatele automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="ec185-146">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="ec185-147">Vzory ovládacího prvku automatizace uživatelského rozhraní pro klienty</span><span class="sxs-lookup"><span data-stu-id="ec185-147">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="ec185-148">Ukázka TextPattern vložení textu</span><span class="sxs-lookup"><span data-stu-id="ec185-148">TextPattern Insert Text Sample</span></span>](http://msdn.microsoft.com/en-us/67353f93-7ee2-42f2-ab76-5c078cf6ca16)  
 [<span data-ttu-id="ec185-149">Přehled stromu automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="ec185-149">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="ec185-150">Použití mezipaměti při automatizaci uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="ec185-150">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)