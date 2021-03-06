---
title: "Sub – výraz (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 43e35bd0386bc56478603ec36437981785cc8ffb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="sub-expression-visual-basic"></a>Sub – výraz (Visual Basic)
Deklaruje, parametry a kód, který definovat podprogramu výrazu lambda.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Součásti  
  
|Termín|Definice|  
|---|---|  
|`parameterlist`|Volitelné. Seznam místní názvy proměnných, které představují parametry procedury. Závorkách musí být k dispozici i v případě, že seznam je prázdný. Další informace najdete v tématu [seznam parametrů](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Požadováno. Jeden příkaz.|  
|`statements`|Požadováno. Seznam příkazů.|  
  
## <a name="remarks"></a>Poznámky  
 A *výrazu lambda* je podprogramu, který nemá název a které provede jeden nebo více příkazů. Výraz lambda lze použít kdekoli používané typem delegáta, s výjimkou jako argument pro `RemoveHandler`. Další informace o Delegáti a použití výrazů lambda s delegáti najdete v tématu [delegáta příkaz](../../../visual-basic/language-reference/statements/delegate-statement.md) a [volný převod delegáta](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Syntaxe výrazu lambda  
 Syntaxe výrazu lambda podobá se standardní podprogramu. Rozdíly jsou následující:  
  
-   Výraz lambda nemá název.  
  
-   Výraz lambda nemůže mít modifikátor, jako například `Overloads` nebo `Overrides`.  
  
-   Tělo výrazu lambda jeden řádek musí být příkaz, není výraz. Text se může skládat z volání procedury sub, ale není volání procedury funkce.  
  
-   Ve výrazu lambda buď všechny parametry musí mít zadán odvodit datové typy nebo všechny parametry.  
  
-   Volitelné a `ParamArray` parametry nejsou povoleny ve výrazech lambda.  
  
-   Obecné parametry nejsou povoleny ve výrazech lambda.  
  
## <a name="example"></a>Příklad  
 Tady je příklad výrazu lambda, která hodnotu zapíše do konzoly. Příklad ukazuje, jak jeden řádek a víceřádkový syntaxe výrazu lambda pro podprogramu. Další příklady najdete v tématu [výrazy Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a>Viz také  
 [Sub – příkaz](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Lambda – výrazy](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Operátory a výrazy](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Příkazy](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Volný převod delegáta](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
