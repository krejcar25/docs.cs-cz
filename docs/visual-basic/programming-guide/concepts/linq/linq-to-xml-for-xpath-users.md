---
title: "Technologie LINQ to XML pro uživatele XPath (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb0666ee1ae5626a4721ea597a53889e1acf8b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>Technologie LINQ to XML pro uživatele XPath (Visual Basic)

Témata zobrazit počet výrazech XPath a jejich [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ekvivalenty.  
  
 Všechny příklady použití funkce jazyka XPath v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] který je zpřístupněn metodami rozšíření v <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>. Příklady spustit výraz XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] výraz. Každý příklad pak porovná výsledky obou dotazů, ověření, že výraz XPath je funkčně srovnatelný [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] dotazu. Jako oba typy dotazů vrátí uzly ve stejném stromu XML, se provádí pomocí referenční identity porovnání výsledků dotazu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Téma|Popis|  
|-----------|-----------------|  
|[Porovnání jazyka XPath a technologie LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Poskytuje přehled podobnosti a rozdíly mezi XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Postupy: hledání prvku podřízené (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-child-element-xpath-linq-to-xml.md)|Porovná ose XPath podřízený element na [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> metoda.<br /><br /> Přidružený výraz XPath je:`"DeliveryNotes"`.|  
|[Postupy: vyhledání seznam podřízené elementy (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Porovná ose XPath podřízené elementy na [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> osy.<br /><br /> Přidružený výraz XPath je:`"./*"`|  
|[Postupy: vyhledání kořenový Element (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-root-element-xpath-linq-to-xml.md)|Porovná jak získat kořenový element s XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`"/PurchaseOrders"`|  
|[Postupy: vyhledání Následnickým elementům (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendant-elements-xpath-linq-to-xml.md)|Porovná jak získat následnickým elementům s konkrétním názvem XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`"//Name"`|  
|[Postupy: filtrování na atribut (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Porovná jak získat následnickým elementům se zadaným názvem a atribut se zadanou hodnotou s XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`".//Address[@Type='Shipping']"`|  
|[Postupy: vyhledání související prvky (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-related-elements-xpath-linq-to-xml.md)|Porovná jak získat k elementu výběr atribut, který je uvedené hodnotou jiný element se XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`|  
|[Postupy: Vyhledání prvků v Namespace (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-in-a-namespace.md)|Porovná použití jazyka XPath <xref:System.Xml.XmlNamespaceManager> třídy s [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XName.Namespace%2A> vlastnost <xref:System.Xml.Linq.XName> třídy pro práci s obory názvů XML.<br /><br /> Přidružený výraz XPath je:`"./aw:*"`|  
|[Postupy: vyhledání předcházející položky na stejné úrovni (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Porovnání jazyka XPath `preceding-sibling` osy k [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] podřízené <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> osy.<br /><br /> Přidružený výraz XPath je:`"preceding-sibling::*"`|  
|[Postupy: vyhledání následníků podřízený Element (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Porovná jak získat následnickým elementům podřízeného prvku s konkrétním názvem XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`"./Paragraph//Text/text()"`|  
|[Postupy: vyhledání spojení dvě cesty umístění (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-union-of-two-location-paths-xpath.md)|Porovná použití operátoru union, <code>&#124;</code>, v XPath s <xref:System.Linq.Enumerable.Concat%2A> operátor standardní dotazu v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:<code>"//Category&#124;//Price"</code>|  
|[Postupy: vyhledání uzly na stejné úrovni (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Porovná jak najít stejné všechny úrovně uzlu, které mají určitý název s XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`"../Book"`|  
|[Postupy: vyhledat atribut nadřazeného (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Porovná přejděte do nadřazeného elementu a vyhledat přidružený atribut použitím XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`"../@id"`|  
|[Postupy: vyhledání atributů na stejné úrovni s konkrétním názvem (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-attributes-of-siblings-with-a-specific-name.md)|Porovná Postup nalezení konkrétních atributů na stejné úrovni uzlu s XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`"``../Book/@id``"`|  
|[Postupy: Vyhledání prvků s určitým atributem (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-with-a-specific-attribute.md)|Porovná jak najít všechny elementy obsahující konkrétní atribut použitím XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`"./*[@Select]"`|  
|[Postupy: hledání podřízených elementů na základě pozice (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-child-elements-based-on-position.md)|Porovná jak najít element podle jeho relativní pozici použitím XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`"Test[position() >= 2 and position() <= 4]"`|  
|[Postupy: vyhledání okamžitou předchozí stejné úrovni (XPath-technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Porovná jak najít okamžitou předchozí stejné úrovni uzlu použitím XPath a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Přidružený výraz XPath je:`"preceding-sibling::*[1]"`|  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Xml.XPath?displayProperty=nameWithType>  
 [Dotazování stromy XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)  
 [Zpracování kódu XML dat pomocí jazyka XPath datový Model](../../../../standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
