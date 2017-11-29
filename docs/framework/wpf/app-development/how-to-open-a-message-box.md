---
title: "Postupy: Otevřete okno se zprávou"
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
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 302a3cd34d90d47e38af1bbeaadca7e777a26395
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="e4fbf-102">Postupy: Otevřete okno se zprávou</span><span class="sxs-lookup"><span data-stu-id="e4fbf-102">How to: Open a Message Box</span></span>
<span data-ttu-id="e4fbf-103">Tento příklad ukazuje, jak otevřít okno se zprávou.</span><span class="sxs-lookup"><span data-stu-id="e4fbf-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4fbf-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="e4fbf-104">Example</span></span>  
 <span data-ttu-id="e4fbf-105">Okno se zprávou je prefabrikované modální dialogové okno pro zobrazení informací o uživatelům.</span><span class="sxs-lookup"><span data-stu-id="e4fbf-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="e4fbf-106">Okno se zprávou je otevřen voláním statické <xref:System.Windows.MessageBox.Show%2A> metodu <xref:System.Windows.MessageBox> třídy.</span><span class="sxs-lookup"><span data-stu-id="e4fbf-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="e4fbf-107">Když <xref:System.Windows.MessageBox.Show%2A> je volána, zprávy je předán pomocí parametr řetězce.</span><span class="sxs-lookup"><span data-stu-id="e4fbf-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="e4fbf-108">Několik přetížení <xref:System.Windows.MessageBox.Show%2A> vám umožní nakonfigurovat, jak se zobrazí okno se zprávou (viz <xref:System.Windows.MessageBox>).</span><span class="sxs-lookup"><span data-stu-id="e4fbf-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="e4fbf-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="e4fbf-109">See Also</span></span>  
 [<span data-ttu-id="e4fbf-110">Ukázka MessageBox</span><span class="sxs-lookup"><span data-stu-id="e4fbf-110">MessageBox Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160023)