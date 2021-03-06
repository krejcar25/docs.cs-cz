---
title: "Postupy: Seskupení ovládacích prvků Windows Forms RadioButton do funkce v podobě skupiny"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c92048374941f735568bcd758ed475eba78b81e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Postupy: Seskupení ovládacích prvků Windows Forms RadioButton do funkce v podobě skupiny
Windows Forms <xref:System.Windows.Forms.RadioButton> ovládací prvky jsou navrženy umožnit uživateli vybrat mezi dva nebo více nastavení, ve kterých lze přiřadit pouze jeden postup nebo objekt. Například skupina <xref:System.Windows.Forms.RadioButton> ovládací prvky se může zobrazovat vybrat balíček prostředníci pro pořadí, ale pouze jedna prostředníci se použije. Proto pouze jeden <xref:System.Windows.Forms.RadioButton> najednou lze vybrat, i když je součástí skupiny funkčnosti.  
  
 Skupina přepínacích tlačítek podle například výkresu uvnitř kontejneru <xref:System.Windows.Forms.Panel> řízení, <xref:System.Windows.Forms.GroupBox> ovládacího prvku nebo formuláře. Všech přepínačů přidané přímo do formuláře stane jedné skupiny. Chcete-li přidat samostatné skupiny, je nutné umístit uvnitř panelů nebo skupinové rámečky. Další informace o panelů nebo skupinové rámečky najdete v tématu [Přehled ovládacího prvku Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) nebo [groupbox – Přehled ovládacího prvku](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Do skupiny RadioButton – ovládací prvky jako sada funkce nezávisle na jiné sady  
  
1.  Přetáhněte <xref:System.Windows.Forms.GroupBox> nebo <xref:System.Windows.Forms.Panel> řídit z **Windows Forms** na kartě **sada nástrojů** do formuláře.  
  
2.  Kreslení <xref:System.Windows.Forms.RadioButton> ovládací prvky na <xref:System.Windows.Forms.GroupBox> nebo <xref:System.Windows.Forms.Panel> ovládacího prvku.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Forms.RadioButton>  
 [Přehled ovládacího prvku RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)  
 [Přehled ovládacího prvku Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Přehled ovládacího prvku GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [Přehled ovládacího prvku CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Ovládací prvek RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
