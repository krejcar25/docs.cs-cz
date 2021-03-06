---
title: "Postupy: Zavedení a zobrazení metasouborů"
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
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7d0f2f15fc9e1dce77b9d8183e2e17b7c35b928
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-and-display-metafiles"></a>Postupy: Zavedení a zobrazení metasouborů
<xref:System.Drawing.Imaging.Metafile> Třídy, která dědí z <xref:System.Drawing.Image> třídy, poskytuje metody pro záznam, zobrazení a zkoumání vektoru bitové kopie.  
  
## <a name="example"></a>Příklad  
 Chcete-li zobrazit bitovou kopii vektoru (metafile) na obrazovce, je třeba <xref:System.Drawing.Imaging.Metafile> objektu a <xref:System.Drawing.Graphics> objektu. Předat název souboru (nebo datový proud) <xref:System.Drawing.Imaging.Metafile> konstruktor. Po vytvoření <xref:System.Drawing.Imaging.Metafile> objektu, který předat <xref:System.Drawing.Imaging.Metafile> do objektu <xref:System.Drawing.Graphics.DrawImage%2A> metodu <xref:System.Drawing.Graphics> objektu.  
  
 V příkladu se vytváří <xref:System.Drawing.Imaging.Metafile> objekt ze souboru EMF (EMF) a pak nakreslí obrázek s jeho levého horního rohu v (60, 10).  
  
 Následující obrázek znázorňuje metafile vykreslovat v zadaném umístění.  
  
 ![Obrázek pozice](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 V předchozím příkladu je určen k použití s modelem Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.Control.Paint> obslužné rutiny události.  
  
## <a name="see-also"></a>Viz také  
 [Práce s obrázky, rastrovými obrázky, ikonami a metasoubory](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
