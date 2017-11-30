---
title: "Implementace vzoru ovládacích prvků vyvolání pro automatizaci uživatelského rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Invoke control pattern
- control patterns, Invoke
- Invoke control pattern
ms.assetid: e5b1e239-49f8-468e-bfec-1fba02ec9ac4
caps.latest.revision: "31"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: d42952328f70fec32b4a2cb58733785b3c1d97ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-invoke-control-pattern"></a><span data-ttu-id="5befa-102">Implementace vzoru ovládacích prvků vyvolání pro automatizaci uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5befa-102">Implementing the UI Automation Invoke Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="5befa-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5befa-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5befa-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="5befa-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5befa-105">Toto téma představuje pokyny a konvence pro implementaci <xref:System.Windows.Automation.Provider.IInvokeProvider>, včetně informací o události a vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="5befa-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IInvokeProvider>, including information about events and properties.</span></span> <span data-ttu-id="5befa-106">Na konci tohoto tématu jsou uvedeny odkazy na další odkazy.</span><span class="sxs-lookup"><span data-stu-id="5befa-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="5befa-107"><xref:System.Windows.Automation.InvokePattern> – Vzor ovládacích prvků se používá pro podporu ovládacích prvků, které uchování stavu, pokud je aktivován ale spíše inicializovat nebo provedení jednoho, jednoznačným akce.</span><span class="sxs-lookup"><span data-stu-id="5befa-107">The <xref:System.Windows.Automation.InvokePattern> control pattern is used to support controls that do not maintain state when activated but rather initiate or perform a single, unambiguous action.</span></span> <span data-ttu-id="5befa-108">Ovládací prvky, které udržují stavu, například zaškrtávací políčka a přepínače, místo toho musí implementovat <xref:System.Windows.Automation.Provider.IToggleProvider> a <xref:System.Windows.Automation.Provider.ISelectionItemProvider> v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="5befa-108">Controls that do maintain state, such as check boxes and radio buttons, must instead implement <xref:System.Windows.Automation.Provider.IToggleProvider> and <xref:System.Windows.Automation.Provider.ISelectionItemProvider> respectively.</span></span> <span data-ttu-id="5befa-109">Příklady ovládacích prvků, které implementují vzor Invoke ovládacích prvků najdete v tématu [řízení vzor mapování pro klienty automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="5befa-109">For examples of controls that implement the Invoke control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="5befa-110">Postup implementace a konvence</span><span class="sxs-lookup"><span data-stu-id="5befa-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="5befa-111">Při implementaci vzoru Invoke ovládacích prvků, poznamenejte si následující pokyny a konvence:</span><span class="sxs-lookup"><span data-stu-id="5befa-111">When implementing the Invoke control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="5befa-112">Ovládací prvky implementovat <xref:System.Windows.Automation.Provider.IInvokeProvider> Pokud stejné chování nebude vystavena prostřednictvím jiného poskytovatele vzor ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="5befa-112">Controls implement <xref:System.Windows.Automation.Provider.IInvokeProvider> if the same behavior is not exposed through another control pattern provider.</span></span> <span data-ttu-id="5befa-113">Například pokud <xref:System.Windows.Automation.InvokePattern.Invoke%2A> metoda v ovládacím prvku provede stejnou akci, jako <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> nebo <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> metody ovládacího prvku by neměly implementovat <xref:System.Windows.Automation.Provider.IInvokeProvider>.</span><span class="sxs-lookup"><span data-stu-id="5befa-113">For example, if the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method on a control performs the same action as the <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> or <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> method, the control should not implement <xref:System.Windows.Automation.Provider.IInvokeProvider>.</span></span>  
  
-   <span data-ttu-id="5befa-114">Vyvolání ovládacího prvku se obvykle provádí klepnutím nebo dvakrát kliknete na soubor nebo stisknutím ENTER, předdefinované klávesové zkratky nebo některé alternativní kombinace kláves.</span><span class="sxs-lookup"><span data-stu-id="5befa-114">Invoking a control is generally performed by clicking or double-clicking or pressing ENTER, a predefined keyboard shortcut, or some alternate combination of keystrokes.</span></span>  
  
-   <span data-ttu-id="5befa-115"><xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>je vyvolána na ovládací prvek, který byl aktivován (jako odpověď do ovládacího prvku jeho přidružené akce).</span><span class="sxs-lookup"><span data-stu-id="5befa-115"><xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> is raised on a control that has been activated (as a response to a control carrying out its associated action).</span></span> <span data-ttu-id="5befa-116">Pokud je to možné by měl být událost vyvolána po dokončil akci a vrátí bez blokování ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="5befa-116">If possible, the event should be raised after the control has completed the action and returned without blocking.</span></span> <span data-ttu-id="5befa-117">Událost Invoked by měl být vyvolána před obsluhy Invoke žádosti v následujících scénářích:</span><span class="sxs-lookup"><span data-stu-id="5befa-117">The Invoked event should be raised before servicing the Invoke request in the following scenarios:</span></span>  
  
    -   <span data-ttu-id="5befa-118">Není možné ani praktické počkejte na dokončení akce.</span><span class="sxs-lookup"><span data-stu-id="5befa-118">It is not possible or practical to wait until the action is complete.</span></span>  
  
    -   <span data-ttu-id="5befa-119">Akce vyžaduje interakci uživatele.</span><span class="sxs-lookup"><span data-stu-id="5befa-119">The action requires user interaction.</span></span>  
  
    -   <span data-ttu-id="5befa-120">Akce je časově náročná a způsobí, že volajícího klienta blokovat pro významné množství času.</span><span class="sxs-lookup"><span data-stu-id="5befa-120">The action is time-consuming and will cause the calling client to block for a significant amount of time.</span></span>  
  
-   <span data-ttu-id="5befa-121">Pokud vyvolání ovládacího prvku má významné vedlejší účinky, by měly být tyto vedlejší účinky vystaveny prostřednictvím <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5befa-121">If invoking the control has significant side-effects, those side-effects should be exposed through the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A> property.</span></span> <span data-ttu-id="5befa-122">Například i když <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> není přidružen k výběru, <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> může způsobit, že jiný řízení jako vybrané.</span><span class="sxs-lookup"><span data-stu-id="5befa-122">For example, even though <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> is not associated with selection, <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> may cause another control to become selected.</span></span>  
  
-   <span data-ttu-id="5befa-123">Při přechodu myší (nebo myší nad) důsledky obecně nepředstavují Invoked událost.</span><span class="sxs-lookup"><span data-stu-id="5befa-123">Hover (or mouse-over) effects generally do not constitute an Invoked event.</span></span> <span data-ttu-id="5befa-124">Však musí podporovat ovládacích prvků, které provedení akce (na rozdíl od příčina vizuální efekt) na základě stavu přechodu <xref:System.Windows.Automation.InvokePattern> – vzor ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="5befa-124">However, controls that perform an action (as opposed to cause a visual effect) based on the hover state should support the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5befa-125">Tato implementace je považován za usnadnění problém, pokud ovládacího prvku nelze vyvolat jenom v důsledku vedlejším účinkem související myši.</span><span class="sxs-lookup"><span data-stu-id="5befa-125">This implementation is considered an accessibility issue if the control can be invoked only as a result of a mouse-related side effect.</span></span>  
  
-   <span data-ttu-id="5befa-126">Vyvolání ovládacího prvku se liší od výběrem položky.</span><span class="sxs-lookup"><span data-stu-id="5befa-126">Invoking a control is different from selecting an item.</span></span> <span data-ttu-id="5befa-127">V závislosti na ovládací prvek, však může ho vyvolání položka, která má jako vybrané jako vedlejším účinkem způsobit.</span><span class="sxs-lookup"><span data-stu-id="5befa-127">However, depending on the control, invoking it may cause the item to become selected as a side-effect.</span></span> <span data-ttu-id="5befa-128">Například volání [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] položky seznamu dokumentu ve složce Dokumenty vybere položka i otevře dokument.</span><span class="sxs-lookup"><span data-stu-id="5befa-128">For example, invoking a [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] document list item in the My Documents folder both selects the item and opens the document.</span></span>  
  
-   <span data-ttu-id="5befa-129">Element může zmizet z [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu okamžitě po vyvolání.</span><span class="sxs-lookup"><span data-stu-id="5befa-129">An element can disappear from the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree immediately upon being invoked.</span></span> <span data-ttu-id="5befa-130">Vyžadování informací o z zadaný element zpětného volání události pravděpodobně v důsledku nezdaří.</span><span class="sxs-lookup"><span data-stu-id="5befa-130">Requesting information from the element provided by the event callback may fail as a result.</span></span> <span data-ttu-id="5befa-131">Předběžné načítání informace uložené v mezipaměti je doporučená řešení.</span><span class="sxs-lookup"><span data-stu-id="5befa-131">Pre-fetching cached information is the recommended workaround.</span></span>  
  
-   <span data-ttu-id="5befa-132">Ovládací prvky můžete implementovat několik vzorů ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="5befa-132">Controls can implement multiple control patterns.</span></span> <span data-ttu-id="5befa-133">Například ovládacího prvku Barva výplně na [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] nástrojů implementuje i <xref:System.Windows.Automation.InvokePattern> a <xref:System.Windows.Automation.ExpandCollapsePattern> řízení vzory.</span><span class="sxs-lookup"><span data-stu-id="5befa-133">For example, the Fill Color control on the [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] toolbar implements both the <xref:System.Windows.Automation.InvokePattern> and the <xref:System.Windows.Automation.ExpandCollapsePattern> control patterns.</span></span> <span data-ttu-id="5befa-134"><xref:System.Windows.Automation.ExpandCollapsePattern>zpřístupní v nabídce a <xref:System.Windows.Automation.InvokePattern> doplní aktivní výběr zvolené barvou.</span><span class="sxs-lookup"><span data-stu-id="5befa-134"><xref:System.Windows.Automation.ExpandCollapsePattern> exposes the menu and the <xref:System.Windows.Automation.InvokePattern> fills the active selection with the chosen color.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-iinvokeprovider"></a><span data-ttu-id="5befa-135">Požadované členy pro IInvokeProvider</span><span class="sxs-lookup"><span data-stu-id="5befa-135">Required Members for IInvokeProvider</span></span>  
 <span data-ttu-id="5befa-136">Následující vlastnosti a metody jsou požadovány pro implementaci <xref:System.Windows.Automation.Provider.IInvokeProvider>.</span><span class="sxs-lookup"><span data-stu-id="5befa-136">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IInvokeProvider>.</span></span>  
  
|<span data-ttu-id="5befa-137">Požadované členy</span><span class="sxs-lookup"><span data-stu-id="5befa-137">Required members</span></span>|<span data-ttu-id="5befa-138">Typ člena</span><span class="sxs-lookup"><span data-stu-id="5befa-138">Member type</span></span>|<span data-ttu-id="5befa-139">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5befa-139">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A>|<span data-ttu-id="5befa-140">– metoda</span><span class="sxs-lookup"><span data-stu-id="5befa-140">method</span></span>|<span data-ttu-id="5befa-141"><xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A>je asynchronní volání a musí vracet okamžitě bez blokování.</span><span class="sxs-lookup"><span data-stu-id="5befa-141"><xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> is an asynchronous call and must return immediately without blocking.</span></span><br /><br /> <span data-ttu-id="5befa-142">Toto chování je obzvláště důležité pro ovládací prvky, které přímo nebo nepřímo, spusťte modální dialogové okno při vyvolání.</span><span class="sxs-lookup"><span data-stu-id="5befa-142">This behavior is particularly critical for controls that, directly or indirectly, launch a modal dialog when invoked.</span></span> <span data-ttu-id="5befa-143">Libovolného automatizace uživatelského rozhraní klienta, který zahájené událost zůstane blokovaný, dokud modální dialogové okno je uzavřený.</span><span class="sxs-lookup"><span data-stu-id="5befa-143">Any UI Automation client that instigated the event will remain blocked until the modal dialog is closed.</span></span>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="5befa-144">Výjimky</span><span class="sxs-lookup"><span data-stu-id="5befa-144">Exceptions</span></span>  
 <span data-ttu-id="5befa-145">Zprostředkovatelé musí throw následující výjimky.</span><span class="sxs-lookup"><span data-stu-id="5befa-145">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="5befa-146">Typ výjimky</span><span class="sxs-lookup"><span data-stu-id="5befa-146">Exception Type</span></span>|<span data-ttu-id="5befa-147">Podmínka</span><span class="sxs-lookup"><span data-stu-id="5befa-147">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<span data-ttu-id="5befa-148">Pokud ovládací prvek není povolena.</span><span class="sxs-lookup"><span data-stu-id="5befa-148">If the control is not enabled.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5befa-149">Viz také</span><span class="sxs-lookup"><span data-stu-id="5befa-149">See Also</span></span>  
 [<span data-ttu-id="5befa-150">Přehled vzorů ovládacích prvků automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5befa-150">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="5befa-151">Podpora vzorů ovládacích prvků u zprostředkovatele automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5befa-151">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="5befa-152">Vzory ovládacího prvku automatizace uživatelského rozhraní pro klienty</span><span class="sxs-lookup"><span data-stu-id="5befa-152">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="5befa-153">Vyvolání ovládacího prvku s použitím automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5befa-153">Invoke a Control Using UI Automation</span></span>](../../../docs/framework/ui-automation/invoke-a-control-using-ui-automation.md)  
 [<span data-ttu-id="5befa-154">Přehled stromu automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5befa-154">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="5befa-155">Použití mezipaměti při automatizaci uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5befa-155">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)