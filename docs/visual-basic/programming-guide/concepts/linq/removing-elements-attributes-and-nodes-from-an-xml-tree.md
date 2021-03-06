---
title: "Odebrání prvky, atributy a uzly ze stromu XML (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1662f0cd1461cc00a8859464b8da3ecb8fd9faf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a>Odebrání prvky, atributy a uzly ze stromu XML (Visual Basic)
Ve stromu XML, můžete upravit odebrání prvky, atributy a jiné typy uzlů.  
  
 Odebrání jeden element nebo jeden atribut z dokumentu XML je jednoduchá. Ale při odebírání kolekce elementy nebo atributy, doporučujeme nejdřív vyhodnotit kolekce do seznamu a pak odstraňte elementy nebo atributy ze seznamu. Nejlepším postupem je použití <xref:System.Xml.Linq.Extensions.Remove%2A> metody rozšíření, která bude to dělají za vás.  
  
 Hlavním důvodem tohoto postupu je výsledkem většinu kolekce, které je načíst ze stromu XML jsou chybná pomocí odložené provedení. Pokud jste není nejdřív vyhodnotit je do seznamu, nebo pokud nepoužijete rozšiřující metody, je možné dojde k určité třídě chyby. Další informace najdete v tématu [smíšený deklarativní kód nebo imperativní kód chyby (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).  
  
 Následující metody odebrat uzly a atributy ze stromu XML.  
  
|Metoda|Popis|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|Odebere <xref:System.Xml.Linq.XAttribute> z nadřazené.|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|Odebere z podřízených uzlů <xref:System.Xml.Linq.XContainer>.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Odstraní obsah a pro atributy z <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Odebere atributy <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Pokud předáte `null` pro hodnotu, pak odebere atribut.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Pokud předáte `null` pro hodnotu, pak odebere podřízený element.|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|Odebere <xref:System.Xml.Linq.XNode> z nadřazené.|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|Odebere každý atribut nebo element ve zdrojové kolekci ze svého nadřízeného elementu.|  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Tento příklad ukazuje tři metody odebírání elementů. Nejprve odebere jeden element. Druhý, načte kolekci elementů, bude je realizována pomocí <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> operátor a také odebere kolekce. Nakonec načte kolekci elementů a odebere je pomocí <xref:System.Xml.Linq.Extensions.Remove%2A> metoda rozšíření.  
  
 Další informace o <xref:System.Linq.Enumerable.ToList%2A> operátor, najdete v části [převádění datové typy (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
### <a name="code"></a>Kód  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
```  
  
### <a name="comments"></a>Komentáře  
 Tento kód vytvoří následující výstup:  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 Všimněte si, že první podřízený prvek byl odebrán z `Child1`. Všechny podřízené elementy byly odebrány z `Child2` a z `Child3`.  
  
## <a name="see-also"></a>Viz také  
 [Úprava XML stromů (technologie LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
