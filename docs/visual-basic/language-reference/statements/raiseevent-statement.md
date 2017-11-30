---
title: "RaiseEvent – příkaz"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2575598577820bd7a72fae2d9b8ba52978f5952d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="raiseevent-statement"></a><span data-ttu-id="b0ff4-102">RaiseEvent – příkaz</span><span class="sxs-lookup"><span data-stu-id="b0ff4-102">RaiseEvent Statement</span></span>
<span data-ttu-id="b0ff4-103">Aktivuje událost deklarovat na úrovni modulu v rámci třídy, formulář nebo dokumentu.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ff4-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b0ff4-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="b0ff4-105">Součásti</span><span class="sxs-lookup"><span data-stu-id="b0ff4-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="b0ff4-106">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-106">Required.</span></span> <span data-ttu-id="b0ff4-107">Název události k aktivaci.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="b0ff4-108">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-108">Optional.</span></span> <span data-ttu-id="b0ff4-109">Čárkami oddělený seznam proměnných, pole nebo výrazy.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="b0ff4-110">`argumentlist` Argument musí být uzavřena v závorkách.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="b0ff4-111">Pokud neexistují žádné argumenty, musí být vynechána závorkách.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0ff4-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b0ff4-112">Remarks</span></span>  
 <span data-ttu-id="b0ff4-113">Požadované `eventname` je název události deklarované v rámci modulu.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="b0ff4-114">Postupuje proměnné zásady vytváření názvů jazyka Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="b0ff4-115">Pokud událost nebyla deklarována v rámci modul, ve kterém se vyvolá, dojde k chybě.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="b0ff4-116">Následující fragment kódu ukazuje deklaraci události a postup, ve které je událost vyvolána.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 <span data-ttu-id="b0ff4-117">Nemůžete použít `RaiseEvent` umožňuje aktivovat události, které nejsou výslovně deklarované v modulu.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="b0ff4-118">Například zdědí všechny formuláře <xref:System.Windows.Forms.Control.Click> událost z <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, nelze zvýšit, pomocí `RaiseEvent` v odvozených formuláře.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="b0ff4-119">Pokud je deklarovat `Click` událostí v modulu formuláře ho shadows formuláře vlastní <xref:System.Windows.Forms.Control.Click> událostí.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="b0ff4-120">Přesto můžete vyvolat formuláře <xref:System.Windows.Forms.Control.Click> událostí voláním <xref:System.Windows.Forms.Control.OnClick%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="b0ff4-121">Ve výchozím nastavení vyvolá událost definované v jazyce Visual Basic jeho obslužné rutiny událostí v pořadí, že jsou navázat připojení.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="b0ff4-122">Protože události může mít `ByRef` parametry, proces, který se připojuje pozdní obdržet parametry, které se změnily starší obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="b0ff4-123">Po spuštění obslužné rutiny události, ovládací prvek se vrátí k podprogramu, který vyvolal událost.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0ff4-124">Pro nesdílené události by neměly být vyvolány v konstruktoru třídy, ve které jsou deklarované.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="b0ff4-125">I když tyto události nezpůsobí běhové chyby, se nemusí být zachytila obslužné rutiny související události.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="b0ff4-126">Použití `Shared` modifikátor vytvoření sdíleného události, pokud je nutné vyvolat událost z konstruktoru.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0ff4-127">Výchozí chování události můžete změnit tak, že definujete vlastní události.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="b0ff4-128">Pro vlastní události `RaiseEvent` příkaz volá události `RaiseEvent` přistupujícího objektu.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="b0ff4-129">Další informace o vlastních událostí najdete v tématu [Event – příkaz](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b0ff4-129">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0ff4-130">Příklad</span><span class="sxs-lookup"><span data-stu-id="b0ff4-130">Example</span></span>  
 <span data-ttu-id="b0ff4-131">Následující příklad používá události počítat dolů sekund z 10 na hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="b0ff4-132">Kód ukazuje několik událostí související metody, vlastnosti a příkazy, včetně `RaiseEvent` příkaz.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="b0ff4-133">Třída, která vyvolá událost, je zdroj události a jsou metody, které zpracovat událost obslužné rutiny událostí.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="b0ff4-134">Zdroje událostí může mít více obslužných rutin pro události, které generuje.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="b0ff4-135">Pokud třída vyvolá událost, že událost se vyvolá při každou třídu, která se rozhodl zpracovat události pro tuto instanci objektu.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="b0ff4-136">V příkladu se rovněž používá formulář (`Form1`) s tlačítkem na (`Button1`) a textového pole (`TextBox1`).</span><span class="sxs-lookup"><span data-stu-id="b0ff4-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="b0ff4-137">Když kliknete na tlačítko, textové pole první zobrazí odpočítávání z 10 na 0 sekund.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="b0ff4-138">Po uplynutí doby úplné (10 sekund), zobrazí první textové pole, "Hotovo".</span><span class="sxs-lookup"><span data-stu-id="b0ff4-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="b0ff4-139">Kód pro `Form1` Určuje počáteční a terminálu stavy formuláře.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="b0ff4-140">Obsahuje taky kód spustit, když jsou vyvolány události.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="b0ff4-141">Chcete-li použít tento příklad, otevřete nový projekt aplikace Windows, přidat tlačítko s názvem `Button1` a textové pole s názvem `TextBox1` hlavní formulář s názvem `Form1`.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="b0ff4-142">Klikněte pravým tlačítkem formuláři a klikněte na tlačítko **kód zobrazení** otevření editoru kódu.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="b0ff4-143">Přidat `WithEvents` do části deklarace proměnné `Form1` třídy.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="b0ff4-144">Příklad</span><span class="sxs-lookup"><span data-stu-id="b0ff4-144">Example</span></span>  
 <span data-ttu-id="b0ff4-145">Přidejte následující kód pro kód pro `Form1`.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="b0ff4-146">Nahraďte všechny duplicitní postupy, které mohou existovat, jako například `Form_Load`, nebo `Button_Click`.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 <span data-ttu-id="b0ff4-147">Stisknutím klávesy F5 spusťte v předchozím příkladu a klikněte na tlačítko s názvem bez přípony **spustit**.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="b0ff4-148">První textové pole začne počítat dolů sekundách.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="b0ff4-149">Po uplynutí doby úplné (10 sekund), zobrazí první textové pole, "Hotovo".</span><span class="sxs-lookup"><span data-stu-id="b0ff4-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0ff4-150">`My.Application.DoEvents` Metoda nezpracovává události stejným způsobem, jak to dělá formuláře.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="b0ff4-151">Chcete-li povolit formuláře pro zpracování událostí přímo, můžete použít více vláken.</span><span class="sxs-lookup"><span data-stu-id="b0ff4-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="b0ff4-152">Další informace najdete v tématu [zřetězení](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="b0ff4-152">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ff4-153">Viz také</span><span class="sxs-lookup"><span data-stu-id="b0ff4-153">See Also</span></span>  
 [<span data-ttu-id="b0ff4-154">Události</span><span class="sxs-lookup"><span data-stu-id="b0ff4-154">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="b0ff4-155">Event – příkaz</span><span class="sxs-lookup"><span data-stu-id="b0ff4-155">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="b0ff4-156">AddHandler – příkaz</span><span class="sxs-lookup"><span data-stu-id="b0ff4-156">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="b0ff4-157">RemoveHandler – příkaz</span><span class="sxs-lookup"><span data-stu-id="b0ff4-157">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="b0ff4-158">Obslužné rutiny</span><span class="sxs-lookup"><span data-stu-id="b0ff4-158">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)