---
title: "Postupy: Vytvoření doplňku tvořící uživatelské rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9151dd5fa36e3691361bcf6d7c7b281646982f3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a><span data-ttu-id="9974c-102">Postupy: Vytvoření doplňku tvořící uživatelské rozhraní</span><span class="sxs-lookup"><span data-stu-id="9974c-102">How to: Create an Add-In That Is a UI</span></span>
<span data-ttu-id="9974c-103">Tento příklad ukazuje, jak vytvořit doplněk, který je [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] který je hostován [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] samostatné aplikace.</span><span class="sxs-lookup"><span data-stu-id="9974c-103">This example shows how to create an add-in that is a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)][!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] which is hosted by a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application.</span></span>  
  
 <span data-ttu-id="9974c-104">Doplněk je [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] tedy [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uživatelský ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="9974c-104">The add-in is a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that is a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] user control.</span></span> <span data-ttu-id="9974c-105">Obsah uživatelského ovládacího prvku je jedné tlačítko, která po kliknutí na zobrazí okno se zprávou.</span><span class="sxs-lookup"><span data-stu-id="9974c-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="9974c-106">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Samostatné aplikace je hostitelem doplněk [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] jako obsah hlavního okna aplikace.</span><span class="sxs-lookup"><span data-stu-id="9974c-106">The [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application hosts the add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] as the content of the main application window.</span></span>  
  
 <span data-ttu-id="9974c-107">**Požadavky**</span><span class="sxs-lookup"><span data-stu-id="9974c-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="9974c-108">Tento příklad klade důraz [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] rozšíření [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelu, který povolit tento scénář a předpokládá následující:</span><span class="sxs-lookup"><span data-stu-id="9974c-108">This example highlights the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model that enable this scenario, and assumes the following:</span></span>  
  
-   <span data-ttu-id="9974c-109">Znalost [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] doplňku modelu, včetně kanálu, doplňku a vývoj hostitele.</span><span class="sxs-lookup"><span data-stu-id="9974c-109">Knowledge of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="9974c-110">Pokud jste obeznámeni s následujícími základními pojmy, najdete v části [doplňky a rozšíření](../../../../docs/framework/add-ins/index.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](../../../../docs/framework/add-ins/index.md).</span></span> <span data-ttu-id="9974c-111">Kurz, který ukazuje implementaci kanál, -v a hostitelskou aplikaci, najdete v části [návod: vytváření rozšiřitelné aplikace](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
-   <span data-ttu-id="9974c-112">Znalosti [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] rozšíření [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] doplňku model, který se nachází tady: [WPF doplňky přehled](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-112">Knowledge of the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, which can be found here:     [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9974c-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="9974c-113">Example</span></span>  
 <span data-ttu-id="9974c-114">Chcete-li vytvořit doplněk, který je [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] vyžaduje konkrétní kód pro každý segment kanálu v doplňku a hostitelskou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="9974c-114">To create an add-in that is a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="9974c-115">Implementace segmentu kanálu kontraktu</span><span class="sxs-lookup"><span data-stu-id="9974c-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="9974c-116">Pokud je doplněk [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], musí implementovat smlouvu pro doplněk <xref:System.AddIn.Contract.INativeHandleContract>.</span><span class="sxs-lookup"><span data-stu-id="9974c-116">When an add-in is a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], the contract for the add-in must implement <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="9974c-117">V příkladu `IWPFAddInContract` implementuje <xref:System.AddIn.Contract.INativeHandleContract>, jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="9974c-117">In the example, `IWPFAddInContract` implements <xref:System.AddIn.Contract.INativeHandleContract>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="9974c-118">Implementace segmentu kanál doplňku zobrazení</span><span class="sxs-lookup"><span data-stu-id="9974c-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="9974c-119">Protože doplněk je implementovaný jako podtřídou třídy <xref:System.Windows.FrameworkElement> typ tohoto zobrazení, musí taky podtřídami <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="9974c-119">Because the add-in is implemented as a subclass of the <xref:System.Windows.FrameworkElement> type, the add-in view must also subclass <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="9974c-120">Následující kód ukazuje zobrazení přidat smlouvy, které jsou implementované jako `WPFAddInView` třídy.</span><span class="sxs-lookup"><span data-stu-id="9974c-120">The following code shows the add-in view of the contract, implemented as the `WPFAddInView` class.</span></span>  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 <span data-ttu-id="9974c-121">Zde je zobrazení doplněk odvozený od <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="9974c-121">Here, the add-in view is derived from <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="9974c-122">V důsledku toho doplněk [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] také měl odvozovat od <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="9974c-122">Consequently, the add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] should also derive from <xref:System.Windows.Controls.UserControl>.</span></span>  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="9974c-123">Implementace segmentu kanálu přidat straně adaptéru</span><span class="sxs-lookup"><span data-stu-id="9974c-123">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="9974c-124">Když je kontrakt <xref:System.AddIn.Contract.INativeHandleContract>, doplněk je <xref:System.Windows.FrameworkElement> (jak je uvedeno podle segmentu kanálu zobrazení add-in).</span><span class="sxs-lookup"><span data-stu-id="9974c-124">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the add-in is a <xref:System.Windows.FrameworkElement> (as specified by the add-in view pipeline segment).</span></span> <span data-ttu-id="9974c-125">Proto <xref:System.Windows.FrameworkElement> musí být převedena na <xref:System.AddIn.Contract.INativeHandleContract> před překračuje hranice izolace.</span><span class="sxs-lookup"><span data-stu-id="9974c-125">Therefore, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="9974c-126">Tento pracovní provádí adaptér přidat straně voláním <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="9974c-126">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 <span data-ttu-id="9974c-127">V modelu doplňku kde doplněk, vrátí [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (najdete v části [vytvořit doplněk, vrátí uživatelského rozhraní](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), je adaptér převést <xref:System.Windows.FrameworkElement> k <xref:System.AddIn.Contract.INativeHandleContract> voláním <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span><span class="sxs-lookup"><span data-stu-id="9974c-127">In the add-in model where an add-in returns a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (see [Create an Add-In That Returns a UI](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), the add-in adapter converted the <xref:System.Windows.FrameworkElement> to an <xref:System.AddIn.Contract.INativeHandleContract> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span> <span data-ttu-id="9974c-128"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>je také nutné volat v tomto modelu, i když potřebujete implementovat metodu ze kterého chcete napsat kód pro volání.</span><span class="sxs-lookup"><span data-stu-id="9974c-128"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> must also be called in this model, although you need to implement a method from which to write the code to call it.</span></span> <span data-ttu-id="9974c-129">To uděláte přepsáním <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> a implementace kód, který volá <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> Pokud kód, který volá <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> očekává <xref:System.AddIn.Contract.INativeHandleContract>.</span><span class="sxs-lookup"><span data-stu-id="9974c-129">You do this by overriding <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> and implementing the code that calls <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> if the code that is calling <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is expecting an <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="9974c-130">V takovém případě bude volající adaptér straně hostitele, který je popsaná v následující dílčí části.</span><span class="sxs-lookup"><span data-stu-id="9974c-130">In this case, the caller will be the host-side adapter, which is covered in a subsequent subsection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9974c-131">Je také nutné přepsat <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> v tomto modelu k povolení přecházení mezi hostitelskou aplikaci pomocí tabulátoru [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a doplněk [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9974c-131">You also need to override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in this model to enable tabbing between host application [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] and add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> <span data-ttu-id="9974c-132">Další informace najdete v tématu "WPF Add-In omezení" v [WPF doplňky přehled](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9974c-132">For more information, see "WPF Add-In Limitations" in [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span></span>  
  
 <span data-ttu-id="9974c-133">Vzhledem k tomu, že je adaptér přidat straně implementuje rozhraní, která je odvozena od <xref:System.AddIn.Contract.INativeHandleContract>, musíte také implementovat <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, i když je to ignorovat při <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> přepsána.</span><span class="sxs-lookup"><span data-stu-id="9974c-133">Because the add-in-side adapter implements an interface that derives from <xref:System.AddIn.Contract.INativeHandleContract>, you also need to implement <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, although this is ignored when <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is overridden.</span></span>  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="9974c-134">Implementace segmentu hostitele zobrazení kanálu</span><span class="sxs-lookup"><span data-stu-id="9974c-134">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="9974c-135">V tomto modelu hostitelskou aplikaci obvykle očekává hostitelském zobrazení být <xref:System.Windows.FrameworkElement> podtřídy.</span><span class="sxs-lookup"><span data-stu-id="9974c-135">In this model, the host application typically expects the host view to be a <xref:System.Windows.FrameworkElement> subclass.</span></span> <span data-ttu-id="9974c-136">Adaptér hostitelské nutné převést <xref:System.AddIn.Contract.INativeHandleContract> k <xref:System.Windows.FrameworkElement> po <xref:System.AddIn.Contract.INativeHandleContract> protne hranice izolace.</span><span class="sxs-lookup"><span data-stu-id="9974c-136">The host-side adapter must convert the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> after the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary.</span></span> <span data-ttu-id="9974c-137">Metoda není volána hostitele aplikací získat <xref:System.Windows.FrameworkElement>, hostitelském zobrazení musí "vrátit" <xref:System.Windows.FrameworkElement> podle obsahující ho.</span><span class="sxs-lookup"><span data-stu-id="9974c-137">Because a method isn't being called by the host application to get the <xref:System.Windows.FrameworkElement>, the host view must "return" the <xref:System.Windows.FrameworkElement> by containing it.</span></span> <span data-ttu-id="9974c-138">V důsledku toho hostitelském zobrazení musí být odvozeny od podtřídou třídy <xref:System.Windows.FrameworkElement> , může obsahovat jiné [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], jako například <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="9974c-138">Consequently, the host view must derive from a subclass of <xref:System.Windows.FrameworkElement> that can contain other [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], such as <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="9974c-139">Následující kód ukazuje hostitelském zobrazení smlouvy, které jsou implementované jako `WPFAddInHostView` třídy.</span><span class="sxs-lookup"><span data-stu-id="9974c-139">The following code shows the host view of the contract, implemented as the `WPFAddInHostView` class.</span></span>  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="9974c-140">Implementace segmentu adaptér hostitelské kanálu</span><span class="sxs-lookup"><span data-stu-id="9974c-140">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="9974c-141">Když je kontrakt <xref:System.AddIn.Contract.INativeHandleContract>, očekává hostitelskou aplikaci <xref:System.Windows.Controls.UserControl> (jak je uvedeno v zobrazení hostitele).</span><span class="sxs-lookup"><span data-stu-id="9974c-141">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the host application expects a <xref:System.Windows.Controls.UserControl> (as specified by the host view).</span></span> <span data-ttu-id="9974c-142">V důsledku toho <xref:System.AddIn.Contract.INativeHandleContract> musí být převedena na <xref:System.Windows.FrameworkElement> po překročení meze hranici izolace, před nastavením jako obsah zobrazení hostitele (která je odvozena z <xref:System.Windows.Controls.UserControl>).</span><span class="sxs-lookup"><span data-stu-id="9974c-142">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary, before being set as content of the host view (which derives from <xref:System.Windows.Controls.UserControl>).</span></span>  
  
 <span data-ttu-id="9974c-143">Tento pracovní provádí adaptéru hostitelské, jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="9974c-143">This work is performed by the host-side adapter, as shown in the following code.</span></span>  
  
  
  
 <span data-ttu-id="9974c-144">Jak můžete vidět, získá adaptér hostitelské <xref:System.AddIn.Contract.INativeHandleContract> voláním adaptéru přidat straně <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> – metoda (to je bod kde <xref:System.AddIn.Contract.INativeHandleContract> protne hranic izolace).</span><span class="sxs-lookup"><span data-stu-id="9974c-144">As you can see, the host-side adapter acquires the <xref:System.AddIn.Contract.INativeHandleContract> by calling the add-in-side adapter's <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> method (this is the point where the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary).</span></span>  
  
 <span data-ttu-id="9974c-145">Adaptér hostitelské potom převede <xref:System.AddIn.Contract.INativeHandleContract> k <xref:System.Windows.FrameworkElement> voláním <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span><span class="sxs-lookup"><span data-stu-id="9974c-145">The host-side adapter then converts the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span></span> <span data-ttu-id="9974c-146">Nakonec <xref:System.Windows.FrameworkElement> je nastaven jako obsah zobrazení hostitele.</span><span class="sxs-lookup"><span data-stu-id="9974c-146">Finally, the <xref:System.Windows.FrameworkElement> is set as the content of the host view.</span></span>  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="9974c-147">Implementace v aplikaci</span><span class="sxs-lookup"><span data-stu-id="9974c-147">Implementing the Add-In</span></span>  
 <span data-ttu-id="9974c-148">Přidat straně adaptéru a přidat zobrazení na místě doplněk lze implementovat Odvozením ze zobrazení add-in, jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="9974c-148">With the add-in-side adapter and add-in view in place, the add-in can be implemented by deriving from the add-in view, as shown in the following code.</span></span>  
  
  
  
  
  
 <span data-ttu-id="9974c-149">Z tohoto příkladu vidíte zajímavé výhodou tohoto modelu: doplněk vývojáři stačí k implementaci doplňku (vzhledem k tomu, že je [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] i), nikoli třída doplňku i doplňku [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9974c-149">From this example, you can see one interesting benefit of this model: add-in developers only need to implement the add-in (since it is the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] as well), rather than both an add-in class and an add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="9974c-150">Implementace aplikace pro hostitele</span><span class="sxs-lookup"><span data-stu-id="9974c-150">Implementing the Host Application</span></span>  
 <span data-ttu-id="9974c-151">Adaptér hostitelské a hostitele zobrazení vytvořené hostitelskou aplikaci pomocí [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] model doplňku otevřít kanál a získat zobrazení hostitele add-in.</span><span class="sxs-lookup"><span data-stu-id="9974c-151">With the host-side adapter and host view created, the host application can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model to open the pipeline and acquire a host view of the add-in.</span></span> <span data-ttu-id="9974c-152">Tyto kroky jsou uvedeny v následující kód.</span><span class="sxs-lookup"><span data-stu-id="9974c-152">These steps are shown in the following code.</span></span>  
  
  
  
 <span data-ttu-id="9974c-153">Hostitelskou aplikaci používá typické [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] model doplňku kód pro aktivaci doplněk, který implicitně vrátí hostitelském zobrazení hostitelskou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="9974c-153">The host application uses typical [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model code to activate the add-in, which implicitly returns the host view to the host application.</span></span> <span data-ttu-id="9974c-154">Hostitelskou aplikaci následně zobrazí hostitelském zobrazení (což je <xref:System.Windows.Controls.UserControl>) z <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="9974c-154">The host application subsequently displays the host view (which is a <xref:System.Windows.Controls.UserControl>) from a <xref:System.Windows.Controls.Grid>.</span></span>  
  
 <span data-ttu-id="9974c-155">Kód pro zpracování interakce s doplněk [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] běží v doplňku na domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="9974c-155">The code for processing interactions with the add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] runs in the add-in's application domain.</span></span> <span data-ttu-id="9974c-156">Tyto akce patří:</span><span class="sxs-lookup"><span data-stu-id="9974c-156">These interactions include the following:</span></span>  
  
-   <span data-ttu-id="9974c-157">Zpracování <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> událostí.</span><span class="sxs-lookup"><span data-stu-id="9974c-157">Handling the <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
-   <span data-ttu-id="9974c-158">Zobrazuje <xref:System.Windows.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="9974c-158">Showing the <xref:System.Windows.MessageBox>.</span></span>  
  
 <span data-ttu-id="9974c-159">Tato aktivita je naprosto izolované od hostitelskou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="9974c-159">This activity is completely isolated from the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9974c-160">Viz také</span><span class="sxs-lookup"><span data-stu-id="9974c-160">See Also</span></span>  
 [<span data-ttu-id="9974c-161">Doplňky a rozšíření</span><span class="sxs-lookup"><span data-stu-id="9974c-161">Add-ins and Extensibility</span></span>](../../../../docs/framework/add-ins/index.md)  
 [<span data-ttu-id="9974c-162">Přehled doplňky WPF</span><span class="sxs-lookup"><span data-stu-id="9974c-162">WPF Add-Ins Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)