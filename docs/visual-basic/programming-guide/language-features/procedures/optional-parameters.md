---
title: "Volitelné parametry (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- parameters [Visual Basic], optional
- Visual Basic code, procedures
- procedures [Visual Basic], optional arguments
- optional arguments
- named arguments [Visual Basic], and optional arguments
- optional parameters
- Optional keyword [Visual Basic], optional arguments
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], and named arguments
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e57023f594cfe4cd79d59cc8541fcf18018de0ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="optional-parameters-visual-basic"></a>Volitelné parametry (Visual Basic)
Můžete určit, že parametr procedury je volitelný, a při volání této procedury se nemusí zadávat žádný argument. *Volitelné parametry* jsou označeny `Optional` – klíčové slovo v definici postupu. Platí následující pravidla:  
  
-   Každý volitelný parametr v definici procedury musí mít výchozí hodnotu.  
  
-   Výchozí hodnota volitelného parametru musí být konstantní výraz.  
  
-   Každý parametr, který v definici procedury následuje za volitelným parametrem, musí být také volitelný.  
  
 Následující syntaxe znázorňuje deklaraci procedury s volitelným parametrem:  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a>Volání procedur s volitelnými parametry  
 Při volání procedury s volitelným parametrem se můžete rozhodnout, zda zadáte argument. Pokud ho nezadáte, použije procedura výchozí hodnotu deklarovanou pro tento parametr.  
  
 Pokud v seznamu argumentů vynecháte jeden nebo více volitelných argumentů, označíte jejich pozice pomocí po sobě jdoucích čárek. V následujícím ukázkovém volání je zadán první a čtvrtý argument, ale nikoli druhý a třetí:  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 Následující příklad vytvoří několik volání `MsgBox` funkce. `MsgBox`jeden vyžaduje parametr a dva volitelné parametry.  
  
 První volání `MsgBox` poskytuje všechny tři argumenty v pořadí, které `MsgBox` definuje je. Ve druhém volání je zadán pouze povinný argument. Ve třetím a čtvrtém volání je zadán první a třetí argument. Třetí volání tak činí podle pozice a čtvrté volání podle názvu.  
  
 [!code-vb[VbVbcnProcedures#47](./codesnippet/VisualBasic/optional-parameters_1.vb)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a>Určení, zda existuje volitelný argument  
 Procedura nedokáže za běhu zjistit, zda byl daný argument vynechán nebo zda volající kód explicitně poskytuje výchozí hodnotu. Pokud to potřebujete rozlišit, můžete jako výchozí nastavit nějakou nepravděpodobnou hodnotu. Následující postup definuje volitelný parametr `office`a testy pro jeho výchozí hodnotu `QJZ`, pokud chcete zobrazit, pokud byla vynechána ve volání:  
  
 [!code-vb[VbVbcnProcedures#46](./codesnippet/VisualBasic/optional-parameters_2.vb)]  
  
 Pokud volitelný parametr, jako je typ odkazu `String`, můžete použít `Nothing` jako výchozí hodnota zadaná, nejedná se očekávaná hodnota pro argument.  
  
## <a name="optional-parameters-and-overloading"></a>Volitelné parametry a přetěžování  
 Proceduru s volitelnými parametry lze definovat také pomocí přetěžování. Pokud máte jeden volitelný parametr, můžete definovat dvě přetížené verze procedury – jednu s parametrem a druhou bez parametru. S rostoucím počtem volitelných parametrů se zvyšuje složitost. Výhodou ale je, že máte absolutní jistotu, zda volající program poskytl jednotlivé volitelné argumenty.  
  
## <a name="see-also"></a>Viz také  
 [Postupy](./index.md)  
 [Parametry a argumenty procedury](./procedure-parameters-and-arguments.md)  
 [Předávání argumentů podle hodnoty a podle Reference](./passing-arguments-by-value-and-by-reference.md)  
 [Předávání argumentů podle pozice a názvu](./passing-arguments-by-position-and-by-name.md)  
 [Pole parametrů](./parameter-arrays.md)  
 [Přetížení procedury](./procedure-overloading.md)  
 [Volitelné](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
