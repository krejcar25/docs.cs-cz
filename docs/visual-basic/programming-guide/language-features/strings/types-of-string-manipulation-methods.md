---
title: "Typy metod manipulace s řetězci v jazyce Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b437be4a6f4a0cc9d5a4d21291a80c9cb8fffcd3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Typy metod manipulace s řetězci v jazyce Visual Basic
K analýze a manipulaci s vaší řetězce několika různými způsoby. Některé metody jsou součástí [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] jazyk a jiné jsou vyplývajících z `String` třídy.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Jazyk Visual Basic a .NET Framework  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]metody se používají jako vyplývajících funkce jazyka. Mohou být použity bez kvalifikace ve vašem kódu. Následující příklad ukazuje typické použití [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zacházení s řetězci příkaz:  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 V tomto příkladu `Mid` funkce přímé operaci provádí `aString` a přiřadí hodnota, která má `bString`.  
  
 Seznam metod manipulace s řetězci jazyka Visual Basic, naleznete v části [souhrn manipulace s řetězci](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Sdílené metody a Instance metody  
 Můžete také upravit řetězců pomocí metod `String` třídy. Existují dva typy metod v `String`: *sdílené* metody a *instance* metody.  
  
#### <a name="shared-methods"></a>Sdílené metody  
 Sdílené metody je metoda, která byl vyvolán `String` třídy sám a nevyžaduje instance této třídy pro práci. Tyto metody mohou být kvalifikovaný pomocí názvu třídy (`String`) a nikoli s instancí `String` třídy. Příklad:  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 V předchozím příkladu <xref:System.String.Copy%2A?displayProperty=nameWithType> metoda je statickou metodu, který pracuje na výrazu ji dostane a přiřadí výsledná hodnota k `bString`.  
  
#### <a name="instance-methods"></a>Instance metody  
 Instance metody naopak kmen z konkrétní instanci `String` a musí být kvalifikovaný pomocí názvu instance. Příklad:  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 V tomto příkladu <xref:System.String.Substring%2A?displayProperty=nameWithType> je metoda metodou instance `String` (tedy `aString`). Provádí operace na `aString` a přiřadí tuto hodnotu na `bString`.  
  
 Další informace najdete v dokumentaci pro <xref:System.String> třídy.  
  
## <a name="see-also"></a>Viz také  
 [Představení řetězců v jazyce Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
