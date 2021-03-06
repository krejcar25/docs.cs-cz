---
title: "PresentationOptions:Freeze – atribut"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cb305c69cec7c4e4766153ae64d37b19ab0bccea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze – atribut
Nastaví <xref:System.Windows.Freezable.IsFrozen%2A> stavu na `true` na obsahující <xref:System.Windows.Freezable> elementu. Výchozí chování <xref:System.Windows.Freezable> bez `PresentationOptions:Freeze` zadaný atribut je, že <xref:System.Windows.Freezable.IsFrozen%2A> je `false` v doba načítání a závisí na Obecné <xref:System.Windows.Freezable> chování za běhu.  
  
## <a name="xaml-attribute-usage"></a>Použití atributu XAML  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>Hodnoty XAML  
  
|||  
|-|-|  
|`PresentationOptions`|Předpony oboru názvů XML, který může být jakýkoli platnou předponu řetězec podle specifikace XML 1.0. Předpona `PresentationOptions` se používá pro potřeby identifikace v této dokumentaci.|  
|`freezableElement`|Element, který vytvoří všechny odvozené třídy z <xref:System.Windows.Freezable>.|  
  
## <a name="remarks"></a>Poznámky  
 `Freeze` Se pouze atribut, nebo jiné programovací element definovaný v `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` obor názvů XML. `Freeze` Atribut existuje v tomto oboru názvů speciální konkrétně tak, aby ho lze označit jako Ignorovatelná pomocí [mc: Ignorovatelná atribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) jako součást deklarací kořenový element. Z důvodu, `Freeze` musí být schopen být Ignorovatelná není protože všechny [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementace zpracovatelů dokážou zmrazení <xref:System.Windows.Freezable> v okamžiku načtení; tato funkce není součástí [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specifikace.  
  
 Možnost zpracování `Freeze` atribut je konkrétně založená na [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesor, který zpracovává [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pro kompilované aplikace. Jakákoli třída nepodporuje atribut a atribut syntaxe není rozšiřitelné nebo změn. Při implementaci vlastní [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesor můžete paralelní zmrazení chování [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesoru při zpracování `Freeze` atributu u <xref:System.Windows.Freezable> elementy v okamžiku načtení.  
  
 Žádnou hodnotu pro `Freeze` atribut jiné než `true` (ne velká a malá písmena) generuje chybu v době zatížení. (Určení `Freeze` atribut jako `false` není chybu, ale který je už výchozí, takže nastavení `false` se nic nestane.).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Freezable>  
 [Přehled zablokovatelných objektů](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [mc:Ignorable – atribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
