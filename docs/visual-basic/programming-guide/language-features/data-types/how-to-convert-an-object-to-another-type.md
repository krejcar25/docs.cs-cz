---
title: "Postupy: Převedení objektu na jiný typ v jazyce Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 053c93e7cf842138f5b9299cd2fcfa56342dd40b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Postupy: Převedení objektu na jiný typ v jazyce Visual Basic
Můžete převést `Object` proměnné na jiný datový typ. pomocí klíčového slova převodu [CType – funkce](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad převede `Object` proměnnou `Integer` a `String`.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Pokud víte, že obsah `Object` proměnné jsou konkrétní datového typu, je lepší převést proměnnou datového typu. Pokud budete pokračovat v používání `Object` proměnné, platit buď *zabalení* a *rozbalení* (pro typ hodnoty) nebo *pozdní vazby* (pro typ odkaz). Tyto operace všechny trvat delší dobu provádění a ujistěte se, nižší výkon.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Odkaz na <xref:System?displayProperty=nameWithType> oboru názvů.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Object>  
 [Převody typů v jazyce Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Rozšíření a zúžení převodů](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Implicitní a explicitní převody](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Převody mezi řetězci a ostatními typy](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Převody pole](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Struktury](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Datové typy](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funkce pro převod typů](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
