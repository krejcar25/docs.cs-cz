---
title: "Úprava prvky, atributy a uzly v Tree3 XML"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: da3b31456bc86b547c5174143620f464dc42f35b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a>Úprava prvky, atributy a uzly ve stromu XML
Následující tabulka shrnuje metody a vlastnosti, které můžete použít k úpravě prvek a jeho podřízené elementy nebo jeho atributy.  
  
 Upravit následující metody <xref:System.Xml.Linq.XElement>.  
  
|Metoda|Popis|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|Nahradí element Analyzovaná XML.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Odebere všechny obsah elementu (podřízené uzly a atributy).|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Odebere atributy elementu.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|Nahradí všechny obsah elementu (podřízené uzly a atributy).|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|Nahradí atributy elementu.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Nastaví hodnotu atributu. Pokud neexistuje, vytvoří atribut. Pokud je hodnota nastavená `null`, odebere atribut.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Nastaví hodnotu podřízený element. Pokud neexistuje, vytvoří elementu. Pokud je hodnota nastavená `null`, odebere element.|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|Obsah elementu (podřízené uzly) nahradí zadaný text.|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|Nastaví hodnotu elementu.|  
  
 Upravit následující metody <xref:System.Xml.Linq.XAttribute>.  
  
|Metoda|Popis|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|Nastaví hodnotu atributu.|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|Nastaví hodnotu atributu.|  
  
 Upravit následující metody <xref:System.Xml.Linq.XNode> (včetně <xref:System.Xml.Linq.XElement> nebo <xref:System.Xml.Linq.XDocument>).  
  
|Metoda|Popis|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|Nahradí uzlu nový obsah.|  
  
 Upravit následující metody <xref:System.Xml.Linq.XContainer> ( <xref:System.Xml.Linq.XElement> nebo <xref:System.Xml.Linq.XDocument>).  
  
|Metoda|Popis|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|Podřízené uzly nahradí nový obsah.|  
  
## <a name="see-also"></a>Viz také  
 [Úprava XML stromů (technologie LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
