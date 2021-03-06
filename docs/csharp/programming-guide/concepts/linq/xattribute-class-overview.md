---
title: "Přehled třídy XAttribute (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e9cfedb476f44ef8c3eaeb45bac571d17802d525
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="xattribute-class-overview-c"></a>Přehled třídy XAttribute (C#)
Atributy jsou páry název/hodnota, které jsou spojeny s elementem. <xref:System.Xml.Linq.XAttribute> Třída reprezentuje atributy XML.  
  
## <a name="overview"></a>Přehled  
 Práce s atributy v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] je podobná práci s elementy. Jejich konstruktory jsou podobné. Metody, které můžete použít k načtení kolekce z nich jsou podobné. A [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] výraz dotazu pro sadu atributů vypadá velmi podobné [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] dotaz výraz pro kolekci elementů.  
  
 Pořadí, ve kterém byly přidány atributy pro element je zachovaná. To znamená pokud iteraci atributy, uvidíte je ve stejném pořadí, v jakém byly přidány.  
  
## <a name="the-xattribute-constructor"></a>Konstruktor XAttribute  
 Následující konstruktoru <xref:System.Xml.Linq.XAttribute> třída je ten, který nejčastěji budete používat:  
  
|Konstruktor|Popis|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Vytvoří <xref:System.Xml.Linq.XAttribute> objektu. `name` Argument určuje název atributu. `content` určuje obsah atributu.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Vytváření Element s atributem  
 Následující kód ukazuje běžné úlohy vytvoření elementu, který obsahuje atribut:  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 Tento příklad vytvoří následující výstup:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Funkční konstrukce atributů  
 Můžete vytvořit <xref:System.Xml.Linq.XAttribute> objekty v řádku s konstrukce <xref:System.Xml.Linq.XElement> objekty, následujícím způsobem:  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
```  
  
 Tento příklad vytvoří následující výstup:  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a>Atributy nejsou uzly  
 Existují určité rozdíly mezi atributy a elementy. <xref:System.Xml.Linq.XAttribute>objekty nejsou uzly ve stromové struktuře XML. Jsou páry název/hodnota, které jsou spojené s elementem XML. Na rozdíl od modelu DOM (Document Object), tím přesněji odráží strukturu XML. I když <xref:System.Xml.Linq.XAttribute> objekty nejsou ve skutečnosti uzly ve stromové struktuře XML, práce s <xref:System.Xml.Linq.XAttribute> je velmi podobný práce s objekty <xref:System.Xml.Linq.XElement> objekty.  
  
 Tento rozdíl je primárně důležitý pouze pro vývojáře, kteří jsou psaní kódu, který funguje s stromy XML na úrovni uzlu. Celá řada vývojářů nebude na těchto rozdílech nevadí.  
  
## <a name="see-also"></a>Viz také  
 [Technologie LINQ to XML přehled programování (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
