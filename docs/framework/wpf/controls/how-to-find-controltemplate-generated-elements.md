---
title: "Postupy: Vyhledávání elementů generovaných objektem ControlTemplate"
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
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f81069873930af57e1f6ab2f3e0408b4d53f38b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-controltemplate-generated-elements"></a><span data-ttu-id="15751-102">Postupy: Vyhledávání elementů generovaných objektem ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="15751-102">How to: Find ControlTemplate-Generated Elements</span></span>
<span data-ttu-id="15751-103">Tento příklad ukazuje, jak najít prvky, které jsou generované <xref:System.Windows.Controls.ControlTemplate>.</span><span class="sxs-lookup"><span data-stu-id="15751-103">This example shows how to find elements that are generated by a <xref:System.Windows.Controls.ControlTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15751-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="15751-104">Example</span></span>  
 <span data-ttu-id="15751-105">Následující příklad ukazuje styl, který vytvoří jednoduchou <xref:System.Windows.Controls.ControlTemplate> pro <xref:System.Windows.Controls.Button> třídy:</span><span class="sxs-lookup"><span data-stu-id="15751-105">The following example shows a style that creates a simple <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> class:</span></span>  
  
 [!code-xaml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 <span data-ttu-id="15751-106">Chcete-li po použití šablony při vyhledávání prvku v rámci šablony, můžete zavolat <xref:System.Windows.FrameworkTemplate.FindName%2A> metodu <xref:System.Windows.Controls.Control.Template%2A>.</span><span class="sxs-lookup"><span data-stu-id="15751-106">To find an element within the template after the template has been applied, you can call the <xref:System.Windows.FrameworkTemplate.FindName%2A> method of the <xref:System.Windows.Controls.Control.Template%2A>.</span></span> <span data-ttu-id="15751-107">Následující příklad vytvoří okno se zprávou, který se zobrazuje hodnota skutečná šířka <xref:System.Windows.Controls.Grid> v rámci šablony ovládacího prvku:</span><span class="sxs-lookup"><span data-stu-id="15751-107">The following example creates a message box that shows the actual width value of the <xref:System.Windows.Controls.Grid> within the control template:</span></span>  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a><span data-ttu-id="15751-108">Viz také</span><span class="sxs-lookup"><span data-stu-id="15751-108">See Also</span></span>  
 [<span data-ttu-id="15751-109">Najít prvky generované DataTemplate</span><span class="sxs-lookup"><span data-stu-id="15751-109">Find DataTemplate-Generated Elements</span></span>](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)  
 [<span data-ttu-id="15751-110">Stylů a ukázka</span><span class="sxs-lookup"><span data-stu-id="15751-110">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="15751-111">Namescopes WPF XAML</span><span class="sxs-lookup"><span data-stu-id="15751-111">WPF XAML Namescopes</span></span>](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [<span data-ttu-id="15751-112">Stromy v grafickém subsystému WPF</span><span class="sxs-lookup"><span data-stu-id="15751-112">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)