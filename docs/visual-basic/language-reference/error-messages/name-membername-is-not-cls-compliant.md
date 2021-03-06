---
title: "Název &lt;membername&gt; není kompatibilní se specifikací CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords: BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba0dda520e37b27f9b7ad3c214508ee370162598
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/21/2017
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a>Název &lt;membername&gt; není kompatibilní se specifikací CLS
Sestavení je označena jako `<CLSCompliant(True)>` ale zveřejňuje člena s názvem, který začíná podtržítkem (`_`).  
  
 Programovací element může obsahovat jeden nebo více podtržítka, ale aby byly kompatibilní s [jazyková nezávislost a jazykově nezávislé komponenty](../../../standard/language-independence-and-language-independent-components.md) (CLS), se nesmí začínat podtržítkem. V tématu [deklarované názvy elementů](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Pokud použijete <xref:System.CLSCompliantAttribute> programovací element, nastavíte atributu `isCompliant` buď parametr `True` nebo `False` indikující dodržování předpisů nebo nesplňujících požadavky. Neexistuje žádný výchozí hodnotou tohoto parametru, a je nutné zadat hodnotu.  
  
 Pokud se nevztahují <xref:System.CLSCompliantAttribute> na element, je považován za nedodržuje předpisy.  
  
 Ve výchozím nastavení je tato zpráva upozornění. Informace o zobrazení nebo skrytí upozornění práce upozornění jako chyby najdete v tématu [Konfigurace upozornění v jazyce Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID chyby:** BC40031  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Pokud budete mít kontrolu nad zdrojový kód, změňte název člena tak, aby nezačíná znakem podtržítka.  
  
-   Pokud budete potřebovat, že název člena zůstanou beze změny, odeberte <xref:System.CLSCompliantAttribute> z jeho definice nebo označte ji jako `<CLSCompliant(False)>`. Přesto můžete označit sestavení jako `<CLSCompliant(True)>`.  
  
## <a name="see-also"></a>Viz také  
 [Deklarované názvy elementů](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Zásady vytváření názvů jazyka Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  

