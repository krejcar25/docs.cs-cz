---
title: Technologie LINQ to XML osy (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecd3bd00-28e5-4517-a59f-53bff39fd478
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 119c4808b6d436c2227331dbb3ab9c4077ff56f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-axes-visual-basic"></a>Technologie LINQ to XML osy (Visual Basic)
Po vytvoření strom XML nebo načíst dokument XML do strom XML, můžete ji najít elementy a atributy a jejich hodnoty načíst dotazovat.  
  
 Než napíšete žádné dotazy, musíte pochopit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] osy. Existují dva typy metod osy: nejdřív existují metody, které zavoláte na jednom <xref:System.Xml.Linq.XElement> objekt, <xref:System.Xml.Linq.XDocument> objekt, nebo <xref:System.Xml.Linq.XNode> objektu. Tyto metody pracovat na jediný objekt a vracet kolekci <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute>, nebo <xref:System.Xml.Linq.XNode> objekty. Druhý existují rozšiřující metody, které pracují kolekce a vrátí kolekce. Rozšiřující metody výčet zdrojové kolekci volat metodu vhodná osa pro každou položku v kolekci a řetězení výsledky.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Téma|Popis|  
|-----------|-----------------|  
|[Technologie LINQ to přehled osy XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Definuje osy a vysvětluje, jak se používají v rámci [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] dotazy.|  
|[Postupy: načtení kolekci elementů (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Zavádí <xref:System.Xml.Linq.XContainer.Elements%2A> metoda. Tato metoda načte kolekci podřízených elementů elementu.|  
|[Postupy: načtení hodnoty elementu (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Ukazuje, jak získat hodnoty elementů.|  
|[Postupy: filtru na názvy elementu (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Ukazuje, jak filtrovat názvy elementů při použití osy.|  
|[Postupy: tvoří řetěz volání metod osy (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Ukazuje, jak zřetězit volání metod osy.|  
|[Postupy: načtení jeden podřízený Element (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Ukazuje, jak načíst jeden podřízený element elementu, zadaný název značky podřízený element.|  
|[Postupy: načtení kolekci atributů (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Zavádí <xref:System.Xml.Linq.XElement.Attributes%2A> metoda. Tato metoda načte atributy elementu.|  
|[Postupy: načtení jeden atribut (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Ukazuje, jak načíst jeden atribut elementu, název atributu.|  
|[Postupy: načtení hodnoty atributu (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Ukazuje, jak získat hodnoty atributů.|  
|[Postupy: načtení hodnoty bez podstruktury elementu (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Ukazuje, jak načíst bez podstruktury hodnotu elementu.|  
|[Language-Integrated osy v jazyce Visual Basic (technologie LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/language-integrated-axes.md)|Shrnuje [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] integrované osy.|  
  
## <a name="see-also"></a>Viz také  
 [Průvodce programováním (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
