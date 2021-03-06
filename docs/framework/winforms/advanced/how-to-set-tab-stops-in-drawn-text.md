---
title: "Postupy: Nastavení zarážek v kresleném textu"
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
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2acc46a9a3fa2c84138cd9a168113f88ab08e4a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Postupy: Nastavení zarážek v kresleném textu
Můžete nastavení zarážek tabulátorů pro text voláním <xref:System.Drawing.StringFormat.SetTabStops%2A> metodu <xref:System.Drawing.StringFormat> objekt a následné předání, <xref:System.Drawing.StringFormat> do objektu <xref:System.Drawing.Graphics.DrawString%2A> metodu <xref:System.Drawing.Graphics> – třída.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> Nemá nepodporuje přidání zarážek tabulátorů vykresleného textu, i když můžete rozšířit stávající karta přestane používat <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> příznak.  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje zarážek na 150, 250 a 350. Kód zobrazí záložkách seznam názvů a výsledků testu.  
  
 Následující obrázek znázorňuje záložkách text.  
  
 ![Text písem](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 Následující kód předá dva argumenty, které mají <xref:System.Drawing.StringFormat.SetTabStops%2A> metoda. Druhý argument je pole, které obsahuje posuny kartě. První argument předaný <xref:System.Drawing.StringFormat.SetTabStops%2A> je 0, což značí, že první posunutí v poli se měří od pozice 0, je levý okraj ohraničující obdélník.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
  
-   V předchozím příkladu je určen k použití s modelem Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Viz také  
 [Použití písem a textu](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Postupy: Kreslení textu pomocí GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
