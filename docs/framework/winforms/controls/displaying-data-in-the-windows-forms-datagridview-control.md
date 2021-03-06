---
title: "Zobrazení dat v ovládacím prvku Windows Forms DataGridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 193562b5dd00950ec483da94e2ea6ea059e88805
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a>Zobrazení dat v ovládacím prvku Windows Forms DataGridView
`DataGridView` Řízení se používá k zobrazení dat z různých zdrojů externí data. Alternativně můžete přidávání řádků a sloupců do ovládacího prvku a ručně přidejte do ní data.  
  
 Při vytvoření vazby ovládacího prvku ke zdroji dat, můžete vygenerovat automaticky na základě schématu zdroje dat sloupců. Pokud tyto sloupce nezobrazí stejně, jako je chcete, můžete skrýt, odebrat nebo změna uspořádání je. Můžete také přidat nevázaných sloupců zobrazíte dodatečná data, která nepochází z datového zdroje.  
  
 Kromě toho můžete zobrazit svá data pomocí standardní formáty (například formátu měny), nebo můžete přizpůsobit zobrazení formátování k prezentaci dat, ale budete muset (jako je například změna barvy pozadí pro záporná čísla nebo výměna řetězcové hodnoty pomocí odpovídající bitových kopií).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Režimy zobrazení dat v ovládacím prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 Popisuje možnosti pro sestavování ovládacího prvku s daty.  
  
 [Formátování dat v ovládacím prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 Popisuje možnosti formátování hodnot v buňkách zobrazení.  
  
 [Návod: Vytvoření nevázaného ovládacího prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 Popisuje, jak ručně naplnit ovládací prvek s daty.  
  
 [Postupy: Vytvoření vazby dat k ovládacímu prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 Popisuje, jak k naplnění ovládacího prvku s daty pomocí vytvoření vazby, aby `BindingSource` obsahující informací načtených z databáze.  
  
 [Postupy: Automatické generování sloupců v ovládacím prvku Windows Forms DataGridView s datovou vazbou](../../../../docs/framework/winforms/controls/autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 Popisuje, jak lze automaticky generovat sloupce podle vázaný datový zdroj.  
  
 [Postupy: Odebrání automaticky vygenerovaných sloupců z ovládacího prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 Popisuje, jak můžete skrýt nebo odstranit sloupce, které automaticky generují z vázaný datový zdroj.  
  
 [Postupy: Změna pořadí sloupců v ovládacím prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 Popisuje, jak ke změně uspořádání sloupců generovaných automaticky z vázaný datový zdroj.  
  
 [Postupy: Přidání nepřipojeného sloupce do ovládacího prvku Windows Forms DataGridView s datovou vazbou](../../../../docs/framework/winforms/controls/unbound-column-to-a-data-bound-datagridview.md)  
 Popisuje postup doplňují data z vázaný datový zdroj zobrazením Další, nevázaných sloupců.  
  
 [Postupy: Vytvoření vazby objektů k ovládacím prvkům Windows Forms DataGridView](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 Popisuje, jak vytvořit vazbu ovládacího prvku do skupiny libovolný objekty tak, aby každý objekt je zobrazen na samostatném řádku.  
  
 [Postupy: Přístup k objektům svázaným s řádky Windows Forms DataGridView](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 Popisuje, jak načíst objekt vázaný na konkrétní řádek ovládacího prvku.  
  
 [Návod: Vytvoření hlavního/podrobného formuláře pomocí dvou ovládacích prvků Windows Forms DataGridView](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 Popisuje, jak zobrazit data ze dvou tabulek souvisejících databáze tak, aby hodnoty zobrazené v jednom `DataGridView` řízení závisí na aktuálně vybraný řádek v jiném ovládacím prvku.  
  
 [Postupy: Přizpůsobení formátování dat v ovládacím prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 Popisuje způsob zpracování <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> událostí Změna vzhledu buněk v závislosti na jejich hodnot.  
  
## <a name="reference"></a>Odkaz  
 <xref:System.Windows.Forms.DataGridView>  
 Poskytuje referenční dokumentaci pro <xref:System.Windows.Forms.DataGridView> ovládacího prvku.  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 Poskytuje referenční dokumentaci pro <xref:System.Windows.Forms.DataGridView.DataSource%2A> vlastnost.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Poskytuje referenční dokumentaci pro <xref:System.Windows.Forms.BindingSource> součásti.  
  
## <a name="related-sections"></a>Související oddíly  
 [Zadávání dat v ovládacím prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 Obsahuje témata, která popisují, jak změnit způsob uživatele, přidání a změna dat v ovládacím prvku.  
  
## <a name="see-also"></a>Viz také  
 [Ovládací prvek DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Typy sloupců v ovládacím prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
