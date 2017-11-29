---
title: "Postupy: Zajištění průhledného pozadí pro vlastní ovládací prvek"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a5ec2c353a960626c54c05009393bcd80dac1b38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-give-your-control-a-transparent-background"></a><span data-ttu-id="83910-102">Postupy: Zajištění průhledného pozadí pro vlastní ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="83910-102">How to: Give Your Control a Transparent Background</span></span>
<span data-ttu-id="83910-103">V dřívějších verzích rozhraní .NET Framework, ovládací prvky nepodporovala nastavení transparentní backcolors bez první nastavení <xref:System.Windows.Forms.Control.SetStyle%2A> metoda v konstruktoru pro formuláře.</span><span class="sxs-lookup"><span data-stu-id="83910-103">In earlier versions of the .NET Framework, controls didn't support setting transparent backcolors without first setting the <xref:System.Windows.Forms.Control.SetStyle%2A> method in the forms's constructor.</span></span> <span data-ttu-id="83910-104">V aktuální verzi, barva pozadí pro většinu ovládacích prvků může být nastaven na <xref:System.Drawing.Color.Transparent%2A> v **vlastnosti** okno v době návrhu nebo v kódu v konstruktoru formuláře.</span><span class="sxs-lookup"><span data-stu-id="83910-104">In the current framework version, the backcolor for most controls can be set to <xref:System.Drawing.Color.Transparent%2A> in the **Properties** window at design time, or in code in the form's constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83910-105">Ovládací prvky Windows Forms nepodporují true průhlednost.</span><span class="sxs-lookup"><span data-stu-id="83910-105">Windows Forms controls do not support true transparency.</span></span> <span data-ttu-id="83910-106">Vykreslení pozadí ovládacího prvku Windows Forms transparentní podle jeho nadřazený objekt.</span><span class="sxs-lookup"><span data-stu-id="83910-106">The background of a transparent Windows Forms control is painted by its parent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83910-107"><xref:System.Windows.Controls.Button> Řízení nepodporuje průhledná barva pozadí i v případě <xref:System.Windows.Forms.ButtonBase.BackColor%2A> je nastavena na <xref:System.Drawing.Color.Transparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="83910-107">The <xref:System.Windows.Controls.Button> control doesn't support a transparent backcolor even when the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property is set to <xref:System.Drawing.Color.Transparent%2A>.</span></span>  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a><span data-ttu-id="83910-108">Průhledná barva pozadí umožnit vlastního ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="83910-108">To give your control a transparent backcolor</span></span>  
  
-   <span data-ttu-id="83910-109">V okně vlastností zvolte <xref:System.Windows.Forms.ButtonBase.BackColor%2A> vlastnost a nastavte ji na<xref:System.Drawing.Color.Transparent%2A></span><span class="sxs-lookup"><span data-stu-id="83910-109">In the Properties window, choose the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property and set it to <xref:System.Drawing.Color.Transparent%2A></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83910-110">Viz také</span><span class="sxs-lookup"><span data-stu-id="83910-110">See Also</span></span>  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [<span data-ttu-id="83910-111">Vývoj vlastních Windows Forms – ovládací prvky s rozhraním .NET Framework</span><span class="sxs-lookup"><span data-stu-id="83910-111">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="83910-112">Použití spravovaných grafických tříd</span><span class="sxs-lookup"><span data-stu-id="83910-112">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 [<span data-ttu-id="83910-113">Postupy: kreslení neprůhledných a poloprůhledných čar</span><span class="sxs-lookup"><span data-stu-id="83910-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)