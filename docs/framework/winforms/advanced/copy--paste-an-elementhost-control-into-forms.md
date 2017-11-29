---
title: "Návod: Zkopírování a vložení ovládacího prvku ElementHost do samostatného formuláře Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 65882925c6fbe3e9b393b139a937bc9a1f95ed04
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a><span data-ttu-id="f0709-102">Návod: Zkopírování a vložení ovládacího prvku ElementHost do samostatného formuláře Windows</span><span class="sxs-lookup"><span data-stu-id="f0709-102">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>
<span data-ttu-id="f0709-103">Tento návod ukazuje, jak kopírovat ovládacího prvku Windows Presentation Foundation (WPF) z jednoho formuláře Windows do jiného.</span><span class="sxs-lookup"><span data-stu-id="f0709-103">This walkthrough shows you how to copy a Windows Presentation Foundation (WPF) control from one Windows Form to another.</span></span>  
  
 <span data-ttu-id="f0709-104">V tomto návodu můžete provádět následující úlohy:</span><span class="sxs-lookup"><span data-stu-id="f0709-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="f0709-105">Vytvoření projektu.</span><span class="sxs-lookup"><span data-stu-id="f0709-105">Create the project.</span></span>  
  
-   <span data-ttu-id="f0709-106">Zkopírujte ovládací prvek WPF.</span><span class="sxs-lookup"><span data-stu-id="f0709-106">Copy a WPF Control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0709-107">Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.</span><span class="sxs-lookup"><span data-stu-id="f0709-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f0709-108">Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky.</span><span class="sxs-lookup"><span data-stu-id="f0709-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f0709-109">Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f0709-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f0709-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f0709-110">Prerequisites</span></span>  
 <span data-ttu-id="f0709-111">K dokončení tohoto návodu budete potřebovat následující komponenty:</span><span class="sxs-lookup"><span data-stu-id="f0709-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="f0709-112">.</span><span class="sxs-lookup"><span data-stu-id="f0709-112">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="f0709-113">Vytvoření projektu</span><span class="sxs-lookup"><span data-stu-id="f0709-113">Creating the Project</span></span>  
 <span data-ttu-id="f0709-114">Prvním krokem je vytvoření projektu modelu Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f0709-114">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0709-115">Pokud hostování obsahu subsystému WPF, jsou podporovány pouze projekty C# a Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f0709-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="f0709-116">Vytvoření projektu</span><span class="sxs-lookup"><span data-stu-id="f0709-116">To create the project</span></span>  
  
-   <span data-ttu-id="f0709-117">Vytvořte nový projekt aplikace Windows Forms v jazyce Visual Basic a Visual C# s názvem `CopyElementHost`.</span><span class="sxs-lookup"><span data-stu-id="f0709-117">Create a new Windows Forms Application project in Visual Basic or Visual C# named `CopyElementHost`.</span></span>  
  
## <a name="copying-a-wpf-control"></a><span data-ttu-id="f0709-118">Kopírování ovládací prvek WPF</span><span class="sxs-lookup"><span data-stu-id="f0709-118">Copying a WPF Control</span></span>  
 <span data-ttu-id="f0709-119">Po přidání ovládací prvek WPF do projektu, zkopírujte jej do jiných formulářů v projektu.</span><span class="sxs-lookup"><span data-stu-id="f0709-119">After you add a WPF control to the project, you can copy it to other forms in the project.</span></span>  
  
#### <a name="to-copy-a-wpf-control"></a><span data-ttu-id="f0709-120">Kopírování ovládací prvek WPF</span><span class="sxs-lookup"><span data-stu-id="f0709-120">To copy a WPF control</span></span>  
  
1.  <span data-ttu-id="f0709-121">Přidat nové WPF <xref:System.Windows.Controls.UserControl> projektu k řešení.</span><span class="sxs-lookup"><span data-stu-id="f0709-121">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="f0709-122">Použití výchozího názvu pro typ ovládacího prvku `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="f0709-122">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="f0709-123">Další informace najdete v tématu [návod: vytvoření nové WPF obsahu v aplikaci Windows Forms v době návrhu](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="f0709-123">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="f0709-124">Sestavte projekt.</span><span class="sxs-lookup"><span data-stu-id="f0709-124">Build the project.</span></span>  
  
3.  <span data-ttu-id="f0709-125">Otevřete `Form1` v Návrháři formulářů.</span><span class="sxs-lookup"><span data-stu-id="f0709-125">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="f0709-126">Z **sada nástrojů**, přetáhněte instanci `UserControl1` do formuláře.</span><span class="sxs-lookup"><span data-stu-id="f0709-126">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="f0709-127">Instance `UserControl1` je hostován v nové <xref:System.Windows.Forms.Integration.ElementHost> ovládací prvek s názvem `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="f0709-127">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
5.  <span data-ttu-id="f0709-128">S `elementHost1` vybrána, stiskněte CTRL + C zkopírujte jej do schránky.</span><span class="sxs-lookup"><span data-stu-id="f0709-128">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
6.  <span data-ttu-id="f0709-129">Přidání nového formuláře Windows Form do projektu.</span><span class="sxs-lookup"><span data-stu-id="f0709-129">Add a new Windows Form to the project.</span></span> <span data-ttu-id="f0709-130">Použití výchozího názvu pro typ formuláře `Form2`.</span><span class="sxs-lookup"><span data-stu-id="f0709-130">Use the default name for the form type, `Form2`.</span></span>  
  
7.  <span data-ttu-id="f0709-131">S `Form2` otevřít v Návrháři formulářů, stiskněte klávesy CTRL + V vložte kopii `elementHost1` do formuláře.</span><span class="sxs-lookup"><span data-stu-id="f0709-131">With `Form2` open in the Windows Forms Designer, press CTRL+V to paste a copy of `elementHost1` onto the form.</span></span>  
  
     <span data-ttu-id="f0709-132">Zkopírovaný ovládacího prvku se nazývá také `elementHost1`, protože je privátní pole `Form2` třídy.</span><span class="sxs-lookup"><span data-stu-id="f0709-132">The copied control is also named `elementHost1`, because it is a private field of the `Form2` class.</span></span> <span data-ttu-id="f0709-133">Neexistuje žádný název kolizí s `elementHost1` v `Form1` třídy.</span><span class="sxs-lookup"><span data-stu-id="f0709-133">There is no name collision with the `elementHost1` in the `Form1` class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0709-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="f0709-134">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="f0709-135">Migrace a vzájemná funkční spolupráce</span><span class="sxs-lookup"><span data-stu-id="f0709-135">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="f0709-136">Pomocí ovládacích prvků WPF</span><span class="sxs-lookup"><span data-stu-id="f0709-136">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="f0709-137">Návrhář WPF</span><span class="sxs-lookup"><span data-stu-id="f0709-137">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)