---
title: "Postupy: Vymazání připojení"
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
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af45d504eb4e7d45808f787925a90c8e0ed19476
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-clear-bindings"></a>Postupy: Vymazání připojení
Tento příklad ukazuje, jak vymazat vazby z objektu.  
  
## <a name="example"></a>Příklad  
 Zrušte vazbu z jednotlivé vlastnosti v objektu, volání <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> jak je znázorněno v následujícím příkladu. Následující příklad odebere vazbu z <xref:System.Windows.Controls.TextBlock.TextProperty> z *mytext*, <xref:System.Windows.Controls.TextBlock> objektu.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Vymazání vazby odebere vazbu, tak, aby hodnota vlastnosti závislosti se změní na ať by byl bez vazby. Tato hodnota může být výchozí hodnotu, zděděná hodnota nebo hodnota z vazbu dat šablony.  
  
 Pokud chcete vymazat vazby od všech vlastností v objektu, použijte <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Data.BindingOperations>  
 [Přehled datových vazeb](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Témata s postupy](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
