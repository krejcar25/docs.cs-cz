---
title: "Postupy: Umisťování ovládacích prvků ve formulářích Windows"
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
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4519be86d83fce5afc7410c9f76591158ed71cb6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-position-controls-on-windows-forms"></a>Postupy: Umisťování ovládacích prvků ve formulářích Windows
Umisťování ovládacích prvků, Návrhář formulářů Windows, nebo zadejte <xref:System.Windows.Forms.Control.Location%2A> vlastnost.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Na pozici ovládacího prvku na plochu návrháře Návrhář formulářů Windows  
  
-   Přetáhněte ovládací prvek na požadované místo pomocí myši.  
  
    > [!NOTE]
    >  Vyberte ovládací prvek a přesunout že ho s šipku klíče na místo, přesněji. Navíc *zarovnávacích čar* vám pomůže v umístění ovládacích prvků přesněji do formuláře. Další informace najdete v tématu [návod: uspořádání ovládacích prvků ve Windows Forms pomocí zarovnávacích čar](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### <a name="to-position-a-control-using-the-properties-window"></a>Na pozici ovládacího prvku pomocí vlastnosti okna  
  
1.  Klikněte na ovládací prvek, který chcete umístit.  
  
2.  V **vlastnosti** okno, zadejte hodnoty <xref:System.Windows.Forms.Control.Location%2A> vlastnost, oddělených čárkou, na pozici v rámci příslušného kontejneru ovládacího prvku.  
  
     První číslo (X) je vzdálenost od levého ohraničení kontejneru; druhé číslo (Y) je vzdálenost od horního ohraničení oblasti kontejneru měřená v pixelech.  
  
    > [!NOTE]
    >  Můžete rozbalit <xref:System.Windows.Forms.Control.Location%2A> vlastnosti na typ **X** a **Y** hodnoty jednotlivě.  
  
### <a name="to-position-a-control-programmatically"></a>Na pozici ovládacího prvku prostřednictvím kódu programu  
  
1.  Nastavte <xref:System.Windows.Forms.Control.Location%2A> vlastnosti do ovládacího prvku <xref:System.Drawing.Point>.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  Změnit souřadnici X umístění ovládacího prvku pomocí <xref:System.Windows.Forms.Control.Left%2A> dílčí vlastnosti.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a>Se zvýší umístění ovládacího prvku prostřednictvím kódu programu  
  
1.  Nastavte <xref:System.Windows.Forms.Control.Left%2A> dílčí vlastnosti se zvýší souřadnici X ovládacího prvku.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  Použití <xref:System.Windows.Forms.Control.Location%2A> vlastnost nastavující X a Y ovládacího prvku umisťuje současně. Chcete-li nastavit pozici jednotlivě, použijte ovládací prvek <xref:System.Windows.Forms.Control.Left%2A> (**X**) nebo <xref:System.Windows.Forms.Control.Top%2A> (**Y**) dílčí vlastnosti. Nepokoušejte se implicitně nastavit souřadnice X a Y <xref:System.Drawing.Point> struktura, která představuje tlačítka umístění, protože tato struktura obsahuje kopii na tlačítko souřadnice.  
  
## <a name="see-also"></a>Viz také  
 [Windows Forms – ovládací prvky](../../../../docs/framework/winforms/controls/index.md)  
 [Návod: Uspořádání ovládacích prvků ve Windows Forms pomocí zarovnávacích čar](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Postupy: Uspořádání ovládacích prvků na Windows Forms s použitím ovládacího prvku TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Postupy: Uspořádání ovládacích prvků na formuláři Windows Forms s použitím ovládacího prvku FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Uspořádávání ovládacích prvků ve Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Popisování jednotlivých ovládacích prvků Windows Forms a zajišťování zástupců pro tyto prvky](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Ovládací prvky používané ve Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Ovládací prvky Windows Forms podle funkce](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [Postupy: nastavení umístění obrazovce Windows Forms](http://msdn.microsoft.com/library/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
