---
title: "Postupy: Výčet instalovaných písem"
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
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 905b5ecbda58d2f7edb7fc30d5505eec63a64c2b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-installed-fonts"></a>Postupy: Výčet instalovaných písem
<xref:System.Drawing.Text.InstalledFontCollection> Třída dědí z <xref:System.Drawing.Text.FontCollection> abstraktní základní třída. Můžete použít <xref:System.Drawing.Text.InstalledFontCollection> objekt, který chcete vytvořit výčet písem v počítači nainstalována. <xref:System.Drawing.Text.FontCollection.Families%2A> Vlastnost <xref:System.Drawing.Text.InstalledFontCollection> objekt je pole <xref:System.Drawing.FontFamily> objekty.  
  
## <a name="example"></a>Příklad  
 Následující příklad uvádí názvy rodiny písem v počítači nainstalována. Kód načte <xref:System.Drawing.FontFamily.Name%2A> vlastnost jednotlivých <xref:System.Drawing.FontFamily> objekt v poli vráceném <xref:System.Drawing.Text.FontCollection.Families%2A> vlastnost. Jako jsou načteny názvů rodin, jsou zřetězen do seznamu formuláře oddělené čárkami. Pak se <xref:System.Drawing.Graphics.DrawString%2A> metodu <xref:System.Drawing.Graphics> třída nevykresluje v obdélníku seznam oddělený čárkami.  
  
 Pokud spustíte příklad kódu, bude výstup podobný zobrazená na následujícím obrázku.  
  
 ![Nainstalovat písem](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 V předchozím příkladu je určen k použití s modelem Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.PaintEventHandler>. Kromě toho by měla importovat <xref:System.Drawing.Text> oboru názvů.  
  
## <a name="see-also"></a>Viz také  
 [Použití písem a textu](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
