---
title: "Funkční konstrukce (technologie LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d5c68fb71fd59d08574cee9eec933cee25e504d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="functional-construction-linq-to-xml-visual-basic"></a>Funkční konstrukce (technologie LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]nabízí efektivní způsob, jak vytvořit elementů XML s názvem *funkční konstrukce*. Funkční konstrukce je schopnost vytvářet strom XML v jediném příkazu.  
  
 Existuje několik klíčových funkcích služby [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programovací rozhraní, které povolit funkční konstrukce:  
  
-   <xref:System.Xml.Linq.XElement> Konstruktor přebírá různé typy argumentů pro obsah. Můžete například předat jiné <xref:System.Xml.Linq.XElement> objekt, který se stane podřízený element. Můžete předat <xref:System.Xml.Linq.XAttribute> objektu, který bude atribut elementu. Nebo můžete předat jiný typ objektu, který je převedeno na řetězec a že bude textového obsahu elementu.  
  
-   <xref:System.Xml.Linq.XElement> Konstruktor přijímá `params` pole typu <xref:System.Object>, takže můžete předat libovolný počet objektů do konstruktoru. Umožňuje vytvořit element, který má složitý obsah.  
  
-   Pokud objekt implementuje <xref:System.Collections.Generic.IEnumerable%601>, je vytvořena kolekce v objektu, a jsou přidány všechny položky v kolekci. Pokud kolekce obsahuje <xref:System.Xml.Linq.XElement> nebo <xref:System.Xml.Linq.XAttribute> objekty, každá položka v kolekci se přidá samostatně. To je důležité, protože vám umožňuje předat výsledky [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] dotazu konstruktoru.  
  
 Následuje příklad:  
  
 Tyto funkce umožňují napsat kód pomocí XML – literály vytvořit strom XML a také napsat kód, který používá výsledky [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] dotazy, když vytvoříte strom XML:  
  
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
            Where CInt(el) > 2 _  
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
  
## <a name="see-also"></a>Viz také  
 [Vytváření stromů XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
