---
title: "Postupy: Uspořádání podřízených formulářů MDI"
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
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a0a32f6a97e02db8e395db504f36bb5270b195c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-arrange-mdi-child-forms"></a>Postupy: Uspořádání podřízených formulářů MDI
Aplikace často, bude mít příkazy nabídky pro akce, například dlaždice Cascade a uspořádat, které řídí rozložení otevřete podřízených formulářů MDI. Můžete použít <xref:System.Windows.Forms.Form.LayoutMdi%2A> metoda s jedním z <xref:System.Windows.Forms.MdiLayout> hodnot výčtu ke změně uspořádání podřízených formulářů v MDI nadřazené formuláře.  
  
 <xref:System.Windows.Forms.MdiLayout> Hodnot výčtu zobrazení podřízených formulářů jako kaskádových jako vodorovně nebo svisle vedle sebe, nebo jako podřízené formuláře ikony uspořádané podél dolní části formuláře MDI. Tyto hodnoty mají stejný účinek jako příkazy Windows **sebe**, **zobrazit windows vedle sebe**, **zobrazit windows skládaný**, a **zobrazení plochy** , v uvedeném pořadí.  
  
 Tyto metody se často používají jako obslužné rutiny událostí, které jsou volány položku nabídky <xref:System.Windows.Forms.Control.Click> událostí. Tímto způsobem může mít položku nabídky s textem "Cascade Windows" požadované vliv na podřízených oken MDI.  
  
### <a name="to-arrange-child-forms"></a>K uspořádání podřízených formulářů  
  
1.  Metoda, použijte <xref:System.Windows.Forms.Form.LayoutMdi%2A> metodu a nastavit <xref:System.Windows.Forms.MdiLayout> výčet nadřazeného formuláře MDI. Následující příklad používá <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> hodnota výčtu pro podřízených oken MDI nadřazeného formuláře (`Form1`). Výčtu se používá v kódu během obslužné rutiny události pro <xref:System.Windows.Forms.Control.Click> události **sebe** položku nabídky.  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  Vám může také dlaždici windows a windows uspořádáním jako ikony změnou <xref:System.Windows.Forms.MdiLayout> použít hodnotu výčtu.  
  
2.  Pokud používáte Visual C#, vložte následující kód v konstruktoru formuláře k registraci obslužné rutiny události.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Aplikace MDI (Multiple-Document Interface)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Postupy: Vytváření nadřazených formulářů MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Postupy: Vytváření podřízených formulářů MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Postupy: Určení podřízeného prvku aktivního MDI](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Postupy: Odesílání dat do aktivního podřízeného MDI](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
