---
title: "Postupy: Volání procedury vlastnosti (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf9080e3c2b23302257499f13e734231f3614495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Postupy: Volání procedury vlastnosti (Visual Basic)
Volání procedury vlastnosti ukládání hodnotu ve vlastnosti nebo načtení jeho hodnoty. Přístup k vlastnosti stejným způsobem jako přístup k proměnné.  
  
 Vlastnosti `Set` postup ukládá hodnotu a jeho `Get` postup načte hodnotu. Ale Nevolejte explicitně tyto postupy podle názvu. Pomocí vlastnosti v příkazu přiřazení nebo výraz, stejně, jako by ukládat a načítat hodnoty proměnné. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Díky volání procedury vlastnosti.  
  
### <a name="to-call-a-propertys-get-procedure"></a>K volání procedury Get vlastnost  
  
1.  Pomocí názvu vlastnosti ve výrazu stejným způsobem, jako byste použili název proměnné. Můžete použít vlastnost kdekoli můžete proměnné nebo konstantní.  
  
     -nebo-  
  
     Použít následující rovná název vlastnosti (`=`) přihlásit příkazu přiřazení.  
  
     Následující příklad načte hodnotu <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> vlastnost implicitně volání jeho `Get` postupu.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Pokud vlastnost přijímá argumenty, postupujte podle názvu vlastnosti v závorkách uveďte seznam argumentů. Pokud neexistují žádné argumenty, můžete volitelně vynechat závorkách.  
  
3.  Umístěte argumenty v seznamu argumentů v závorkách, oddělených čárkami. Ujistěte se, že zadáte argumenty ve stejném pořadí, vlastnost definuje odpovídajících parametrů.  
  
 Hodnota vlastnosti, na které se účastní výraz stejně jako proměnné Konstanta by nebo je uložené v proměnné nebo vlastnosti na levé straně příkazu přiřazení.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Volání vlastnosti sadu postup  
  
1.  Na levé straně příkazu přiřazení pomocí názvu vlastnosti.  
  
     Nastaví hodnotu v následujícím příkladu <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> vlastnost implicitně volání `Set` postupu.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Pokud vlastnost přijímá argumenty, postupujte podle názvu vlastnosti v závorkách uveďte seznam argumentů. Pokud neexistují žádné argumenty, můžete volitelně vynechat závorkách.  
  
3.  Umístěte argumenty v seznamu argumentů v závorkách, oddělených čárkami. Ujistěte se, že zadáte argumenty ve stejném pořadí, vlastnost definuje odpovídajících parametrů.  
  
 Hodnota generovaná na pravé straně přiřazení příkazu je uložené v určité vlastnosti.  
  
## <a name="see-also"></a>Viz také  
 [Procedury vlastností](./property-procedures.md)  
 [Parametry a argumenty procedury](./procedure-parameters-and-arguments.md)  
 [Property – příkaz](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Rozdíly mezi vlastnostmi a proměnnými v jazyce Visual Basic](./differences-between-properties-and-variables.md)  
 [Postupy: vytvoření vlastnosti](./how-to-create-a-property.md)  
 [Postupy: deklarace vlastnosti se smíšenými úrovněmi přístupu](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Postupy: deklarace a volání výchozí vlastnosti v jazyce Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Postupy: vložení hodnoty do vlastnosti](./how-to-put-a-value-in-a-property.md)  
 [Postupy: získání hodnoty z vlastnosti](./how-to-get-a-value-from-a-property.md)  
 [Get – příkaz](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set – příkaz](../../../../visual-basic/language-reference/statements/set-statement.md)
