---
title: "Postupy: Zpracování události MouseDoubleClick pro jednotlivé položky v objektu ListView"
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
helpviewer_keywords: ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3fef9655ab95328e027a303df57c3359a7676eac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Postupy: Zpracování události MouseDoubleClick pro jednotlivé položky v objektu ListView
Zpracovat událost pro položku v <xref:System.Windows.Controls.ListView>, je nutné přidat obslužné rutiny události pro každé <xref:System.Windows.Controls.ListViewItem>. Při <xref:System.Windows.Controls.ListView> je vázán ke zdroji dat nevytvoříte explicitně <xref:System.Windows.Controls.ListViewItem>, ale můžete zpracovat událost pro každou položku přidáním <xref:System.Windows.EventSetter> na styl <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří vázané na data <xref:System.Windows.Controls.ListView> a vytvoří <xref:System.Windows.Style> přidání obslužné rutiny události pro každé <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Následující příklad popisovače <xref:System.Windows.Controls.Control.MouseDoubleClick> událostí.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  I když se nejčastěji vytvořit vazbu <xref:System.Windows.Controls.ListView> ke zdroji dat můžete použít styl přidání obslužné rutiny události pro každé <xref:System.Windows.Controls.ListViewItem> v jiný vázané na data <xref:System.Windows.Controls.ListView> bez ohledu na to, jestli je explicitně vytvořit <xref:System.Windows.Controls.ListViewItem>.  Další informace o explicitní a implicitní vytvoření <xref:System.Windows.Controls.ListViewItem> najdete v části ovládací prvky, <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Xml.XmlElement>  
 [Přehled datových vazeb](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Styly a šablony](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Vytvoření vazby k datům XML pomocí objektu XMLDataProvider a dotazů XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [ListView – přehled](../../../../docs/framework/wpf/controls/listview-overview.md)
