---
title: "Postupy: načtení jeden podřízený Element (technologie LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 580315fda6ef6f1919f7f2aabc0cf3604a5c4337
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a>Postupy: načtení jeden podřízený Element (technologie LINQ to XML) (Visual Basic)
Toto téma vysvětluje, jak načíst jeden podřízený element zadaný název podřízeného prvku. Pokud znáte název podřízeného elementu, a že je pouze jeden element, který má tento název, může být vhodnější načíst pouze jeden prvek místo kolekce.  
  
 <xref:System.Xml.Linq.XContainer.Element%2A> Metoda vrací prvního podřízeného <xref:System.Xml.Linq.XElement> se zadaným <xref:System.Xml.Linq.XName>.  
  
 Pokud chcete načíst jeden podřízený element v jazyku Visual Basic, je běžný postup použijte vlastnost XML a následně načíst první prvek notaci indexer pole.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití <xref:System.Xml.Linq.XContainer.Element%2A> metoda. Tento příklad trvá stromu XML s názvem `po` a vyhledá první prvek s názvem `Comment`.  
  
 Visual Basic příklad ukazuje, notaci indexer pole načíst jediným elementem.  
  
 Tento příklad používá následující dokumentu XML: [ukázkový soubor XML: typické nákupní objednávka (technologie LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 Tento příklad vytvoří následující výstup:  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje stejný kód pro formát XML, který je v oboru názvů. Další informace najdete v tématu [práci s obory názvů XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 Tento příklad používá následující dokumentu XML: [ukázkový soubor XML: typické nákupní objednávka v Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim e As XElement = po.<aw:DeliveryNotes>(0)  
        Console.WriteLine(e)  
    End Sub  
End Module  
```  
  
 Tento příklad vytvoří následující výstup:  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a>Viz také  
 [Technologie LINQ to XML osy (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
