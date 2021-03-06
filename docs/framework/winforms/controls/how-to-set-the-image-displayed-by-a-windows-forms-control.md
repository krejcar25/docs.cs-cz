---
title: "Postupy: Nastavení obrázku zobrazovaného ovládacím prvkem Windows Forms"
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
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bf42fc90e19cbac0f165b59c0c6d3dfb7456b5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Postupy: Nastavení obrázku zobrazovaného ovládacím prvkem Windows Forms
Několik Windows Forms – ovládací prvky můžete zobrazit obrázky. Tyto Image může být ikony, které vysvětluje účel ovládacího prvku, jako je například disketu ikonu na tlačítko, které označuje **Uložit** příkaz. Ikony, případně může být obrázky na pozadí vzhled a chování, které chcete poskytnout ovládacího prvku.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>K nastavení obrázku zobrazovaného ovládacím prvkem  
  
1.  Nastavte ovládacího prvku `Image` nebo `BackgroundImage` vlastností pro objekt typu <xref:System.Drawing.Image>. Obecně platí, je bude možné načítat obrázek ze souboru pomocí <xref:System.Drawing.Image.FromFile%2A> metoda.  
  
     V následujícím příkladu kódu cesta pro umístění image je nastavena **obrázky** složky. Většina počítačů s operačním systémem Windows budou obsahovat tento adresář. To také umožňuje uživatelům s minimální systém úrovně přístupu pro spuštění aplikace bezpečně. Následující příklad kódu vyžaduje, že už máte formulář s <xref:System.Windows.Forms.PictureBox> ovládací prvek přidán.  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
