---
title: "Zachování mezer při Serializing2"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 93cfc1c14d75078170d6e1bbb3fc4ad72f47a206
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="preserving-white-space-while-serializing"></a>Zachování bílé místo při serializaci
Toto téma popisuje, jak řídit mezer při serializaci strom XML.  
  
 Běžný scénář je číst zobrazují odsazené XML, vytvořte ve stromu v paměti XML bez mezer text uzlů (tedy ne zachování mezer), provádění některých operací na soubor XML a potom uložte soubor XML s odsazení. Při serializaci XML s formátování se zachová jenom významné mezer ve stromové struktuře XML. Toto je výchozí chování pro [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Další z typických možností je číst a upravovat kód XML, který je už záměrně zobrazují odsazené. Možná chcete změnit toto odsazení žádným způsobem. To uděláte v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], zachovat mezer při načtení nebo analyzovat soubor XML a zakázat formátování při serializaci XML.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Prázdné znaky chování metod, které serializovat stromy XML  
 Následující metody v <xref:System.Xml.Linq.XElement> a <xref:System.Xml.Linq.XDocument> třídy serializovat strom XML. Ve stromu XML do souboru, může serializovat <xref:System.IO.TextReader>, nebo <xref:System.Xml.XmlReader>. `ToString` Metoda serializuje na řetězec.  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 Pokud metoda nevyžaduje <xref:System.Xml.Linq.SaveOptions> jako argument, pak metodu naformátuje (odsazení) serializovaných XML. V takovém případě se zahodí všechny zanedbatelný mezer ve stromové struktuře XML.  
  
 Pokud metoda <xref:System.Xml.Linq.SaveOptions> jako argument, potom můžete zadat, že metoda není formátu (odsazení) serializovaných XML. V takovém případě se zachovala všechna mezer ve stromové struktuře XML.  
  
## <a name="see-also"></a>Viz také  
 [Serializace XML stromů (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
