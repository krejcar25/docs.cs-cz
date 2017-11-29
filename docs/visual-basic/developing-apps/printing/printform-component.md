---
title: "PrintForm – součást (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: PrintForm component [Visual Basic]
ms.assetid: 03de98b8-b54c-4764-91d7-83c64e974750
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 890d5a3a3f9c3a737a59e17fef0d4ac0407e9924
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="printform-component-visual-basic"></a><span data-ttu-id="bfb2f-102">PrintForm – součást (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfb2f-102">PrintForm Component (Visual Basic)</span></span>
<span data-ttu-id="bfb2f-103"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Součásti pro [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] umožňuje vytisknout image Windows Form v době běhu.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enables you to print an image of a Windows Form at run time.</span></span> <span data-ttu-id="bfb2f-104">Své chování nahrazuje u `PrintForm` metoda v dřívějších verzích jazyka Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-104">Its behavior replaces that of the `PrintForm` method in earlier versions of Visual Basic.</span></span>  
  
 <span data-ttu-id="bfb2f-105">Ovládací prvky PowerPack jsou již zahrnuty v sadě Visual Studio, ale si můžete stáhnout z [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="bfb2f-105">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="printform-component-overview"></a><span data-ttu-id="bfb2f-106">PrintForm – součást – přehled</span><span class="sxs-lookup"><span data-stu-id="bfb2f-106">PrintForm Component Overview</span></span>  
 <span data-ttu-id="bfb2f-107">Běžný scénář pro Windows Forms je vytvořit formulář, který je naformátován tak, aby připomínaly dokumentu formuláře nebo sestavy, a potom k tisku obrázek ve formátu.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-107">A common scenario for Windows Forms is to create a form that is formatted to resemble a paper form or a report, and then to print an image of the form.</span></span> <span data-ttu-id="bfb2f-108">Přestože je možné použít <xref:System.Drawing.Printing.PrintDocument> součást k tomu, bude vyžadovat velké množství kódu.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-108">Although you can use a <xref:System.Drawing.Printing.PrintDocument> component to do this, it would require a lot of code.</span></span> <span data-ttu-id="bfb2f-109"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Součást umožňuje tisk obrázku formuláře k tiskárně, okno náhledu tisku nebo do souboru bez použití <xref:System.Drawing.Printing.PrintDocument> součásti.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-109">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to print an image of a form to a printer, to a print preview window, or to a file without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="bfb2f-110"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Součást se nachází na **PowerPacks jazyka Visual Basic** kartě **sada nástrojů**.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-110">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is located on the **Visual Basic PowerPacks** tab of the **Toolbox**.</span></span> <span data-ttu-id="bfb2f-111">Když je přetáhli formulář se zobrazí na hlavním panelu součást oblasti malé pod dolní ohraničení tvaru.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-111">When it is dragged onto a form it appears in the component tray, the small area under the bottom border of the form.</span></span> <span data-ttu-id="bfb2f-112">Pokud je součást vybraná, vlastnosti, které definují své chování může být nastavena v **vlastnosti** okno.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-112">When the component is selected, properties that define its behavior can be set in the **Properties** window.</span></span> <span data-ttu-id="bfb2f-113">Všechny tyto vlastnosti můžete také nastavit v kódu.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-113">All of these properties can also be set in code.</span></span> <span data-ttu-id="bfb2f-114">Můžete také vytvořit instanci <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> součásti v kódu bez přidání komponentu v době návrhu.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-114">You can also create an instance of the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component in code without adding the component at design time.</span></span>  
  
 <span data-ttu-id="bfb2f-115">Při tisku formuláře je vytištěno vše v klientské oblasti formuláře.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-115">When you print a form, everything in the client area of the form is printed.</span></span> <span data-ttu-id="bfb2f-116">To zahrnuje všechny ovládací prvky a libovolný text nebo grafické vykresleny na formuláři pomocí jiných metod grafiky.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-116">This includes all controls and any text or graphics drawn on the form by graphics methods.</span></span> <span data-ttu-id="bfb2f-117">Ve výchozím nastavení nejsou vytištěny záhlaví formuláře, posuvníky a ohraničení.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-117">By default, the form's title bar, scroll bars, and border are not printed.</span></span> <span data-ttu-id="bfb2f-118">Také ve výchozím nastavení <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> součást vytiskne viditelné části formuláře.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-118">Also by default, the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component prints only the visible part of the form.</span></span> <span data-ttu-id="bfb2f-119">Například pokud uživatel změní velikost formuláře za běhu, pouze ovládací prvky a obrázky, které jsou aktuálně viditelné jsou vytisknout.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-119">For example, if the user resizes the form at run time, only the controls and graphics that are currently visible are printed.</span></span>  
  
 <span data-ttu-id="bfb2f-120">Tiskárny výchozí používané <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> součásti je určen podle nastavení ovládacích panelů operačního systému.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-120">The default printer used by the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is determined by the operating system's Control Panel settings.</span></span>  
  
 <span data-ttu-id="bfb2f-121">Po inicializaci tisk standardní <xref:System.Drawing.Printing.PrintDocument> se zobrazí dialogové okno tisku.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-121">After printing is initiated, a standard <xref:System.Drawing.Printing.PrintDocument> printing dialog box is displayed.</span></span> <span data-ttu-id="bfb2f-122">Toto dialogové okno umožňuje uživatelům tiskovou úlohu zrušit.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-122">This dialog box enables users to cancel the print job.</span></span>  
  
### <a name="key-methods-properties-and-events"></a><span data-ttu-id="bfb2f-123">Klíče metody, vlastnosti a události</span><span class="sxs-lookup"><span data-stu-id="bfb2f-123">Key Methods, Properties, and Events</span></span>  
 <span data-ttu-id="bfb2f-124">Metodě klíče <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> součást je <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> metodu, která vytiskne obrázek formuláře tiskárny, okno náhledu tisku nebo souboru.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-124">The key method of the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> method, which prints an image of the form to a printer, print preview window, or file.</span></span> <span data-ttu-id="bfb2f-125">Existují dvě verze <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> metoda:</span><span class="sxs-lookup"><span data-stu-id="bfb2f-125">There are two versions of the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> method:</span></span>  
  
-   <span data-ttu-id="bfb2f-126">Základní verze bez parametrů:`Print()`</span><span class="sxs-lookup"><span data-stu-id="bfb2f-126">A basic version without parameters: `Print()`</span></span>  
  
-   <span data-ttu-id="bfb2f-127">Přetížené verze s parametry, které určují tisk chování:`Print(printForm As Form, printFormOption As PrintOption)`</span><span class="sxs-lookup"><span data-stu-id="bfb2f-127">An overloaded version with parameters that specify printing behavior: `Print(printForm As Form, printFormOption As PrintOption)`</span></span>  
  
     <span data-ttu-id="bfb2f-128">`PrintOption` Přetížené metody, určuje základní implementaci používá k vytištění formuláře, zda záhlaví formuláře, posuvníky a ohraničení vytisknou a jestli jsou vytisknout posouvatelného části formuláře.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-128">The `PrintOption` parameter of the overloaded method determines the underlying implementation used to print the form, whether the form's title bar, scroll bars, and border are printed, and whether scrollable parts of the form are printed.</span></span>  
  
 <span data-ttu-id="bfb2f-129"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> Vlastnost je klíčovou vlastnost <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> součásti.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-129">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property is a key property of the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component.</span></span> <span data-ttu-id="bfb2f-130">Tato vlastnost určuje, zda je výstup odeslán na tiskárnu, zobrazí okno náhledu tisku nebo uložený jako soubor Encapsulated PostScript.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-130">This property determines whether the output is sent to a printer, displayed in a print preview window, or saved as an Encapsulated PostScript file.</span></span> <span data-ttu-id="bfb2f-131">Pokud <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> je nastavena na <xref:System.Drawing.Printing.PrintAction.PrintToFile>, <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> vlastnost určuje název a cesta k souboru.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-131">If the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property is set to <xref:System.Drawing.Printing.PrintAction.PrintToFile>, the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> property specifies the path and file name.</span></span>  
  
 <span data-ttu-id="bfb2f-132"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> Vlastnost poskytuje přístup k základní <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> objekt, který umožňuje určit taková nastavení jako tiskárny, které mají být použity a počet kopií.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-132">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> property provides access to an underlying <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> object that enables you to specify such settings as the printer to use and the number of copies to print.</span></span> <span data-ttu-id="bfb2f-133">Můžete taky zadat dotaz tiskárny funkce, například barvu nebo duplexní podpory.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-133">You can also query the printer's capabilities, such as color or duplex support.</span></span> <span data-ttu-id="bfb2f-134">Tato vlastnost pravděpodobně není v **vlastnosti** okno; přístupná jenom z kódu.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-134">This property does not appear in the **Properties** window; it can be accessed only from code.</span></span>  
  
 <span data-ttu-id="bfb2f-135"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> Vlastnost se používá k určení formátu tisknout při vyvolání <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> součást prostřednictvím kódu programu.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-135">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> property is used to specify the form to print when you invoke the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component programmatically.</span></span> <span data-ttu-id="bfb2f-136">Pokud komponentu je přidán do formuláře v době návrhu, které tvoří je výchozí.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-136">If the component is added to a form at design time, that form is the default.</span></span>  
  
 <span data-ttu-id="bfb2f-137">Klíče událostí <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> součásti zahrnují následující:</span><span class="sxs-lookup"><span data-stu-id="bfb2f-137">Key events for the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component include the following:</span></span>  
  
-   <span data-ttu-id="bfb2f-138"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint>událost.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-138"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint> event.</span></span> <span data-ttu-id="bfb2f-139">Nastane při <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> metoda je volána a před první stránka výtisků dokumentu.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-139">Occurs when the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> method is called and before the first page of the document prints.</span></span>  
  
-   <span data-ttu-id="bfb2f-140"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint>událost.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-140"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint> event.</span></span> <span data-ttu-id="bfb2f-141">Vyskytne se po poslední tisknout.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-141">Occurs after the last page is printed.</span></span>  
  
-   <span data-ttu-id="bfb2f-142"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings>událost.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-142"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings> event.</span></span> <span data-ttu-id="bfb2f-143">Nastane bezprostředně před každou tisknout.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-143">Occurs immediately before each page is printed.</span></span>  
  
### <a name="remarks"></a><span data-ttu-id="bfb2f-144">Poznámky</span><span class="sxs-lookup"><span data-stu-id="bfb2f-144">Remarks</span></span>  
 <span data-ttu-id="bfb2f-145">Pokud formulář obsahuje text nebo grafické vykresleny podle <xref:System.Drawing.Graphics> metody, použijte základní <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> (`Print()`) metoda k jeho tisku.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-145">If a form contains text or graphics drawn by <xref:System.Drawing.Graphics> methods, use the basic <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> (`Print()`) method to print it.</span></span> <span data-ttu-id="bfb2f-146">U některých operačních systémů nemusí vykreslení grafiky při přetížené <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> metoda se používá.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-146">Graphics may not render on some operating systems when the overloaded <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> method is used.</span></span>  
  
 <span data-ttu-id="bfb2f-147">Je-li ve tvaru, který je širší než šířka papíru v tiskárně, může být oříznutí pravé straně formuláře.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-147">If the width of a form is wider than the width of the paper in the printer, the right side of the form might be cut off.</span></span> <span data-ttu-id="bfb2f-148">Při návrhu formuláře pro tisk, ujistěte se, že formulář vešel na papír standardní velikosti.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-148">When you design forms for printing, make sure that the form fits on standard-sized paper.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfb2f-149">Příklad</span><span class="sxs-lookup"><span data-stu-id="bfb2f-149">Example</span></span>  
 <span data-ttu-id="bfb2f-150">Následující příklad ukazuje, běžně se používají <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> součásti.</span><span class="sxs-lookup"><span data-stu-id="bfb2f-150">The following example shows a common use of the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component.</span></span>  
  
```  
' Visual Basic.  
Dim pf As New PrintForm  
pf.Form = Me  
pf.PrintAction = PrintToPrinter  
pf.Print()  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfb2f-151">Viz také</span><span class="sxs-lookup"><span data-stu-id="bfb2f-151">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 [<span data-ttu-id="bfb2f-152">Postupy: tisk formuláře pomocí součásti PrintForm</span><span class="sxs-lookup"><span data-stu-id="bfb2f-152">How to: Print a Form by Using the PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-form-by-using-the-printform-component.md)  
 [<span data-ttu-id="bfb2f-153">Postupy: tisk klientské oblasti formuláře</span><span class="sxs-lookup"><span data-stu-id="bfb2f-153">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [<span data-ttu-id="bfb2f-154">Postupy: tisk klientských i Neklientských oblastí formuláře</span><span class="sxs-lookup"><span data-stu-id="bfb2f-154">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [<span data-ttu-id="bfb2f-155">Postupy: tisk posuvného formuláře</span><span class="sxs-lookup"><span data-stu-id="bfb2f-155">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)