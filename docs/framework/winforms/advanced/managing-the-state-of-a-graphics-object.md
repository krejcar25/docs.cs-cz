---
title: "Správa stavu grafického objektu"
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
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a9514d845580bfe921fefa5f4a249c5a905d03d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="managing-the-state-of-a-graphics-object"></a>Správa stavu grafického objektu
<xref:System.Drawing.Graphics> Třída je jádrem [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Kreslení nic, můžete získat <xref:System.Drawing.Graphics> objektu, nastavte jeho vlastnosti a volat jeho metody <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>a podobně).  
  
 Následující příklad volání <xref:System.Drawing.Graphics.DrawRectangle%2A> metodu <xref:System.Drawing.Graphics> objektu. První argument předaný <xref:System.Drawing.Graphics.DrawRectangle%2A> je metoda <xref:System.Drawing.Pen> objektu.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a>Stav grafiky  
 A <xref:System.Drawing.Graphics> objekt více než zadejte kreslení metody, jako třeba <xref:System.Drawing.Graphics.DrawLine%2A> a <xref:System.Drawing.Graphics.DrawRectangle%2A>. A <xref:System.Drawing.Graphics> objekt také udržuje grafiky stav, který je možné rozdělit do následujících kategorií:  
  
-   Nastavení kvality  
  
-   Transformace  
  
-   Oblast ořezu  
  
### <a name="quality-settings"></a>Nastavení kvality  
 A <xref:System.Drawing.Graphics> objekt má několik vlastností, které ovlivňují kvalitu položky, které se mají vykreslovat. Například můžete nastavit <xref:System.Drawing.Graphics.TextRenderingHint%2A> vlastnosti a určit typ vyhlazení (pokud existuje) použít na text. Další vlastnosti, které ovlivňují kvality jsou <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, a <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 Následující příklad nevykresluje dvě výpustky, jeden s vyhlazování režim nastavený na <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> a jednu s vyhlazování režim nastavený na <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a>Transformace  
 A <xref:System.Drawing.Graphics> objekt udržuje dvě transformace (world a stránky), které se použijí pro všechny položky, které jsou vykreslovány v tomto <xref:System.Drawing.Graphics> objektu. Všechny afinní transformace mohou být uloženy ve Světové transformace. Afinní transformace zahrnují změny velikosti, otáčení, která znázorňuje, zkosení a překladu. Transformace stránky lze použít pro škálování a změna jednotky (například pixelů k palce). Další informace najdete v tématu [systém souřadnic a transformace](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
 Následující příklad ilustruje world a stránka transformace z <xref:System.Drawing.Graphics> objektu. Světové transformace nastavena na rotaci 30 stupňů. Transformace stránky je nastaven tak, aby souřadnice předat druhým <xref:System.Drawing.Graphics.DrawEllipse%2A> budou považovány za milimetry místo pixelů. Kód vytvoří dvě identické volání <xref:System.Drawing.Graphics.DrawEllipse%2A> metoda. Světové transformace se použije pro první <xref:System.Drawing.Graphics.DrawEllipse%2A> volání a obě transformace (world a stránka) se použijí pro druhý <xref:System.Drawing.Graphics.DrawEllipse%2A> volání.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 Následující obrázek znázorňuje dva výpustky. Upozorňujeme, že se 30 stupeň otočení o původu souřadnicový systém (levého horního rohu klientské oblasti), nikoli o středy na symbol tří teček. Všimněte si také, že pera šířku 1 znamená 1 pixel pro první elipsy a 1 milimetru pro druhý třemi tečkami.  
  
 ![Elipsy](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### <a name="clipping-region"></a>Oblast ořezu  
 A <xref:System.Drawing.Graphics> objekt udržuje oblast ořezu, která se použije pro všechny položky, které jsou vykreslovány v tomto <xref:System.Drawing.Graphics> objektu. Oblast ořezu můžete nastavit tak, že zavoláte <xref:System.Drawing.Graphics.SetClip%2A> metoda.  
  
 Následující příklad vytvoří oblast ve tvaru plus tvořících sjednocení dvou tvaru. Tuto oblast je určený jako oblast výstřižek <xref:System.Drawing.Graphics> objektu. Potom kód nevykresluje dva řádky, které jsou omezeny na vnitřek oblast ořezu.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 Následující obrázek znázorňuje oříznutí řádky.  
  
 ![Omezené oblasti klip](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## <a name="see-also"></a>Viz také  
 [Grafika a kreslení v modelu Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Použití vnořených grafických kontejnerů](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
