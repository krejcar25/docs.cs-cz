---
title: "Postupy: Vytváření standardních tiskových úloh Windows Forms"
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
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69499cdee7803de504e960b08754df33602cfcf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Postupy: Vytváření standardních tiskových úloh Windows Forms
Základ pro tisk ve Windows Forms je <xref:System.Drawing.Printing.PrintDocument> součást – přesněji řečeno, <xref:System.Drawing.Printing.PrintDocument.PrintPage> událostí. Vytvořením kód pro zpracování <xref:System.Drawing.Printing.PrintDocument.PrintPage> událostí, můžete zadat, tisknout, jak můžete k jeho tisku.  
  
### <a name="to-create-a-print-job"></a>Chcete-li vytvořit tiskové úlohy  
  
1.  Přidat <xref:System.Drawing.Printing.PrintDocument> součásti do svého formuláře.  
  
2.  Napsat kód pro zpracování <xref:System.Drawing.Printing.PrintDocument.PrintPage> událostí.  
  
     Budete muset code tisk logiky. Kromě toho budete muset zadat materiálu k tisku.  
  
     V následujícím příkladu kódu je vytvořen obrázek ukázkové ve tvaru red obdélníku v <xref:System.Drawing.Printing.PrintDocument.PrintPage> obslužné rutiny události tak, aby fungoval jako materiálu k tisku.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] a [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) vložte následující kód v konstruktoru formuláře k registraci obslužné rutiny události.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     Můžete také psát kód pro <xref:System.Drawing.Printing.PrintDocument.BeginPrint> a <xref:System.Drawing.Printing.PrintDocument.EndPrint> události, případně včetně celé číslo představující celkový počet stránek tisknout, se odečte jako vytiskne každé stránce.  
  
    > [!NOTE]
    >  Můžete přidat <xref:System.Windows.Forms.PrintDialog> součásti do svého formuláře zajistit vyčištění a efektivní uživatelské rozhraní (UI) pro vaše uživatele. Nastavení <xref:System.Windows.Forms.PrintDialog.Document%2A> vlastnost <xref:System.Windows.Forms.PrintDialog> součást umožňuje vám umožní nastavit vlastnosti související s print dokladu, ve kterém pracujete s svého formuláře. Další informace o <xref:System.Windows.Forms.PrintDialog> součást, najdete v části [PrintDialog – komponenta](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).  
  
     Další informace o jaké jsou specifikace Windows Forms tiskové úlohy, včetně toho, jak vytvořit tiskové úlohy prostřednictvím kódu programu, najdete v části <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Podpora tisku v modelu Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
