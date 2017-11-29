---
title: "Klonování vs. Připojení (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c3bd105-c9d3-49bd-875b-27ab4e8bc7a3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 811e0b9d6359287d779a8352482f5dc56a3b0035
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="cloning-vs-attaching-visual-basic"></a><span data-ttu-id="a6ab7-102">Klonování vs. Připojení (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6ab7-102">Cloning vs. Attaching (Visual Basic)</span></span>
<span data-ttu-id="a6ab7-103">Při přidávání <xref:System.Xml.Linq.XNode> (včetně <xref:System.Xml.Linq.XElement>) nebo <xref:System.Xml.Linq.XAttribute> objekty na novou větev, pokud se nový obsah nemá nadřazený, jsou objekty jednoduše připojené k stromové struktuře XML.</span><span class="sxs-lookup"><span data-stu-id="a6ab7-103">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects to a new tree, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="a6ab7-104">Pokud nový obsah už je nadřazena a je součástí jiného stromu XML, je klonovat nový obsah.</span><span class="sxs-lookup"><span data-stu-id="a6ab7-104">If the new content already is parented, and is part of another XML tree, the new content is cloned.</span></span> <span data-ttu-id="a6ab7-105">Nově naklonovaný obsah je poté připojený k stromové struktuře XML.</span><span class="sxs-lookup"><span data-stu-id="a6ab7-105">The newly cloned content is then attached to the XML tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6ab7-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="a6ab7-106">Example</span></span>  
 <span data-ttu-id="a6ab7-107">Následující kód ukazuje chování, když přidáte nadřazeným prvkem elementu ke stromu, a při přidání element žádný nadřazený ke stromu.</span><span class="sxs-lookup"><span data-stu-id="a6ab7-107">The following code demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 <span data-ttu-id="a6ab7-108">Tento příklad vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="a6ab7-108">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6ab7-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="a6ab7-109">See Also</span></span>  
 [<span data-ttu-id="a6ab7-110">Vytváření stromů XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6ab7-110">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)