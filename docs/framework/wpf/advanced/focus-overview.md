---
title: "Přehled fokusu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4e10f7136b636829f99da34388db7676810cd06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="focus-overview"></a><span data-ttu-id="137f0-102">Přehled fokusu</span><span class="sxs-lookup"><span data-stu-id="137f0-102">Focus Overview</span></span>
<span data-ttu-id="137f0-103">V [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] existují dvě hlavní koncepty, které se týkají fokus: fokus a logické fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-103">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] there are two main concepts that pertain to focus: keyboard focus and logical focus.</span></span>  <span data-ttu-id="137f0-104">Fokus klávesnice vztahuje k elementu, který přijímá vstup z klávesnice a logické fokus odkazuje na element v fokus obor, který má právě fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-104">Keyboard focus refers to the element that receives keyboard input and logical focus refers to the element in a focus scope that has focus.</span></span>  <span data-ttu-id="137f0-105">Tyto koncepty jsou podrobněji v tomto přehledu.</span><span class="sxs-lookup"><span data-stu-id="137f0-105">These concepts are discussed in detail in this overview.</span></span>  <span data-ttu-id="137f0-106">Vysvětlení rozdílu v tyto koncepty je důležité pro vytvoření složitých aplikací, které mají více oblastech, kde lze získat fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-106">Understanding the difference in these concepts is important for creating complex applications that have multiple regions where focus can be obtained.</span></span>  
  
 <span data-ttu-id="137f0-107">Hlavní třídy, které jsou součástí správy fokus <xref:System.Windows.Input.Keyboard> třídy, <xref:System.Windows.Input.FocusManager> třídy a prvku základní třídy, jako <xref:System.Windows.UIElement> a <xref:System.Windows.ContentElement>.</span><span class="sxs-lookup"><span data-stu-id="137f0-107">The major classes that participate in focus management are the <xref:System.Windows.Input.Keyboard> class, the <xref:System.Windows.Input.FocusManager> class, and the base element classes, such as <xref:System.Windows.UIElement> and <xref:System.Windows.ContentElement>.</span></span>  <span data-ttu-id="137f0-108">Další informace o základní prvky najdete v tématu [základní přehled elementy](../../../../docs/framework/wpf/advanced/base-elements-overview.md).</span><span class="sxs-lookup"><span data-stu-id="137f0-108">For more information about the base elements, see the [Base Elements Overview](../../../../docs/framework/wpf/advanced/base-elements-overview.md).</span></span>  
  
 <span data-ttu-id="137f0-109"><xref:System.Windows.Input.Keyboard> Třídy se týká především fokus klávesnice a <xref:System.Windows.Input.FocusManager> se zajímají hlavně logické fokus, ale nejedná se o absolutní odlišení.</span><span class="sxs-lookup"><span data-stu-id="137f0-109">The <xref:System.Windows.Input.Keyboard> class is concerned primarily with keyboard focus and the <xref:System.Windows.Input.FocusManager> is concerned primarily with logical focus, but this is not an absolute distinction.</span></span>  <span data-ttu-id="137f0-110">Element, který má právě fokus klávesnice, bude mít i logické fokus, ale element, který má právě fokus logické nemá nutně fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-110">An element that has keyboard focus will also have logical focus, but an element that has logical focus does not necessarily have keyboard focus.</span></span>  <span data-ttu-id="137f0-111">Toto je zřejmá při použití <xref:System.Windows.Input.Keyboard> třída elementu, který má fokus klávesnice pro ni nastavit také nastaví logické fokus na elementu.</span><span class="sxs-lookup"><span data-stu-id="137f0-111">This is apparent when you use the <xref:System.Windows.Input.Keyboard> class to set the element that has keyboard focus, for it also sets logical focus on the element.</span></span>  
  

  
<a name="Keyboard_Focus"></a>   
## <a name="keyboard-focus"></a><span data-ttu-id="137f0-112">Fokus klávesnice</span><span class="sxs-lookup"><span data-stu-id="137f0-112">Keyboard Focus</span></span>  
 <span data-ttu-id="137f0-113">Fokus klávesnice odkazuje na element, který je aktuálně přijímá vstup z klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-113">Keyboard focus refers to the element that is currently receiving keyboard input.</span></span>  <span data-ttu-id="137f0-114">Může existovat pouze jeden element celkově plochy, který má právě fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-114">There can be only one element on the whole desktop that has keyboard focus.</span></span>  <span data-ttu-id="137f0-115">V [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], bude mít elementu, který má právě fokus klávesnice <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> nastavena na `true`.</span><span class="sxs-lookup"><span data-stu-id="137f0-115">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], the element that has keyboard focus will have <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> set to `true`.</span></span>  <span data-ttu-id="137f0-116">Statické vlastnosti <xref:System.Windows.Input.Keyboard.FocusedElement%2A> na <xref:System.Windows.Input.Keyboard> třída získá elementu, který má právě fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-116">The static property <xref:System.Windows.Input.Keyboard.FocusedElement%2A> on the <xref:System.Windows.Input.Keyboard> class gets the element that currently has keyboard focus.</span></span>  
  
 <span data-ttu-id="137f0-117">V pořadí pro daný element získat fokus klávesnice <xref:System.Windows.UIElement.Focusable%2A> a <xref:System.Windows.UIElement.IsVisible%2A> vlastnosti na základní elementy musí být nastavena na `true`.</span><span class="sxs-lookup"><span data-stu-id="137f0-117">In order for an element to obtain keyboard focus, the <xref:System.Windows.UIElement.Focusable%2A> and the <xref:System.Windows.UIElement.IsVisible%2A> properties on the base elements must be set to `true`.</span></span>  <span data-ttu-id="137f0-118">Některé třídy, jako <xref:System.Windows.Controls.Panel> základní třídy, mít <xref:System.Windows.UIElement.Focusable%2A> nastavena na `false` ve výchozím nastavení; proto musíte nastavit <xref:System.Windows.UIElement.Focusable%2A> k `true` Pokud chcete mít možnost získat fokus klávesnice takový prvek.</span><span class="sxs-lookup"><span data-stu-id="137f0-118">Some classes, such as the <xref:System.Windows.Controls.Panel> base class, have <xref:System.Windows.UIElement.Focusable%2A> set to `false` by default; therefore, you must set <xref:System.Windows.UIElement.Focusable%2A> to `true` if you want such an element to be able to obtain keyboard focus.</span></span>  
  
 <span data-ttu-id="137f0-119">Nelze získat fokus klávesnice prostřednictvím interakce uživatele s [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], jako jsou například pomocí klávesy tabulátor do elementu nebo kliknutím na tlačítko myši na některé prvky.</span><span class="sxs-lookup"><span data-stu-id="137f0-119">Keyboard focus can be obtained through user interaction with the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], such as tabbing to an element or clicking the mouse on certain elements.</span></span>  <span data-ttu-id="137f0-120">Fokus klávesnice jsou k dispozici prostřednictvím kódu programu pomocí <xref:System.Windows.Input.Keyboard.Focus%2A> metodu <xref:System.Windows.Input.Keyboard> třídy.</span><span class="sxs-lookup"><span data-stu-id="137f0-120">Keyboard focus can also be obtained programmatically by using the <xref:System.Windows.Input.Keyboard.Focus%2A> method on the <xref:System.Windows.Input.Keyboard> class.</span></span>  <span data-ttu-id="137f0-121"><xref:System.Windows.Input.Keyboard.Focus%2A> Metoda se pokusí předat fokus klávesnice zadaný element.</span><span class="sxs-lookup"><span data-stu-id="137f0-121">The <xref:System.Windows.Input.Keyboard.Focus%2A> method attempts to give the specified element keyboard focus.</span></span>  <span data-ttu-id="137f0-122">Vrácený element je element, který má fokus klávesnice, což může být element jiný než požadováno, pokud buď staré nebo nové zaměřit bloku object žádosti.</span><span class="sxs-lookup"><span data-stu-id="137f0-122">The returned element is the element that has keyboard focus, which might be a different element than requested if either the old or new focus object block the request.</span></span>  
  
 <span data-ttu-id="137f0-123">Následující příklad používá <xref:System.Windows.Input.Keyboard.Focus%2A> metodu a nastavit fokus klávesnice na <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="137f0-123">The following example uses the <xref:System.Windows.Input.Keyboard.Focus%2A> method to set keyboard focus on a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 <span data-ttu-id="137f0-124"><xref:System.Windows.UIElement.IsKeyboardFocused%2A> Vlastnost třídy base element získá hodnotu označující, zda má element fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-124">The <xref:System.Windows.UIElement.IsKeyboardFocused%2A> property on the base element classes gets a value indicating whether the element has keyboard focus.</span></span>  <span data-ttu-id="137f0-125"><xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> Vlastnost třídy base element získá hodnotu označující, zda element nebo kterékoli z jeho visual podřízené elementy má fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-125">The <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> property on the base element classes gets a value indicating whether the element or any one of its visual child elements has keyboard focus.</span></span>  
  
 <span data-ttu-id="137f0-126">Při nastavování počáteční fokus při spuštění aplikace, elementu, který chcete získat fokus musí být ve vizuální strojové struktuře okna počáteční načíst aplikací a musí mít element <xref:System.Windows.UIElement.Focusable%2A> a <xref:System.Windows.UIElement.IsVisible%2A> nastavena na `true`.</span><span class="sxs-lookup"><span data-stu-id="137f0-126">When setting initial focus at application startup, the element to receive focus must be in the visual tree of the initial window loaded by the application, and the element must have <xref:System.Windows.UIElement.Focusable%2A> and <xref:System.Windows.UIElement.IsVisible%2A> set to `true`.</span></span>  <span data-ttu-id="137f0-127">Je doporučené místo na nastavit počáteční fokus <xref:System.Windows.FrameworkElement.Loaded> obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="137f0-127">The recommended place to set initial focus is in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  <span data-ttu-id="137f0-128">A <xref:System.Windows.Threading.Dispatcher> zpětného volání lze také voláním <xref:System.Windows.Threading.Dispatcher.Invoke%2A> nebo <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="137f0-128">A <xref:System.Windows.Threading.Dispatcher> callback can also be used by calling <xref:System.Windows.Threading.Dispatcher.Invoke%2A> or <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.</span></span>  
  
<a name="Logical_Focus"></a>   
## <a name="logical-focus"></a><span data-ttu-id="137f0-129">Logické fokusu</span><span class="sxs-lookup"><span data-stu-id="137f0-129">Logical Focus</span></span>  
 <span data-ttu-id="137f0-130">Logické fokus odkazuje <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> v oboru fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-130">Logical focus refers to the <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> in a focus scope.</span></span>  <span data-ttu-id="137f0-131">Fokus obor je element, který sleduje <xref:System.Windows.Input.FocusManager.FocusedElement%2A> ve svém oboru.</span><span class="sxs-lookup"><span data-stu-id="137f0-131">A focus scope is an element that keeps track of the <xref:System.Windows.Input.FocusManager.FocusedElement%2A> within its scope.</span></span>  <span data-ttu-id="137f0-132">Když fokus klávesnice opustí obor fokus, cílených elementu dojde ke ztrátě fokus klávesnice, ale zachovají logické fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-132">When keyboard focus leaves a focus scope, the focused element will lose keyboard focus but will retain logical focus.</span></span>  <span data-ttu-id="137f0-133">Když se fokus klávesnice vrátí do oboru fokus, bude cílených element získat fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-133">When keyboard focus returns to the focus scope, the focused element will obtain keyboard focus.</span></span>  <span data-ttu-id="137f0-134">To umožňuje fokus klávesnice změnit mezi více obory fokus, ale zajišťuje, že cílených element v oboru fokus získal fokus klávesnice když se fokus vrátí do oboru fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-134">This allows for keyboard focus to be changed between multiple focus scopes but ensures that the focused element in the focus scope regains keyboard focus when focus returns to the focus scope.</span></span>  
  
 <span data-ttu-id="137f0-135">Může být více elementů, které mají logické fokusu v aplikaci, ale může existovat pouze jeden element, který má právě fokus logické v konkrétní výběr oboru.</span><span class="sxs-lookup"><span data-stu-id="137f0-135">There can be multiple elements that have logical focus in an application, but there may only be one element that has logical focus in a particular focus scope.</span></span>  
  
 <span data-ttu-id="137f0-136">Element, který má právě fokus klávesnice, má logické fokus, které patří do oboru fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-136">An element that has keyboard focus has logical focus for the focus scope it belongs to.</span></span>  
  
 <span data-ttu-id="137f0-137">Element mohou být změněny na obor fokusu v [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] nastavením <xref:System.Windows.Input.FocusManager> přidružená vlastnost <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> k `true`.</span><span class="sxs-lookup"><span data-stu-id="137f0-137">An element can be turned into a focus scope in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] by setting the <xref:System.Windows.Input.FocusManager> attached property <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> to `true`.</span></span>  <span data-ttu-id="137f0-138">V kódu element mohou být změněny na obor fokus voláním <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.</span><span class="sxs-lookup"><span data-stu-id="137f0-138">In code, an element can be turned into a focus scope by calling <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.</span></span>  
  
 <span data-ttu-id="137f0-139">Následující příklad vytvoří <xref:System.Windows.Controls.StackPanel> do oboru fokus nastavením <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> přidružená vlastnost.</span><span class="sxs-lookup"><span data-stu-id="137f0-139">The following example makes a <xref:System.Windows.Controls.StackPanel> into a focus scope by setting the <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> attached property.</span></span>  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <span data-ttu-id="137f0-140"><xref:System.Windows.Input.FocusManager.GetFocusScope%2A>Vrátí fokus rozsah pro zadaný element.</span><span class="sxs-lookup"><span data-stu-id="137f0-140"><xref:System.Windows.Input.FocusManager.GetFocusScope%2A> returns the focus scope for the specified element.</span></span>  
  
 <span data-ttu-id="137f0-141">Třídy v [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] který jsou obory fokus ve výchozím nastavení jsou <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, a <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="137f0-141">Classes in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] which are focus scopes by default are <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, and <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
 <span data-ttu-id="137f0-142"><xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>Získá cílených element pro obor zadaný fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-142"><xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> gets the focused element for the specified focus scope.</span></span>  <span data-ttu-id="137f0-143"><xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>Nastaví cílených element v oboru zadaný fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-143"><xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> sets the focused element in the specified focus scope.</span></span>  <span data-ttu-id="137f0-144"><xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>se obvykle používá k nastavení počátečního cílených elementu.</span><span class="sxs-lookup"><span data-stu-id="137f0-144"><xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> is typically used to set the initial focused element.</span></span>  
  
 <span data-ttu-id="137f0-145">Následující příklad nastaví element cílených na obor fokus a získá cílených elementu obor fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-145">The following example sets the focused element on a focus scope and gets the focused element of a focus scope.</span></span>  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## <a name="keyboard-navigation"></a><span data-ttu-id="137f0-146">Navigace pomocí klávesnice</span><span class="sxs-lookup"><span data-stu-id="137f0-146">Keyboard Navigation</span></span>  
 <span data-ttu-id="137f0-147"><xref:System.Windows.Input.KeyboardNavigation> Třída je odpovědná za implementace navigační fokus klávesnice výchozí při stisknutí jeden z klíčů navigace.</span><span class="sxs-lookup"><span data-stu-id="137f0-147">The <xref:System.Windows.Input.KeyboardNavigation> class is responsible for implementing default keyboard focus navigation when one of the navigation keys is pressed.</span></span>  <span data-ttu-id="137f0-148">Navigační klávesy, jsou: karta, SHIFT + TAB, CTRL + TAB, CTRL + SHIFT + TAB, UPARROW, DOWNARROW, šipka vlevo a šipka vpravo klíče.</span><span class="sxs-lookup"><span data-stu-id="137f0-148">The navigation keys are: TAB, SHIFT+TAB, CTRL+TAB, CTRL+SHIFT+TAB, UPARROW, DOWNARROW, LEFTARROW, and RIGHTARROW keys.</span></span>  
  
 <span data-ttu-id="137f0-149">Navigační chování navigační kontejner může změnit nastavení připojený <xref:System.Windows.Input.KeyboardNavigation> vlastnosti <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, a <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.</span><span class="sxs-lookup"><span data-stu-id="137f0-149">The navigation behavior of a navigation container can be changed by setting the attached <xref:System.Windows.Input.KeyboardNavigation> properties <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, and <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.</span></span>  <span data-ttu-id="137f0-150">Tyto vlastnosti jsou typu <xref:System.Windows.Input.KeyboardNavigationMode> a možné hodnoty jsou <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, a <xref:System.Windows.Input.KeyboardNavigationMode.None>.</span><span class="sxs-lookup"><span data-stu-id="137f0-150">These properties are of type <xref:System.Windows.Input.KeyboardNavigationMode> and the possible values are <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, and <xref:System.Windows.Input.KeyboardNavigationMode.None>.</span></span>  <span data-ttu-id="137f0-151">Výchozí hodnota je <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, což znamená, že element není kontejner navigace.</span><span class="sxs-lookup"><span data-stu-id="137f0-151">The default value is <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, which means the element is not a navigation container.</span></span>  
  
 <span data-ttu-id="137f0-152">Následující příklad vytvoří <xref:System.Windows.Controls.Menu> s počtem <xref:System.Windows.Controls.MenuItem> objekty.</span><span class="sxs-lookup"><span data-stu-id="137f0-152">The following example creates a <xref:System.Windows.Controls.Menu> with a number of <xref:System.Windows.Controls.MenuItem> objects.</span></span>  <span data-ttu-id="137f0-153"><xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> Je připojená vlastnost nastavená na <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> na <xref:System.Windows.Controls.Menu>.</span><span class="sxs-lookup"><span data-stu-id="137f0-153">The <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> attached property is set to <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> on the <xref:System.Windows.Controls.Menu>.</span></span>  <span data-ttu-id="137f0-154">Při změně fokus pomocí klávesy tab v rámci <xref:System.Windows.Controls.Menu>, fokus přesune z každého prvku a když je dosaženo posledním elementem fokus vrátí do první prvek.</span><span class="sxs-lookup"><span data-stu-id="137f0-154">When focus is changed using the tab key within the <xref:System.Windows.Controls.Menu>, focus will move from each element and when the last element is reached focus will return to the first element.</span></span>  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## <a name="navigating-focus-programmatically"></a><span data-ttu-id="137f0-155">Navigace fokus prostřednictvím kódu programu</span><span class="sxs-lookup"><span data-stu-id="137f0-155">Navigating Focus Programmatically</span></span>  
 <span data-ttu-id="137f0-156">Další [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] pro práci s fokus jsou <xref:System.Windows.UIElement.MoveFocus%2A> a <xref:System.Windows.UIElement.PredictFocus%2A>.</span><span class="sxs-lookup"><span data-stu-id="137f0-156">Additional [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to work with focus are <xref:System.Windows.UIElement.MoveFocus%2A> and <xref:System.Windows.UIElement.PredictFocus%2A>.</span></span>  
  
 <span data-ttu-id="137f0-157"><xref:System.Windows.FrameworkElement.MoveFocus%2A>změny fokus na další prvek v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="137f0-157"><xref:System.Windows.FrameworkElement.MoveFocus%2A> changes focus to the next element in the application.</span></span>  <span data-ttu-id="137f0-158">A <xref:System.Windows.Input.TraversalRequest> slouží k určení směru.</span><span class="sxs-lookup"><span data-stu-id="137f0-158">A <xref:System.Windows.Input.TraversalRequest> is used to specify the direction.</span></span>   <span data-ttu-id="137f0-159"><xref:System.Windows.Input.FocusNavigationDirection> Předaný <xref:System.Windows.UIElement.MoveFocus%2A> Určuje jinou pokynů fokus lze přesunout, například <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> a <xref:System.Windows.Input.FocusNavigationDirection.Down>.</span><span class="sxs-lookup"><span data-stu-id="137f0-159">The <xref:System.Windows.Input.FocusNavigationDirection> passed to <xref:System.Windows.UIElement.MoveFocus%2A> specifies the different directions focus can be moved, such as <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> and <xref:System.Windows.Input.FocusNavigationDirection.Down>.</span></span>  
  
 <span data-ttu-id="137f0-160">Následující příklad používá <xref:System.Windows.FrameworkElement.MoveFocus%2A> změnit cílených elementu.</span><span class="sxs-lookup"><span data-stu-id="137f0-160">The following example uses <xref:System.Windows.FrameworkElement.MoveFocus%2A> to change the focused element.</span></span>  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <span data-ttu-id="137f0-161"><xref:System.Windows.FrameworkElement.PredictFocus%2A>Vrátí objekt, který by získat fokus, kdyby se musí změnit fokus.</span><span class="sxs-lookup"><span data-stu-id="137f0-161"><xref:System.Windows.FrameworkElement.PredictFocus%2A> returns the object which would receive focus if focus were to be changed.</span></span>  <span data-ttu-id="137f0-162">V současné době pouze <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, a <xref:System.Windows.Input.FocusNavigationDirection.Right> podporuje <xref:System.Windows.FrameworkElement.PredictFocus%2A>.</span><span class="sxs-lookup"><span data-stu-id="137f0-162">Currently, only <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, and <xref:System.Windows.Input.FocusNavigationDirection.Right> are supported by <xref:System.Windows.FrameworkElement.PredictFocus%2A>.</span></span>  
  
<a name="Focus_Events"></a>   
## <a name="focus-events"></a><span data-ttu-id="137f0-163">Fokus události</span><span class="sxs-lookup"><span data-stu-id="137f0-163">Focus Events</span></span>  
 <span data-ttu-id="137f0-164">Události související s fokus klávesnice jsou <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> a <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.</span><span class="sxs-lookup"><span data-stu-id="137f0-164">The events related to keyboard focus are <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> and <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.</span></span>  <span data-ttu-id="137f0-165">Události jsou definované jako připojené události na <xref:System.Windows.Input.Keyboard> třídy, ale jsou více snadno přístupné jako ekvivalentní směrované události na třídy base element.</span><span class="sxs-lookup"><span data-stu-id="137f0-165">The events are defined as attached events on the <xref:System.Windows.Input.Keyboard> class, but are more readily accessible as equivalent routed events on the base element classes.</span></span>  <span data-ttu-id="137f0-166">Další informace o událostech, najdete v článku [směrovány Přehled událostí](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="137f0-166">For more information about events, see the [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span></span>  
  
 <span data-ttu-id="137f0-167"><xref:System.Windows.Input.Keyboard.GotKeyboardFocus>se vyvolá, když elementu získává fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-167"><xref:System.Windows.Input.Keyboard.GotKeyboardFocus> is raised when the element obtains keyboard focus.</span></span>  <span data-ttu-id="137f0-168"><xref:System.Windows.Input.Keyboard.LostKeyboardFocus>se vyvolá, když element ztratí fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="137f0-168"><xref:System.Windows.Input.Keyboard.LostKeyboardFocus> is raised when the element loses keyboard focus.</span></span>  <span data-ttu-id="137f0-169">Pokud <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> události nebo <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> událost je zpracovávána a <xref:System.Windows.RoutedEventArgs.Handled%2A> je nastaven na `true`, pak se fokus nedojde ke změně.</span><span class="sxs-lookup"><span data-stu-id="137f0-169">If the <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> event or the <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> event is handled and <xref:System.Windows.RoutedEventArgs.Handled%2A> is set to `true`, then focus will not change.</span></span>  
  
 <span data-ttu-id="137f0-170">Následující příklad připojí <xref:System.Windows.UIElement.GotKeyboardFocus> a <xref:System.Windows.UIElement.LostKeyboardFocus> obslužných rutin událostí pro <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="137f0-170">The following example attaches <xref:System.Windows.UIElement.GotKeyboardFocus> and <xref:System.Windows.UIElement.LostKeyboardFocus> event handlers to a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 <span data-ttu-id="137f0-171">Když <xref:System.Windows.Controls.TextBox> získá fokus klávesnice <xref:System.Windows.Controls.Control.Background%2A> vlastnost <xref:System.Windows.Controls.TextBox> se změní na <xref:System.Windows.Media.Brushes.LightBlue%2A>.</span><span class="sxs-lookup"><span data-stu-id="137f0-171">When the <xref:System.Windows.Controls.TextBox> obtains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> property of the <xref:System.Windows.Controls.TextBox> is changed to <xref:System.Windows.Media.Brushes.LightBlue%2A>.</span></span>  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 <span data-ttu-id="137f0-172">Když <xref:System.Windows.Controls.TextBox> ztratí fokus klávesnice <xref:System.Windows.Controls.Control.Background%2A> vlastnost <xref:System.Windows.Controls.TextBox> se změní zpět na prázdné.</span><span class="sxs-lookup"><span data-stu-id="137f0-172">When the <xref:System.Windows.Controls.TextBox> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> property of the <xref:System.Windows.Controls.TextBox> is changed back to white.</span></span>  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 <span data-ttu-id="137f0-173">Události související s logické fokus jsou <xref:System.Windows.UIElement.GotFocus> a <xref:System.Windows.UIElement.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="137f0-173">The events related to logical focus are <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus>.</span></span>  <span data-ttu-id="137f0-174">Tyto události jsou definovány na <xref:System.Windows.Input.FocusManager> jako připojené události, ale <xref:System.Windows.Input.FocusManager> nevystavuje obálky události CLR.</span><span class="sxs-lookup"><span data-stu-id="137f0-174">These events are defined on the <xref:System.Windows.Input.FocusManager> as attached events, but the <xref:System.Windows.Input.FocusManager> does not expose CLR event wrappers.</span></span>  <span data-ttu-id="137f0-175"><xref:System.Windows.UIElement>a <xref:System.Windows.ContentElement> snadněji vystavit tyto události.</span><span class="sxs-lookup"><span data-stu-id="137f0-175"><xref:System.Windows.UIElement> and <xref:System.Windows.ContentElement> expose these events more conveniently.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="137f0-176">Viz také</span><span class="sxs-lookup"><span data-stu-id="137f0-176">See Also</span></span>  
 <xref:System.Windows.Input.FocusManager>  
 <xref:System.Windows.UIElement>  
 <xref:System.Windows.ContentElement>  
 [<span data-ttu-id="137f0-177">Vstupní – přehled</span><span class="sxs-lookup"><span data-stu-id="137f0-177">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="137f0-178">Přehled základní prvky</span><span class="sxs-lookup"><span data-stu-id="137f0-178">Base Elements Overview</span></span>](../../../../docs/framework/wpf/advanced/base-elements-overview.md)