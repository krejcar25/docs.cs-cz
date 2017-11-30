---
title: "Přehled nabídky"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81611e7c5f509314b10e3188106870bdc67dfb0e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="menu-overview"></a><span data-ttu-id="9a010-102">Přehled nabídky</span><span class="sxs-lookup"><span data-stu-id="9a010-102">Menu Overview</span></span>
<span data-ttu-id="9a010-103"><xref:System.Windows.Controls.Menu> Třída umožňuje uspořádat prvky přidružené příkazy a obslužné rutiny událostí v hierarchickém pořadí.</span><span class="sxs-lookup"><span data-stu-id="9a010-103">The <xref:System.Windows.Controls.Menu> class enables you to organize elements associated with commands and event handlers in a hierarchical order.</span></span> <span data-ttu-id="9a010-104">Každý <xref:System.Windows.Controls.Menu> element obsahuje kolekci <xref:System.Windows.Controls.MenuItem> elementy.</span><span class="sxs-lookup"><span data-stu-id="9a010-104">Each <xref:System.Windows.Controls.Menu> element contains a collection of <xref:System.Windows.Controls.MenuItem> elements.</span></span>  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a><span data-ttu-id="9a010-105">Menu – ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="9a010-105">Menu Control</span></span>  
 <span data-ttu-id="9a010-106"><xref:System.Windows.Controls.Menu> Řízení představuje seznam položek, které určují příkazy nebo možnosti pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="9a010-106">The <xref:System.Windows.Controls.Menu> control presents a list of items that specify commands or options for an application.</span></span> <span data-ttu-id="9a010-107">Obvykle, kliknutím <xref:System.Windows.Controls.MenuItem> otevře podnabídky nebo způsobí, že aplikaci k provedení příkazu.</span><span class="sxs-lookup"><span data-stu-id="9a010-107">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a><span data-ttu-id="9a010-108">Vytváření nabídek</span><span class="sxs-lookup"><span data-stu-id="9a010-108">Creating Menus</span></span>  
 <span data-ttu-id="9a010-109">Následující příklad vytvoří <xref:System.Windows.Controls.Menu> pro práci s textem v <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="9a010-109">The following example creates a <xref:System.Windows.Controls.Menu> to manipulate text in a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="9a010-110"><xref:System.Windows.Controls.Menu> Obsahuje <xref:System.Windows.Controls.MenuItem> objekty, které používají <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, a <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> vlastnosti a <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, a <xref:System.Windows.Controls.MenuItem.Click> události.</span><span class="sxs-lookup"><span data-stu-id="9a010-110">The <xref:System.Windows.Controls.Menu> contains <xref:System.Windows.Controls.MenuItem> objects that use the <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, and <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> properties and the <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, and <xref:System.Windows.Controls.MenuItem.Click> events.</span></span>  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a><span data-ttu-id="9a010-111">Vlastnost MenuItems pomocí klávesové zkratky</span><span class="sxs-lookup"><span data-stu-id="9a010-111">MenuItems with Keyboard Shortcuts</span></span>  
 <span data-ttu-id="9a010-112">Klávesové zkratky jsou kombinace znaků, které lze zadat pomocí klávesnice k vyvolání <xref:System.Windows.Controls.Menu> příkazy.</span><span class="sxs-lookup"><span data-stu-id="9a010-112">Keyboard shortcuts are character combinations that can be entered with the keyboard to invoke <xref:System.Windows.Controls.Menu> commands.</span></span> <span data-ttu-id="9a010-113">Například na zástupce **kopie** je CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="9a010-113">For example, the shortcut for **Copy** is CTRL+C.</span></span> <span data-ttu-id="9a010-114">Existují dvě vlastnosti se používat s klávesové zkratky a položky nabídky –<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> nebo <xref:System.Windows.Controls.MenuItem.Command%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a010-114">There are two properties to use with keyboard shortcuts and menu items —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> or <xref:System.Windows.Controls.MenuItem.Command%2A>.</span></span>  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a><span data-ttu-id="9a010-115">InputGestureText</span><span class="sxs-lookup"><span data-stu-id="9a010-115">InputGestureText</span></span>  
 <span data-ttu-id="9a010-116">Následující příklad ukazuje, jak používat <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> vlastnost přiřadit text klávesové zkratky pro <xref:System.Windows.Controls.MenuItem> ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="9a010-116">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> property to assign keyboard shortcut text to <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="9a010-117">To jenom umístí klávesovou zkratku položku nabídky.</span><span class="sxs-lookup"><span data-stu-id="9a010-117">This only places the keyboard shortcut in the menu item.</span></span>  <span data-ttu-id="9a010-118">Příkaz s nespojí <xref:System.Windows.Controls.MenuItem>.</span><span class="sxs-lookup"><span data-stu-id="9a010-118">It does not associate the command with the <xref:System.Windows.Controls.MenuItem>.</span></span> <span data-ttu-id="9a010-119">Aplikace musí zpracovat vstup uživatele k provedení akce.</span><span class="sxs-lookup"><span data-stu-id="9a010-119">The application must handle the user's input to carry out the action.</span></span>  
  
 [!code-xaml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a><span data-ttu-id="9a010-120">Příkaz</span><span class="sxs-lookup"><span data-stu-id="9a010-120">Command</span></span>  
 <span data-ttu-id="9a010-121">Následující příklad ukazuje, jak používat <xref:System.Windows.Controls.MenuItem.Command%2A> vlastnost pro přidružení **otevřete** a **Uložit** příkazy pomocí <xref:System.Windows.Controls.MenuItem> ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="9a010-121">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.Command%2A> property to associate the **Open** and **Save** commands with <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="9a010-122">Ne jenom vlastnost příkazu přidružit příkaz se <xref:System.Windows.Controls.MenuItem>, ale také poskytuje vstupní gesto text, který chcete použít jako zástupce.</span><span class="sxs-lookup"><span data-stu-id="9a010-122">Not only does the command property associate a command with a <xref:System.Windows.Controls.MenuItem>, but it also supplies the input gesture text to use as a shortcut.</span></span>  
  
 [!code-xaml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <span data-ttu-id="9a010-123"><xref:System.Windows.Controls.MenuItem> Třída také obsahuje <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> vlastnosti, která určuje elementu, kde dochází k příkazu.</span><span class="sxs-lookup"><span data-stu-id="9a010-123">The <xref:System.Windows.Controls.MenuItem> class also has a <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> property, which specifies the element where the command occurs.</span></span> <span data-ttu-id="9a010-124">Pokud <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> není nastaven, elementu, který má právě fokus klávesnice přijme příkaz.</span><span class="sxs-lookup"><span data-stu-id="9a010-124">If <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> is not set, the element that has keyboard focus receives the command.</span></span> <span data-ttu-id="9a010-125">Další informace o příkazech najdete v tématu [tvorba příkazů přehled](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a010-125">For more information about commands, see [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a><span data-ttu-id="9a010-126">Nabídky stylů</span><span class="sxs-lookup"><span data-stu-id="9a010-126">Menu Styling</span></span>  
 <span data-ttu-id="9a010-127">S stylů ovládacího prvku, můžete výrazně změnit vzhled a chování <xref:System.Windows.Controls.Menu> ovládacím prvkům bez nutnosti psaní vlastního ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="9a010-127">With control styling, you can dramatically change the appearance and behavior of <xref:System.Windows.Controls.Menu> controls without having to write a custom control.</span></span> <span data-ttu-id="9a010-128">Kromě nastavení vizuálních vlastností, můžete také použít <xref:System.Windows.Style> na jednotlivé části ovládacího prvku změnit chování částí ovládacího prvku prostřednictvím vlastnosti, nebo přidání dalších částí nebo změna rozložení ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="9a010-128">In addition to setting visual properties, you can also apply a <xref:System.Windows.Style> to individual parts of a control, change the behavior of parts of the control through properties, or add additional parts or change the layout of a control.</span></span> <span data-ttu-id="9a010-129">Následující příklady ukazují několik způsobů, jak přidat <xref:System.Windows.Style> k <xref:System.Windows.Controls.Menu> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="9a010-129">The following examples demonstrate several ways to add a <xref:System.Windows.Style> to a <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 <span data-ttu-id="9a010-130">V prvním příkladu kód definuje <xref:System.Windows.Style> názvem `Simple` který ukazuje, jak používat aktuální nastavení systému ve vašem stylu.</span><span class="sxs-lookup"><span data-stu-id="9a010-130">The first code example defines a <xref:System.Windows.Style> called `Simple` that shows how to use the current system settings in your style.</span></span> <span data-ttu-id="9a010-131">Kód přiřadí barvu `MenuHighlightBrush` jako barva pozadí v nabídce a `MenuTextBrush` jako barvu popředí v nabídce.</span><span class="sxs-lookup"><span data-stu-id="9a010-131">The code assigns the color of the `MenuHighlightBrush` as the menu's background color and the `MenuTextBrush` as the menu's foreground color.</span></span> <span data-ttu-id="9a010-132">Všimněte si, můžete k přiřazení stopy použít klíčů prostředku.</span><span class="sxs-lookup"><span data-stu-id="9a010-132">Notice that you use resource keys to assign the brushes.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 <span data-ttu-id="9a010-133">Následující ukázkové používá <xref:System.Windows.Trigger> elementy, které vám umožní změnit vzhled <xref:System.Windows.Controls.MenuItem> v reakci na události na <xref:System.Windows.Controls.Menu>.</span><span class="sxs-lookup"><span data-stu-id="9a010-133">The following sample uses <xref:System.Windows.Trigger> elements that enable you to change the appearance of a <xref:System.Windows.Controls.MenuItem> in response to events that occur on the <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="9a010-134">Při přesunutí myši <xref:System.Windows.Controls.Menu>, barvu popředí a vlastnosti písma položek nabídky změnit.</span><span class="sxs-lookup"><span data-stu-id="9a010-134">When you move the mouse over the <xref:System.Windows.Controls.Menu>, the foreground color and the font characteristics of the menu items change.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9a010-135">Viz také</span><span class="sxs-lookup"><span data-stu-id="9a010-135">See Also</span></span>  
 [<span data-ttu-id="9a010-136">Ukázka galerie ovládacích prvků grafického subsystému WPF</span><span class="sxs-lookup"><span data-stu-id="9a010-136">WPF Controls Gallery Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160053)