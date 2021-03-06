---
title: "Postupy: Vložení hodnoty do vlastnosti (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44e7c4a92ea3d087c12e74aa2ede33a52c8730cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Postupy: Vložení hodnoty do vlastnosti (Visual Basic)
Hodnota uložená v vlastnost umístěním název vlastnosti na levé straně příkazu přiřazení.  
  
 Vlastnosti `Set` postup ukládá hodnotu, ale můžete explicitně ho nevolají podle názvu. Stejně, jako by použijete proměnnou, použijte vlastnost. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Díky volání procedury vlastnosti.  
  
### <a name="to-store-a-value-in-a-property"></a>K uložení hodnoty do vlastnosti  
  
1.  Na levé straně příkazu přiřazení pomocí názvu vlastnosti.  
  
     Nastaví hodnotu v následujícím příkladu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `TimeOfDay` vlastnost poledne, implicitně volání jeho `Set` postupu.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  Pokud vlastnost přijímá argumenty, postupujte podle názvu vlastnosti v závorkách uveďte seznam argumentů. Pokud neexistují žádné argumenty, můžete volitelně vynechat závorkách.  
  
3.  Umístěte argumenty v seznamu argumentů v závorkách, oddělených čárkami. Ujistěte se, že zadáte argumenty ve stejném pořadí, vlastnost definuje odpovídajících parametrů.  
  
4.  Hodnota generovaná na pravé straně přiřazení příkazu je uložené v určité vlastnosti.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [Procedury vlastností](./property-procedures.md)  
 [Parametry a argumenty procedury](./procedure-parameters-and-arguments.md)  
 [Property – příkaz](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Rozdíly mezi vlastnostmi a proměnnými v jazyce Visual Basic](./differences-between-properties-and-variables.md)  
 [Postupy: vytvoření vlastnosti](./how-to-create-a-property.md)  
 [Postupy: deklarace vlastnosti se smíšenými úrovněmi přístupu](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Postupy: volání procedury vlastnosti](./how-to-call-a-property-procedure.md)  
 [Postupy: deklarace a volání výchozí vlastnosti v jazyce Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Postupy: získání hodnoty z vlastnosti](./how-to-get-a-value-from-a-property.md)
