---
title: "Změna stromové struktury v paměti XML vs. Funkční konstrukce (technologie LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b5afc31d-a325-4ec6-bf17-0ff90a20ffca
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d8ff61927d6335228858b24138af074a841d779e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml-c"></a>Změna stromové struktury v paměti XML vs. Funkční konstrukce (technologie LINQ to XML) (C#)
Úprava strom XML na místě je tradiční přístup k změna tvaru dokument XML. Typická aplikace dokumentu načte do úložiště dat, jako je například DOM nebo [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]; používá programovací rozhraní vložení uzlů, odstranit uzly nebo změnit obsah uzly; a potom uloží do souboru XML nebo přenáší přes síť.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]Umožňuje jiná možnost, která je užitečné v mnoha scénářích*: funkční konstrukce*. Funkční konstrukce zpracovává změny dat, jako problém transformace, nikoli jako podrobné manipulaci data Store. Pokud může trvat znázornění dat a transformují je efektivně z jednoho formátu do druhého, výsledek je stejný, jako kdyby trvalo jedno úložiště dat a s nimi manipulovat nějakým způsobem provést další obrazec. Klíč k funkční konstrukce přístup, je předat výsledky dotazů pro <xref:System.Xml.Linq.XDocument> a <xref:System.Xml.Linq.XElement> konstruktory.  
  
 V mnoha případech můžete napsat kód transformational za zlomek času, které by byly třeba k manipulaci s úložiště dat, a tento kód je robustnější a snadněji provádět údržbu. V těchto případech i když transformational přístup může trvat další výpočetní výkon, je efektivnější způsob, jak upravovat data. Pokud znáte funkční přístup vývojář se výsledný kód v mnoha případech je srozumitelnější. Je snadno najít kód, který upravuje jednotlivých součástí stromu.  
  
 Přístup, kde můžete upravit XML stromu místní je známější mnoho DOM programátorům, zatímco kód napsaný funkční přístup může vypadat neznámého vývojáře, kteří ještě nerozumí tento přístup. Pokud je nutné provést pouze malé změny na velké strom XML, přístup, kde můžete upravit stromu zavedené v mnoha případech bude trvat méně času procesoru.  
  
 Toto téma poskytuje příklad, který implementuje pomocí obou přístupů.  
  
## <a name="transforming-attributes-into-elements"></a>Transformace atributy do elementů  
 Například předpokládejme, že chcete upravit následující jednoduché dokumentu XML tak, aby atributy stát elementy. Toto téma představuje první přístup úpravu tradičním na místě. Poté zobrazí funkční konstrukce přístup.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root Data1="123" Data2="456">  
  <Child1>Content</Child1>  
</Root>  
```  
  
### <a name="modifying-the-xml-tree"></a>Úprava stromu XML  
 Můžete napsat kód procedurální k vytváření prvků z atributů a pak odstraňte atributy, následujícím způsobem:  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
foreach (XAttribute att in root.Attributes()) {  
    root.Add(new XElement(att.Name, (string)att));  
}  
root.Attributes().Remove();  
Console.WriteLine(root);  
```  
  
 Tento kód vytvoří následující výstup:  
  
```xml  
<Root>  
  <Child1>Content</Child1>  
  <Data1>123</Data1>  
  <Data2>456</Data2>  
</Root>  
```  
  
### <a name="functional-construction-approach"></a>Funkční konstrukce přístup  
 Naopak funkční přístup se skládá z kódu a vytvořit novou větev, výběr a Výběr elementů a atributů ze stromu zdroj a je vhodné, když jsou přidávány do stromu nové transformace. Funkční přístup vypadá takto:  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
XElement newTree = new XElement("Root",  
    root.Element("Child1"),  
    from att in root.Attributes()  
    select new XElement(att.Name, (string)att)  
);  
Console.WriteLine(newTree);  
```  
  
 Tento příklad výstupu stejné XML jako v prvním příkladu. Všimněte si však, že ve skutečnosti najdete v části výsledné strukturu nový kód XML v funkční přístup. Uvidíte vytvoření `Root` element, kód, který žádá o `Child1` element ze stromu zdroje a kód, který transformuje atributy ze stromu zdroje na elementy ve stromové struktuře nové.  
  
 Funkční příklad v tomto případě není žádná kratší než v prvním příkladu, a není skutečně jednodušší. Ale pokud máte mnoho změn, aby na strom XML, není funkční přístup se stane poměrně složitá a poněkud obtuse. Naproti tomu při použití funkční přístup, stále jenom formuláře požadované XML, vkládání dotazy a výrazy podle potřeby, požadovaný obsah stáhnout. Funkční způsob vypočítá kód, který je snazší správa.  
  
 Všimněte si, že v tomto případě funkční přístup pravděpodobně nebude provádět poměrně a také způsob zpracování stromu. Hlavní problém je, že funkční přístup vytváří více krátké povahy objektů. Kompromis je však efektivní jeden Pokud funkční přístup umožňuje vyšší produktivita programátory.  
  
 To je velmi jednoduchý příklad, ale funguje na tento rozdíl v filosofie mezi dva přístupy. Funkční způsob vypočítá větší zvýšení produktivity pro převod větší dokumentů XML.  
  
## <a name="see-also"></a>Viz také  
 [Úprava XML stromů (technologie LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
