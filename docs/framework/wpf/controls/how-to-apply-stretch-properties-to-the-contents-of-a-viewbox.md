---
title: "Postupy: Použití vlastností roztažení na obsah viewbox"
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
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 93e61783f70ee501266a68785350ee0810dff255
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a>Postupy: Použití vlastností roztažení na obsah viewbox
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak chcete-li změnit hodnotu <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> a <xref:System.Windows.Controls.Viewbox.Stretch%2A> vlastnosti <xref:System.Windows.Controls.Viewbox>.  
  
 V prvním příkladu používá [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] k definování <xref:System.Windows.Controls.Viewbox> elementu. Přiřadí <xref:System.Windows.FrameworkElement.MaxWidth%2A> a <xref:System.Windows.FrameworkElement.MaxHeight%2A> 400. Příklad vnoří <xref:System.Windows.Controls.Image> v rámci <xref:System.Windows.Controls.Viewbox>. <xref:System.Windows.Controls.Button>elementy, které odpovídají hodnot vlastností pro <xref:System.Windows.Controls.Viewbox.Stretch%2A> a <xref:System.Windows.Controls.StretchDirection> výčty manipulaci roztažení chování vnořeného <xref:System.Windows.Controls.Image>.  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 Následující popisovače souborů kódu <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> události, předchozí [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] příklad definuje.  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Controls.Viewbox>  
 <xref:System.Windows.Media.Stretch>  
 <xref:System.Windows.Controls.StretchDirection>
