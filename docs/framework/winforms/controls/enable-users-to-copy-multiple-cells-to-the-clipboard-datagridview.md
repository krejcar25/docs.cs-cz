---
title: "Postupy: Povolení kopírování více buněk do schránky z ovládacího prvku Windows Forms DataGridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 703284572005ab262a7e9379b601d8144d8e9af1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="f3999-102">Postupy: Povolení kopírování více buněk do schránky z ovládacího prvku Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="f3999-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f3999-103">Když povolíte kopírování buňky, provedete dat ve vaší <xref:System.Windows.Forms.DataGridView> snadno dostupný k ostatním aplikacím prostřednictvím ovládacího prvku <xref:System.Windows.Forms.Clipboard>.</span><span class="sxs-lookup"><span data-stu-id="f3999-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="f3999-104">Hodnoty vybraných buněk jsou převedeny na řetězce a přidat do schránky jako text oddělený tabulátory hodnot pro vložení do aplikace, jako je Poznámkový blok a aplikace Excel a jako tabulku ve formátu HTML pro vložení do aplikace, jako je Word.</span><span class="sxs-lookup"><span data-stu-id="f3999-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="f3999-105">Můžete nakonfigurovat buňky kopírování ke kopírování hodnot v buňkách, zahrnout text záhlaví řádků a sloupců do dat ze schránky nebo zahrnovat text záhlaví jenom v případě, že uživatelé vybrat celé řádky nebo sloupce.</span><span class="sxs-lookup"><span data-stu-id="f3999-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="f3999-106">V závislosti na režimu výběru uživatelé mohou vybrat více skupin odpojené buněk.</span><span class="sxs-lookup"><span data-stu-id="f3999-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="f3999-107">Když uživatel kopie buněk do schránky, nebudou zkopírovány řádků a sloupců s žádné vybraných buněk.</span><span class="sxs-lookup"><span data-stu-id="f3999-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="f3999-108">Všechny ostatní řádky nebo sloupce stát řádků a sloupců v tabulce dat zkopírován do schránky.</span><span class="sxs-lookup"><span data-stu-id="f3999-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="f3999-109">Nezaškrtnuté buněk v tyto řádky a sloupce se zástupnými symboly prázdné zkopírován do schránky.</span><span class="sxs-lookup"><span data-stu-id="f3999-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="f3999-110">Povolit kopírování buňky</span><span class="sxs-lookup"><span data-stu-id="f3999-110">To enable cell copying</span></span>  
  
-   <span data-ttu-id="f3999-111">Nastavte <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="f3999-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="f3999-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="f3999-112">Example</span></span>  
 <span data-ttu-id="f3999-113">Následující příklad kompletní kód ukazuje, jak jsou buněk zkopírován do schránky.</span><span class="sxs-lookup"><span data-stu-id="f3999-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="f3999-114">Tento příklad obsahuje tlačítko, které zkopíruje vybrané buňky do schránky pomocí <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> metoda a zobrazí obsah schránky do textového pole.</span><span class="sxs-lookup"><span data-stu-id="f3999-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3999-115">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="f3999-115">Compiling the Code</span></span>  
 <span data-ttu-id="f3999-116">Tento kód vyžaduje:</span><span class="sxs-lookup"><span data-stu-id="f3999-116">This code requires:</span></span>  
  
-   <span data-ttu-id="f3999-117">Odkazy na sestavení n: System a N:System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="f3999-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f3999-118">Informace o sestavení z příkazového řádku pro tento příklad [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] nebo [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], najdete v části [sestavení z příkazového řádku](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [vytváření pomocí příkazového řádku csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f3999-118">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f3999-119">V tomto příkladu můžete také vytvořit [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] zadáním nebo vložením kódu do nového projektu.</span><span class="sxs-lookup"><span data-stu-id="f3999-119">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="f3999-120">Viz také [postupy: zkompilování a spuštění dokončení Windows Forms kód příklad pomocí sady Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="f3999-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3999-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="f3999-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>  
 [<span data-ttu-id="f3999-122">Výběr a používání schránky s ovládacím prvkem Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="f3999-122">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)