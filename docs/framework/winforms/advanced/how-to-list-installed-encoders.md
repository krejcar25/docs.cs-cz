---
title: "Postupy: Vypsání seznamu instalovaných kodérů"
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
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec3ce7d2d933226162664826764c818eacf97afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-list-installed-encoders"></a>Postupy: Vypsání seznamu instalovaných kodérů
Můžete zobrazit seznam kodérů dostupné v počítači, chcete-li zjistit, jestli vaše aplikace můžete uložit do formátu souboru z bitové kopie. <xref:System.Drawing.Imaging.ImageCodecInfo> Třída poskytuje <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> statických metod, aby mohla určit, která image kodéry jsou k dispozici. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>Vrátí pole <xref:System.Drawing.Imaging.ImageCodecInfo> objekty.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu Vypíše seznam nainstalovaných kodéry a jejich hodnoty vlastností.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Aplikace Windows Forms.  
  
-   A <xref:System.Windows.Forms.PaintEventArgs>, což je parametr <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vypsání seznamu instalovaných dekodérů](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [Použití kodérů a dekodérů ve spravovaném GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
