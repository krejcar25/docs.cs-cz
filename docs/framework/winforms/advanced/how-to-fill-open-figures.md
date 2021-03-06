---
title: "Postupy: Vyplňování otevřených obrázků"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c020e5f7306e73ee97dff0b492b04b5a153059cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-open-figures"></a>Postupy: Vyplňování otevřených obrázků
Cestu můžete vyplnit předáním <xref:System.Drawing.Drawing2D.GraphicsPath> do objektu <xref:System.Drawing.Graphics.FillPath%2A> metoda. <xref:System.Drawing.Graphics.FillPath%2A> Metoda doplní cestu podle režim vyplnění (alternativní nebo vinutí) nastaveno pro cestu. Pokud cesta obsahuje všech otevřených obrázků, cesta vyplněno jako v případě, že tyto údaje nebyly zavřeny. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]Zavře obrázek podle kreslení přímku z koncového bodu pro výchozí bod.  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří cestu, která má jeden otevřený útvar (oblouk) a jeden uzavřený útvar (elipsy). <xref:System.Drawing.Graphics.FillPath%2A> Metoda doplní cestu podle režim vyplnění výchozí, což je <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 Následující obrázek znázorňuje výstup ukázkový kód. Všimněte si, že cesta je plná (podle <xref:System.Drawing.Drawing2D.FillMode.Alternate>) jako kdyby byly otevřený útvar uzavřené přímku z koncového bodu pro výchozí bod.  
  
 ![Vyplnění otevřené cesty](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 V předchozím příkladu je určen k použití s modelem Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.Control.Paint> obslužné rutiny události.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Grafické cesty v GDI+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
