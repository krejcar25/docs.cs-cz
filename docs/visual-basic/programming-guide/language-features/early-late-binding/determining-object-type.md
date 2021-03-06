---
title: "Určení typu objektu (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9a63b5cf5941deb4dcc7518880b4dc7d0545803c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="determining-object-type-visual-basic"></a>Určení typu objektu (Visual Basic)
Obecné objektové proměnné (to znamená, proměnné je deklarovat jako `Object`) může obsahovat objekty z libovolné třídy. Při použití proměnné typu `Object`, budete muset provést různé akce na základě třídy objektu; například některé objekty nemusí podporovat konkrétní vlastnosti nebo metody. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]poskytuje dvě prostředky pro určení toho, jaký typ objektu je uložené v proměnné objektu: `TypeName` funkce a `TypeOf...Is` operátor.  
  
## <a name="typename-and-typeofis"></a>TypeName a TypeOf... Je  
 `TypeName` Funkce vrátí řetězec, je nejlepší volbou, když potřebujete uložit nebo zobrazit název třídy objektu, jak je znázorněno v následující fragment kódu:  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 `TypeOf...Is` Operátor je nejlepší volbou pro testování typ objektu, protože je mnohem rychlejší než porovnání ekvivalentní řetězec pomocí `TypeName`. Následující fragment kódu používá `TypeOf...Is` v rámci `If...Then...Else` příkaz:  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 Zde jsou kvůli slovo varování. `TypeOf...Is` Vrátí operátor `True` Pokud objekt určitého typu nebo je odvozený z konkrétního typu. Téměř všechno, co se děje s [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zahrnuje objekty, které zahrnují některé prvky obvykle představit jako objekty, například řetězce a celá čísla. Tyto objekty jsou odvozeny od a dědí z metody <xref:System.Object>. Když uplyne `Integer` a vyhodnotí s `Object`, `TypeOf...Is` vrátí operátor `True`. Následující příklad uvádí, že parametr `InParam` se `Object` a `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 Následující příklad používá obě `TypeOf...Is` a `TypeName` k určení typu objektu do ní předán v `Ctrl` argument. `TestObject` Volání procedur `ShowType` s tři různé typy ovládacích prvků.  
  
#### <a name="to-run-the-example"></a>Chcete-li spustit příklad  
  
1.  Vytvořte nový projekt aplikace Windows a přidejte <xref:System.Windows.Forms.Button> řízení, <xref:System.Windows.Forms.CheckBox> řízení a <xref:System.Windows.Forms.RadioButton> ovládacího prvku formuláře.  
  
2.  Z tlačítko ve formuláři, volání `TestObject` postupu.  
  
3.  Přidejte následující kód do svého formuláře:  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [Volání vlastnosti nebo metody pomocí názvu řetězce](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [Object – datový typ](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [If... Potom... Else – příkaz](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [String – datový typ](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Integer – datový typ](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
