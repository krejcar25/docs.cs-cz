---
title: "Postupy: Umístění podřízených elementů pomocí vlastností připojených k plátnu"
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
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5314f39c3012826f25fa6c64baf7eb8e42329f58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>Postupy: Umístění podřízených elementů pomocí vlastností připojených k plátnu
Tento příklad ukazuje, jak používat připojené vlastnosti <xref:System.Windows.Controls.Canvas> na pozici podřízené elementy.  
  
## <a name="example"></a>Příklad  
 Následující příklad přidá čtyři <xref:System.Windows.Controls.Button> elementy jako podřízené prvky nadřazený <xref:System.Windows.Controls.Canvas>. Každý podřízený element představuje jedinečné připojené vlastnost <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, a <xref:System.Windows.Controls.Canvas.Top%2A>. Každý <xref:System.Windows.Controls.Button> je umístěn relativně k nadřazené <xref:System.Windows.Controls.Canvas> a s ohledem na jeho hodnotu přiřazenou vlastnosti.  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.Canvas.Bottom%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 <xref:System.Windows.Controls.Canvas.Right%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Button>  
 [Přehled panelu](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Témata s postupy](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)  
 [Přehled přidružených vlastností](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)
