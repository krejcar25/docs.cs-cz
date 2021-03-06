---
title: "Přehled XElement třídy (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: decd7c4f805de0d23b091972ee95a323baf0b7d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="xelement-class-overview-visual-basic"></a>Přehled XElement třídy (Visual Basic)
<xref:System.Xml.Linq.XElement> Třída je jedné ze základních tříd v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Reprezentuje element, XML. Tuto třídu můžete použít k vytváření prvků; Změňte obsah elementu; přidat, změnit nebo odstranit podřízené elementy; Přidání atributů do elementu; nebo serializovat obsah elementu v textové podobě. Také můžete spolupracovat s jiné třídy v <xref:System.Xml?displayProperty=nameWithType>, jako například <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, a <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="xelement-functionality"></a>Funkce XElement  
 Toto téma popisuje funkce poskytované službou <xref:System.Xml.Linq.XElement> třídy.  
  
### <a name="constructing-xml-trees"></a>Vytváření stromů XML  
 Můžete vytvořit stromy XML v mnoha různými způsoby, včetně následujících:  
  
-   Můžete vytvořit strom XML v kódu. Další informace najdete v tématu [vytváření stromů XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
-   Můžete analyzovat soubor XML z různých zdrojů, včetně <xref:System.IO.TextReader>, textové soubory nebo webovou adresu (URL). Další informace najdete v tématu [analýze XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).  
  
-   Můžete použít <xref:System.Xml.XmlReader> k naplnění stromu. Další informace naleznete v tématu <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
-   Pokud máte modul, který může zapisovat obsah tak, aby <xref:System.Xml.XmlWriter>, můžete použít <xref:System.Xml.Linq.XContainer.CreateWriter%2A> metodu pro vytvoření zapisovač, zapisovač předat modul a potom používat obsah, který je zapsán do <xref:System.Xml.XmlWriter> k naplnění stromové struktuře XML.  
  
 Však většiny běžných způsob, jak vytvořit strom XML je následující:  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 Jiné velmi běžné technika pro vytvoření strom XML, která využívá výsledky [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] dotaz k naplnění strom XML, jak je znázorněno v následujícím příkladu:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 Tento příklad vytvoří následující výstup:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a>Serializace XML stromů  
 Může serializovat XML stromu <xref:System.IO.File>, <xref:System.IO.TextWriter>, nebo <xref:System.Xml.XmlWriter>.  
  
 Další informace najdete v tématu [serializaci stromy XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>Načítání dat XML pomocí metody osy  
 Metody osy můžete načíst atributy, podřízené elementy, následnickým elementům a nadřazenými prvky. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]dotazy na ose metody pracovat a zadejte několik způsobů pružnější a výkonnější procházení a zpracovat strom XML.  
  
 Další informace najdete v tématu [technologie LINQ to XML osy (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).  
  
### <a name="querying-xml-trees"></a>Dotazování stromy XML  
 Můžete napsat [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] dotazy, které extrahovat data z strom XML.  
  
 Další informace najdete v tématu [dotazování stromy XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).  
  
### <a name="modifying-xml-trees"></a>Úprava stromy XML  
 Element v mnoha různými způsoby, včetně změny jeho obsah nebo atributy, můžete upravit. Můžete také odebrat element z jeho nadřazený objekt.  
  
 Další informace najdete v tématu [úpravy stromů XML (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).  
  
## <a name="see-also"></a>Viz také  
 [Technologie LINQ to přehled programování v XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
