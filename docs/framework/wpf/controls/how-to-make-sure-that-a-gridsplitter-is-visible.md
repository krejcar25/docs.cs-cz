---
title: 'Postupy: Kontrola viditelnosti objektu GridSplitter'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b7587a093b2b43856a05693bb785a0465211782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>Postupy: Kontrola viditelnosti objektu GridSplitter
Tento příklad ukazuje, jak zajistit <xref:System.Windows.Controls.GridSplitter> z jiných ovládacích prvků v není skrytý ovládací prvek <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Příklad  
 <xref:System.Windows.Controls.Panel.Children%2A> z <xref:System.Windows.Controls.Grid> řízení se zobrazují v pořadí, že jsou definovány v kód. <xref:System.Windows.Controls.GridSplitter>ovládací prvky můžete skrytý za další ovládací prvky, pokud nejsou definovány jako poslední elementů v <xref:System.Windows.Controls.Panel.Children%2A> kolekce nebo je zadat další ovládací prvky a vyšší <xref:System.Windows.Controls.Panel.ZIndexProperty>.  
  
 Aby se zabránilo Skrytá <xref:System.Windows.Controls.GridSplitter> ovládací prvky, proveďte jednu z následujících akcí.  
  
-   Ujistěte se, že <xref:System.Windows.Controls.GridSplitter> ovládací prvky jsou poslední <xref:System.Windows.Controls.Panel.Children%2A> přidán do <xref:System.Windows.Controls.Grid>. Následující příklad ukazuje <xref:System.Windows.Controls.GridSplitter> jako posledním prvkem v <xref:System.Windows.Controls.Panel.Children%2A> kolekce <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   Nastavte <xref:System.Windows.Controls.Panel.ZIndexProperty> na <xref:System.Windows.Controls.GridSplitter> vyšší než ovládací prvek, který by jinak skrýt. Poskytuje následující příklad <xref:System.Windows.Controls.GridSplitter> řízení a vyšší <xref:System.Windows.Controls.Panel.ZIndexProperty> než <xref:System.Windows.Controls.Button> ovládacího prvku.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   Nastavení okrajů na ovládací prvek, který by jinak skrýt <xref:System.Windows.Controls.GridSplitter> tak, aby <xref:System.Windows.Controls.GridSplitter> zpřístupněn. Následující příklad nastaví okrajů pro ovládací prvek, který by jinak překrytí a skrýt <xref:System.Windows.Controls.GridSplitter>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Controls.GridSplitter>  
 [Témata s postupy](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
