---
title: "Události změny vlastnosti"
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
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad22d77043f00ab0caaa6d8b08b6b0a9eef1fed5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="property-changed-events"></a>Události změny vlastnosti
Pokud chcete, aby vaše řízení k odesílání oznámení, když vlastnost s názvem *PropertyName* změny, zadejte událost s názvem *PropertyName* `Changed` a metodu s názvem `On` *PropertyName* `Changed` který vyvolává událost. Zásady vytváření názvů v rozhraní Windows Forms je připojit slovo *změněno* k názvu vlastnosti. Typ delegáta související události pro události změny vlastnosti je <xref:System.EventHandler>, a je datový typ události <xref:System.EventArgs>. Základní třída <xref:System.Windows.Forms.Control> definuje mnoho události změny vlastnosti, jako například <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>a další. Základní informace o událostech, najdete v části [události](../../../../docs/standard/events/index.md) a [události v ovládacích prvcích Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).  
  
 Události změny vlastnosti jsou užitečné, protože umožňují příjemci ovládacího prvku připojit obslužné rutiny událostí, které reagují na změnu. Pokud vaše ovládací prvek musí reagovat na událost změny vlastnosti, která se vyvolá, mají přednost před odpovídající `On` *PropertyName* `Changed` metody místo připojení delegáta k události. Ovládací prvek se obvykle odpovídá na událost změny vlastnosti aktualizace jiných vlastností nebo překreslování některé nebo všechny jeho kreslicí plochy.  
  
 Následující příklad ukazuje jak `FlashTrackBar` vlastního ovládacího prvku odpovídá na některé změny vlastnosti události, které dědí z <xref:System.Windows.Forms.Control>. Kompletní příklad, najdete v části [postupy: vytvoření Windows Forms ovládací prvek, zobrazuje průběh](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>Viz také  
 [Události](../../../../docs/standard/events/index.md)  
 [Události v ovládacích prvcích Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Vlastnosti v ovládacích prvcích Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
