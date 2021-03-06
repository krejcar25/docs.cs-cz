---
title: "Prázdné znaky v literálech XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8587abb98fe33ab2c5a0cef6cea76049a00909e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Prázdné znaky v literálech XML (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Kompilátoru zahrnuje pouze znaky významné prázdné znaky z literál XML při vytváření [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objektu. Nejsou zahrnuty zanedbatelný prázdné znaky.  
  
## <a name="significant-and-insignificant-white-space"></a>Významné a zanedbatelný prázdné znaky  
 Prázdné znaky v literálech XML jsou důležitá pouze tří oblastí:  
  
-   Pokud se hodnota atributu.  
  
-   Když jsou součástí textového obsahu elementu a text také obsahuje jiné znaky.  
  
-   Když jsou v embedded výrazu pro textového obsahu elementu.  
  
 Jinak kompilátor zpracovává prázdné znaky jako zanedbatelný a pak nezahrnuje v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objekt pro literál.  
  
 Literál XML zahrnout zanedbatelný prázdné znaky, použijte embedded výraz, který obsahuje řetězcový literál s bílými oblasti.  
  
> [!NOTE]
>  Pokud `xml:space` atributu se zobrazí v elementu XML literálu, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kompilátoru obsahuje atribut v <xref:System.Xml.Linq.XElement> objektu, ale přidání tento atribut nezmění jak kompilátor zpracovává mezer.  
  
## <a name="examples"></a>Příklady  
 Následující příklad obsahuje dva elementy XML vnitřní a vnější. Oba elementy obsahovat prázdné znaky v jejich textového obsahu. Prázdné znaky v prvku vnější je zanedbatelný, protože obsahuje jenom prázdné znaky a XML element. Prázdné znaky v informacích o vnitřní element je důležité, protože obsahuje prázdné znaky a text.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 Při spuštění, tento kód zobrazí následující text.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření XML v jazyce Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
