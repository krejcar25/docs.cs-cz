---
title: "Postupy: Určení směru připojení"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9944ff214a9dfe12b21e005c4e1998c249bf72b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Postupy: Určení směru připojení
Tento příklad ukazuje, jak určit, zda vazby aktualizuje pouze vazby pro vlastnost target (cíl), vlastnost vazby zdroj (zdroj) nebo vlastnost target i vlastnost zdroje.  
  
## <a name="example"></a>Příklad  
 Můžete použít <xref:System.Windows.Data.Binding.Mode%2A> vlastnosti k určení směru vazby. V následujícím seznamu výčtu jsou uvedené dostupné možnosti pro vazbu aktualizace:  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay>Při každé změně vlastnost Cílová nebo zdrojová vlastnost aktualizuje vlastnost target nebo vlastnost.  
  
-   <xref:System.Windows.Data.BindingMode.OneWay>Vlastnost target aktualizuje jenom v případě, že změny vlastností zdroje.  
  
-   <xref:System.Windows.Data.BindingMode.OneTime>aktualizuje vlastnost target pouze při spuštění aplikace, nebo když <xref:System.Windows.FrameworkElement.DataContext%2A> zde nevyskytlo změnu.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource>Aktualizuje vlastnosti zdroj při vlastnost target.  
  
-   <xref:System.Windows.Data.BindingMode.Default>způsobí, že výchozí <xref:System.Windows.Data.Binding.Mode%2A> hodnotu vlastnost target, který se má použít.  
  
 Další informace najdete v tématu <xref:System.Windows.Data.BindingMode> výčtu.  
  
 Následující příklad ukazuje, jak nastavit <xref:System.Windows.Data.Binding.Mode%2A> vlastnost.  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Ke zjištění změny zdrojů (platí pro <xref:System.Windows.Data.BindingMode.OneWay> a <xref:System.Windows.Data.BindingMode.TwoWay> vazby), zdroj musí implementovat, jako vhodný mechanismus oznámení změn vhodný vlastnost <xref:System.ComponentModel.INotifyPropertyChanged>. V tématu [oznámení o změně vlastnost implementace](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) příklad <xref:System.ComponentModel.INotifyPropertyChanged> implementace.  
  
 Pro <xref:System.Windows.Data.BindingMode.TwoWay> nebo <xref:System.Windows.Data.BindingMode.OneWayToSource> vazby, můžete řídit načasování aktualizací zdroje podle nastavení <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> vlastnost. Další informace naleznete v tématu <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Data.Binding>  
 [Přehled datových vazeb](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Témata s postupy](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
