---
title: "Non kompatibilní se specifikací CLS &lt;membername&gt; není povolen v rozhraní, které je kompatibilní se specifikací CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords: BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74744b89ad72b6fd051f83ba38354d0a277555c8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>Non kompatibilní se specifikací CLS &lt;membername&gt; není povolen v rozhraní, které je kompatibilní se specifikací CLS
Vlastnost, postup nebo události v rozhraní je označena jako `<CLSCompliant(True)>` rozhraní samotné, když je označena jako `<CLSCompliant(False)>` nebo není označen.  
  
 Pro rozhraní splňovat [jazyková nezávislost a jazykově nezávislé komponenty](../../../standard/language-independence-and-language-independent-components.md) (CLS), musí být všichni její členové v souladu.  
  
 Pokud použijete <xref:System.CLSCompliantAttribute> programovací element, nastavíte atributu `isCompliant` buď parametr `True` nebo `False` indikující dodržování předpisů nebo nesplňujících požadavky. Neexistuje žádný výchozí hodnotou tohoto parametru, a je nutné zadat hodnotu.  
  
 Pokud se nevztahují <xref:System.CLSCompliantAttribute> na element, je považován za nedodržuje předpisy.  
  
 Ve výchozím nastavení je tato zpráva upozornění. Informace o zobrazení nebo skrytí upozornění práce upozornění jako chyby najdete v tématu [Konfigurace upozornění v jazyce Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID chyby:** BC40033  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Pokud se vyžadují souladu se specifikací CLS a máte kontrolu nad zdrojový kód rozhraní, označit rozhraní jako `<CLSCompliant(True)>` Pokud předpisům všichni její členové.  
  
-   Pokud vyžadují souladu se specifikací CLS a nemáte kontrolu nad zdrojový kód rozhraní, nebo pokud nesplňuje podmínky tak, aby vyhovoval, zadejte tento člen v rámci jiné rozhraní.  
  
-   Pokud požadujete, aby tento člen zůstat v rámci jeho aktuální rozhraní, odeberte <xref:System.CLSCompliantAttribute> z jeho definice nebo označte ji jako `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Viz také  
 [Příkaz Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 
