---
title: "Názvy deklarovaných XML elementů a atributů (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 846a028e076873d1978f751fdb70e93c7c6a81af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Názvy deklarovaných XML elementů a atributů (Visual Basic)
Toto téma obsahuje [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] pravidla pro vytváření názvů XML elementů a atributů v literálech XML.  V XML literálu můžete zadat místní název nebo kvalifikovaný název. Úplný název se skládá z předponu oboru názvů XML, dvojtečkou a místní název. Další informace o předpon oboru názvů XML, najdete v části [literál XML elementu](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Pravidla  
 Místní název elementu nebo atributu v [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] musí splňovat následující pravidla.  
  
-   Ho můžete začít s názvů. Musí začínat alfabetickým znakem nebo podtržítkem (`_`).  
  
-   Musí obsahovat pouze abecední znaky, číslice desítkové soustavy, podtržítka, tečky (.) a pomlčky (-).  
  
-   Nesmí být víc než 1 024 znaků.  
  
-   Použití dvojteček, které se zobrazují v názvech znamenat vymezení oboru názvů. Proto můžete dvojtečky pouze k určení oboru názvů XML pro určitý název.  
  
 Kromě toho by měl splňovat tyto zásady.  
  
-   Specifikace XML 1.0 si vyhrazuje všechna názvy začíná tímto řetězcem "xml" jakékoliv změny malá a velká písmena. Proto nepoužívejte tyto názvy pro vaše element a atributů.  
  
### <a name="name-length-guidelines"></a>Název délka pokyny  
 Prakticky musí být název co nejkratší při identifikaci stále jasně povaha elementu. Tím zlepšuje čitelnost kódu a snižuje velikost řádku délku a zdrojový soubor.  
  
 Název nesmí být však krátký tak, že nepopisuje adekvátní element nebo jak se používá váš kód. To je důležité pro čitelnost kódu. Pokud někdo jiný pokouší porozumět, nebo pokud sami hledáte na to dlouhou dobu, po ho napsal, názvy odpovídající element ušetřit čas.  
  
## <a name="case-sensitivity-in-names"></a>Malá a velká písmena v názvech  
 Názvy elementů XML rozlišují malá a velká písmena. To znamená, že pokud [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kompilátoru porovná dva názvy, které se liší v abecedním případě pouze, je ji interpretuje jako odlišné názvy. Například interpretuje `ABC` a `abc` jako odkazující na jednotlivé prvky.  
  
## <a name="xml-namespaces"></a>Obory názvů XML  
 Při vytváření literál elementu XML, můžete zadat předponu oboru názvů XML pro název elementu. Další informace najdete v tématu [literál XML elementu](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření XML v jazyce Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Literál XML elementu](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
