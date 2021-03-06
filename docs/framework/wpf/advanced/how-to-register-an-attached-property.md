---
title: "Postupy: Registrace připojené vlastnosti"
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
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37c727eee7b56473808fec06ea42044fc742f7f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-register-an-attached-property"></a>Postupy: Registrace připojené vlastnosti
Tento příklad ukazuje způsob registrace přidružená vlastnost a poskytovat veřejné přístupových objektů, takže můžete použít vlastnost v obou [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] a kód. Přidružené vlastnosti jsou definované pomocí syntaxe koncept [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Většina přidružené vlastnosti pro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] typy jsou implementované také jako vlastnosti závislosti. Můžete použít na všech vlastností závislostí <xref:System.Windows.DependencyObject> typy.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak zaregistrovat přidružená vlastnost jako vlastnost závislosti, s použitím <xref:System.Windows.DependencyProperty.RegisterAttached%2A> metoda. Třída zprostředkovatele má možnost poskytnout výchozí metadata pro vlastnost, která lze použít při vlastnost se používá na jiné třídy, pokud přepsání třídy metadat. V tomto příkladu, výchozí hodnota `IsBubbleSource` je nastavena na `false`.  
  
 Třída zprostředkovatele (i když není registrován jako vlastnost závislosti) připojené vlastnosti musíte zadat statické get a sadu přístupových objektů, které následují zásady vytváření názvů `Set` *[AttachedPropertyName]* a `Get` *[AttachedPropertyName]*. Tyto přístupové objekty jsou potřeba, aby funguje [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] čtečky poznáte vlastnost jako atribut v [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] a vyřešení příslušných typů.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.DependencyProperty>  
 [Přehled vlastností závislosti](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Vlastní vlastnosti závislosti](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Témata s postupy](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
