---
title: "Postupy: Použití systémových barev v gradientu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: acf0f2c63e0b176f28d611183aab1abecc8f1678
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-colors-in-a-gradient"></a>Postupy: Použití systémových barev v gradientu
Chcete-li používat barvy systému v přechodu, použijte  *\<SystemColor >*barev a  *\<SystemColor >*ColorKey statické vlastnosti <xref:System.Windows.SystemColors> třída získat odkaz na barvu, kde  *\<SystemColor >* je název barvy požadované systému. Použití  *\<SystemColor >*ColorKey vlastnosti, když chcete vytvořit dynamické odkaz, který aktualizuje automaticky jako změny motiv systému. Jinak použijte  *\<SystemColor >*barvu vlastnosti.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá dynamický systém barva prostředky pro vytvoření přechodu.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 Další příklad používá statický systém barva prostředků k vytvoření přechodu.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.SystemColors>  
 [Vykreslení oblasti systémovým štětcem](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Přehled malování plnými barvami a přechody](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
