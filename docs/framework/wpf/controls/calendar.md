---
title: "Kalendář"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 857f6b3be1467ec54fd27c76679279c0d0960690
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="calendar"></a><span data-ttu-id="0843a-102">Kalendář</span><span class="sxs-lookup"><span data-stu-id="0843a-102">Calendar</span></span>
<span data-ttu-id="0843a-103">Kalendář umožňuje uživateli vybrat datum pomocí zobrazení visual kalendáře.</span><span class="sxs-lookup"><span data-stu-id="0843a-103">A calendar enables a user to select a date by using a visual calendar display.</span></span>  
  
 <span data-ttu-id="0843a-104">A <xref:System.Windows.Controls.Calendar> řízení lze použít samostatně nebo jako součást rozevíracího seznamu <xref:System.Windows.Controls.DatePicker> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="0843a-104">A <xref:System.Windows.Controls.Calendar> control can be used on its own, or as a drop-down part of a <xref:System.Windows.Controls.DatePicker> control.</span></span> <span data-ttu-id="0843a-105">Další informace naleznete v tématu <xref:System.Windows.Controls.DatePicker>.</span><span class="sxs-lookup"><span data-stu-id="0843a-105">For more information, see <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="0843a-106">Následující obrázek ukazuje dva <xref:System.Windows.Controls.Calendar> ovládací prvky a s výběry a přerušení spojení data bez.</span><span class="sxs-lookup"><span data-stu-id="0843a-106">The following illustration shows two <xref:System.Windows.Controls.Calendar> controls, one with selections and blackout dates and one without.</span></span>  
  
 <span data-ttu-id="0843a-107">![Ovládací prvky kalendáře](../../../../docs/framework/wpf/controls/media/ndp-calendarcontrols.png "NDP_CalendarControls")</span><span class="sxs-lookup"><span data-stu-id="0843a-107">![Calendar controls](../../../../docs/framework/wpf/controls/media/ndp-calendarcontrols.png "NDP_CalendarControls")</span></span>  
<span data-ttu-id="0843a-108">Ovládací prvky kalendáře</span><span class="sxs-lookup"><span data-stu-id="0843a-108">Calendar controls</span></span>  
  
 <span data-ttu-id="0843a-109">Následující tabulka obsahuje informace o úlohách, které jsou obvykle přidruženy <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="0843a-109">The following table provides information about tasks that are typically associated with the <xref:System.Windows.Controls.Calendar>.</span></span>  
  
|<span data-ttu-id="0843a-110">Úloha</span><span class="sxs-lookup"><span data-stu-id="0843a-110">Task</span></span>|<span data-ttu-id="0843a-111">Implementace</span><span class="sxs-lookup"><span data-stu-id="0843a-111">Implementation</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="0843a-112">Zadat data, není k dispozici.</span><span class="sxs-lookup"><span data-stu-id="0843a-112">Specify dates that cannot be selected.</span></span>|<span data-ttu-id="0843a-113">Použití <xref:System.Windows.Controls.Calendar.BlackoutDates%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="0843a-113">Use the <xref:System.Windows.Controls.Calendar.BlackoutDates%2A> property.</span></span>|  
|<span data-ttu-id="0843a-114">Máte <xref:System.Windows.Controls.Calendar> zobrazení měsíce, celý rok nebo deset.</span><span class="sxs-lookup"><span data-stu-id="0843a-114">Have the <xref:System.Windows.Controls.Calendar> display a month, an entire year, or a decade.</span></span>|<span data-ttu-id="0843a-115">Nastavte <xref:System.Windows.Controls.Calendar.DisplayMode%2A> vlastnost na měsíc, rok nebo desetiletí.</span><span class="sxs-lookup"><span data-stu-id="0843a-115">Set the <xref:System.Windows.Controls.Calendar.DisplayMode%2A> property to Month, Year, or Decade.</span></span>|  
|<span data-ttu-id="0843a-116">Zadejte, jestli může uživatel vybrat datum, rozsah kalendářních dat nebo víc rozsahů kalendářních dat.</span><span class="sxs-lookup"><span data-stu-id="0843a-116">Specify whether the user can select a date, a range of dates, or multiple ranges of dates.</span></span>|<span data-ttu-id="0843a-117">Použití <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="0843a-117">Use the <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.</span></span>|  
|<span data-ttu-id="0843a-118">Zadejte rozsah dat, který <xref:System.Windows.Controls.Calendar> zobrazí.</span><span class="sxs-lookup"><span data-stu-id="0843a-118">Specify the range of dates that the <xref:System.Windows.Controls.Calendar> displays.</span></span>|<span data-ttu-id="0843a-119">Použití <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> a <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A> vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="0843a-119">Use the <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> and <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A> properties.</span></span>|  
|<span data-ttu-id="0843a-120">Zadejte, zda je označený aktuální datum.</span><span class="sxs-lookup"><span data-stu-id="0843a-120">Specify whether the current date is highlighted.</span></span>|<span data-ttu-id="0843a-121">Použití <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="0843a-121">Use the <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> property.</span></span> <span data-ttu-id="0843a-122">Ve výchozím nastavení <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> je `true`.</span><span class="sxs-lookup"><span data-stu-id="0843a-122">By default, <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> is `true`.</span></span>|  
|<span data-ttu-id="0843a-123">Změna velikosti <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="0843a-123">Change the size of the <xref:System.Windows.Controls.Calendar>.</span></span>|<span data-ttu-id="0843a-124">Použití <xref:System.Windows.Controls.Viewbox> nebo nastavte <xref:System.Windows.FrameworkElement.LayoutTransform%2A> vlastnosti <xref:System.Windows.Media.ScaleTransform>.</span><span class="sxs-lookup"><span data-stu-id="0843a-124">Use a <xref:System.Windows.Controls.Viewbox> or set the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property to a <xref:System.Windows.Media.ScaleTransform>.</span></span> <span data-ttu-id="0843a-125">Všimněte si, že pokud nastavíte <xref:System.Windows.FrameworkElement.Width%2A> a <xref:System.Windows.FrameworkElement.Height%2A> vlastnosti <xref:System.Windows.Controls.Calendar>, skutečný kalendáře nezmění jeho velikost.</span><span class="sxs-lookup"><span data-stu-id="0843a-125">Note that if you set the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of a <xref:System.Windows.Controls.Calendar>, the actual calendar does not change its size.</span></span>|  
  
 <span data-ttu-id="0843a-126"><xref:System.Windows.Controls.Calendar> Řízení poskytuje základní navigaci pomocí myši nebo klávesnice.</span><span class="sxs-lookup"><span data-stu-id="0843a-126">The <xref:System.Windows.Controls.Calendar> control provides basic navigation using either the mouse or keyboard.</span></span> <span data-ttu-id="0843a-127">Následující tabulka shrnuje klávesnice navigace.</span><span class="sxs-lookup"><span data-stu-id="0843a-127">The following table summarizes keyboard navigation.</span></span>  
  
|<span data-ttu-id="0843a-128">Kombinace klíče</span><span class="sxs-lookup"><span data-stu-id="0843a-128">Key Combination</span></span>|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|<span data-ttu-id="0843a-129">Akce</span><span class="sxs-lookup"><span data-stu-id="0843a-129">Action</span></span>|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|<span data-ttu-id="0843a-130">ŠIPKA</span><span class="sxs-lookup"><span data-stu-id="0843a-130">ARROW</span></span>|<xref:System.Windows.Controls.CalendarMode.Month>|<span data-ttu-id="0843a-131">Změny <xref:System.Windows.Controls.Calendar.SelectedDate%2A> vlastnost Pokud <xref:System.Windows.Controls.Calendar.SelectionMode%2A> vlastnost není nastavena na <xref:System.Windows.Controls.CalendarSelectionMode.None>.</span><span class="sxs-lookup"><span data-stu-id="0843a-131">Changes the <xref:System.Windows.Controls.Calendar.SelectedDate%2A> property if the <xref:System.Windows.Controls.Calendar.SelectionMode%2A> property is not set to <xref:System.Windows.Controls.CalendarSelectionMode.None>.</span></span>|  
|<span data-ttu-id="0843a-132">ŠIPKA</span><span class="sxs-lookup"><span data-stu-id="0843a-132">ARROW</span></span>|<xref:System.Windows.Controls.CalendarMode.Year>|<span data-ttu-id="0843a-133">Změní měsíc <xref:System.Windows.Controls.Calendar.DisplayDate%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="0843a-133">Changes the month of the <xref:System.Windows.Controls.Calendar.DisplayDate%2A> property.</span></span> <span data-ttu-id="0843a-134">Všimněte si, že <xref:System.Windows.Controls.Calendar.SelectedDate%2A> se nemění.</span><span class="sxs-lookup"><span data-stu-id="0843a-134">Note that the <xref:System.Windows.Controls.Calendar.SelectedDate%2A> does not change.</span></span>|  
|<span data-ttu-id="0843a-135">ŠIPKA</span><span class="sxs-lookup"><span data-stu-id="0843a-135">ARROW</span></span>|<xref:System.Windows.Controls.CalendarMode.Decade>|<span data-ttu-id="0843a-136">Rok se změní <xref:System.Windows.Controls.Calendar.DisplayDate%2A>.</span><span class="sxs-lookup"><span data-stu-id="0843a-136">Changes the year of the <xref:System.Windows.Controls.Calendar.DisplayDate%2A>.</span></span> <span data-ttu-id="0843a-137">Všimněte si, že <xref:System.Windows.Controls.Calendar.SelectedDate%2A> se nemění.</span><span class="sxs-lookup"><span data-stu-id="0843a-137">Note that the <xref:System.Windows.Controls.Calendar.SelectedDate%2A> does not change.</span></span>|  
|<span data-ttu-id="0843a-138">SHIFT + ŠIPKA</span><span class="sxs-lookup"><span data-stu-id="0843a-138">SHIFT+ARROW</span></span>|<xref:System.Windows.Controls.CalendarMode.Month>|<span data-ttu-id="0843a-139">Pokud <xref:System.Windows.Controls.Calendar.SelectionMode%2A> není nastavený na <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> nebo <xref:System.Windows.Controls.CalendarSelectionMode.None>, rozšiřuje rozsah dat, vybrané.</span><span class="sxs-lookup"><span data-stu-id="0843a-139">If <xref:System.Windows.Controls.Calendar.SelectionMode%2A> is not set to <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> or <xref:System.Windows.Controls.CalendarSelectionMode.None>, extends the range of selected dates.</span></span>|  
|<span data-ttu-id="0843a-140">DOMOVSKÉ</span><span class="sxs-lookup"><span data-stu-id="0843a-140">HOME</span></span>|<xref:System.Windows.Controls.CalendarMode.Month>|<span data-ttu-id="0843a-141">Změny <xref:System.Windows.Controls.Calendar.SelectedDate%2A> na první den aktuálního měsíce.</span><span class="sxs-lookup"><span data-stu-id="0843a-141">Changes the <xref:System.Windows.Controls.Calendar.SelectedDate%2A> to the first day of the current month.</span></span>|  
|<span data-ttu-id="0843a-142">DOMOVSKÉ</span><span class="sxs-lookup"><span data-stu-id="0843a-142">HOME</span></span>|<xref:System.Windows.Controls.CalendarMode.Year>|<span data-ttu-id="0843a-143">Změní měsíc <xref:System.Windows.Controls.Calendar.DisplayDate%2A> první měsíc v roce.</span><span class="sxs-lookup"><span data-stu-id="0843a-143">Changes the month of the <xref:System.Windows.Controls.Calendar.DisplayDate%2A> to the first month of the year.</span></span> <span data-ttu-id="0843a-144"><xref:System.Windows.Controls.Calendar.SelectedDate%2A> Se nemění.</span><span class="sxs-lookup"><span data-stu-id="0843a-144">The <xref:System.Windows.Controls.Calendar.SelectedDate%2A> does not change.</span></span>|  
|<span data-ttu-id="0843a-145">DOMOVSKÉ</span><span class="sxs-lookup"><span data-stu-id="0843a-145">HOME</span></span>|<xref:System.Windows.Controls.CalendarMode.Decade>|<span data-ttu-id="0843a-146">Rok se změní <xref:System.Windows.Controls.Calendar.DisplayDate%2A> k prvnímu roku desetiletí.</span><span class="sxs-lookup"><span data-stu-id="0843a-146">Changes the year of the <xref:System.Windows.Controls.Calendar.DisplayDate%2A> to the first year of the decade.</span></span> <span data-ttu-id="0843a-147"><xref:System.Windows.Controls.Calendar.SelectedDate%2A> Se nemění.</span><span class="sxs-lookup"><span data-stu-id="0843a-147">The <xref:System.Windows.Controls.Calendar.SelectedDate%2A> does not change.</span></span>|  
|<span data-ttu-id="0843a-148">END</span><span class="sxs-lookup"><span data-stu-id="0843a-148">END</span></span>|<xref:System.Windows.Controls.CalendarMode.Month>|<span data-ttu-id="0843a-149">Změny <xref:System.Windows.Controls.Calendar.SelectedDate%2A> na poslední den aktuálního měsíce.</span><span class="sxs-lookup"><span data-stu-id="0843a-149">Changes the <xref:System.Windows.Controls.Calendar.SelectedDate%2A> to the last day of the current month.</span></span>|  
|<span data-ttu-id="0843a-150">END</span><span class="sxs-lookup"><span data-stu-id="0843a-150">END</span></span>|<xref:System.Windows.Controls.CalendarMode.Year>|<span data-ttu-id="0843a-151">Změní měsíc <xref:System.Windows.Controls.Calendar.DisplayDate%2A> poslední měsíc v roce.</span><span class="sxs-lookup"><span data-stu-id="0843a-151">Changes the month of the <xref:System.Windows.Controls.Calendar.DisplayDate%2A> to the last month of the year.</span></span> <span data-ttu-id="0843a-152"><xref:System.Windows.Controls.Calendar.SelectedDate%2A> Se nemění.</span><span class="sxs-lookup"><span data-stu-id="0843a-152">The <xref:System.Windows.Controls.Calendar.SelectedDate%2A> does not change.</span></span>|  
|<span data-ttu-id="0843a-153">END</span><span class="sxs-lookup"><span data-stu-id="0843a-153">END</span></span>|<xref:System.Windows.Controls.CalendarMode.Decade>|<span data-ttu-id="0843a-154">Rok se změní <xref:System.Windows.Controls.Calendar.DisplayDate%2A> na poslední rok desetiletí.</span><span class="sxs-lookup"><span data-stu-id="0843a-154">Changes the year of the <xref:System.Windows.Controls.Calendar.DisplayDate%2A> to the last year of the decade.</span></span> <span data-ttu-id="0843a-155"><xref:System.Windows.Controls.Calendar.SelectedDate%2A> Se nemění.</span><span class="sxs-lookup"><span data-stu-id="0843a-155">The <xref:System.Windows.Controls.Calendar.SelectedDate%2A> does not change.</span></span>|  
|<span data-ttu-id="0843a-156">CTRL + ŠIPKA NAHORU</span><span class="sxs-lookup"><span data-stu-id="0843a-156">CTRL+UP ARROW</span></span>|<span data-ttu-id="0843a-157">všechny</span><span class="sxs-lookup"><span data-stu-id="0843a-157">Any</span></span>|<span data-ttu-id="0843a-158">Přepne do dalšího větší <xref:System.Windows.Controls.Calendar.DisplayMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="0843a-158">Switches to the next larger <xref:System.Windows.Controls.Calendar.DisplayMode%2A>.</span></span> <span data-ttu-id="0843a-159">Pokud <xref:System.Windows.Controls.Calendar.DisplayMode%2A> je již <xref:System.Windows.Controls.CalendarMode.Decade>, žádná akce.</span><span class="sxs-lookup"><span data-stu-id="0843a-159">If <xref:System.Windows.Controls.Calendar.DisplayMode%2A> is already <xref:System.Windows.Controls.CalendarMode.Decade>, no action.</span></span>|  
|<span data-ttu-id="0843a-160">CTRL + ŠIPKA DOLŮ</span><span class="sxs-lookup"><span data-stu-id="0843a-160">CTRL+DOWN ARROW</span></span>|<span data-ttu-id="0843a-161">všechny</span><span class="sxs-lookup"><span data-stu-id="0843a-161">Any</span></span>|<span data-ttu-id="0843a-162">Přepne do dalšího menší <xref:System.Windows.Controls.Calendar.DisplayMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="0843a-162">Switches to the next smaller <xref:System.Windows.Controls.Calendar.DisplayMode%2A>.</span></span> <span data-ttu-id="0843a-163">Pokud <xref:System.Windows.Controls.Calendar.DisplayMode%2A> je již <xref:System.Windows.Controls.CalendarMode.Month>, žádná akce.</span><span class="sxs-lookup"><span data-stu-id="0843a-163">If <xref:System.Windows.Controls.Calendar.DisplayMode%2A> is already <xref:System.Windows.Controls.CalendarMode.Month>, no action.</span></span>|  
|<span data-ttu-id="0843a-164">MEZERNÍK nebo ENTER</span><span class="sxs-lookup"><span data-stu-id="0843a-164">SPACEBAR or ENTER</span></span>|<span data-ttu-id="0843a-165"><xref:System.Windows.Controls.CalendarMode.Year>nebo<xref:System.Windows.Controls.CalendarMode.Decade></span><span class="sxs-lookup"><span data-stu-id="0843a-165"><xref:System.Windows.Controls.CalendarMode.Year> or <xref:System.Windows.Controls.CalendarMode.Decade></span></span>|<span data-ttu-id="0843a-166">Přepínače <xref:System.Windows.Controls.Calendar.DisplayMode%2A> k <xref:System.Windows.Controls.CalendarMode.Month> nebo <xref:System.Windows.Controls.CalendarMode.Year> reprezentována cílených položky.</span><span class="sxs-lookup"><span data-stu-id="0843a-166">Switches <xref:System.Windows.Controls.Calendar.DisplayMode%2A> to the <xref:System.Windows.Controls.CalendarMode.Month> or <xref:System.Windows.Controls.CalendarMode.Year> represented by focused item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0843a-167">Viz také</span><span class="sxs-lookup"><span data-stu-id="0843a-167">See Also</span></span>  
 [<span data-ttu-id="0843a-168">Ovládací prvky</span><span class="sxs-lookup"><span data-stu-id="0843a-168">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="0843a-169">Stylů a ukázka</span><span class="sxs-lookup"><span data-stu-id="0843a-169">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)