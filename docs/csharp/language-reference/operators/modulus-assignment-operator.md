---
title: "%= – operátor (Referenční dokumentace jazyka C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '%=_CSharpKeyword'
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9bafd0078153e29fbf923948d9b380d4795c3d35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>%= – operátor (Referenční dokumentace jazyka C#)
Operátor přiřazení zbytku.  
  
## <a name="remarks"></a>Poznámky  
 K pomocí výrazu `%=` operátor přiřazení, jako například  
  
```  
x %= y  
```  
  
 je ekvivalentem  
  
```  
x = x % y  
```  
  
 Kromě toho, že `x` je Vyhodnocená jenom jednou. [% – Operátor](../../../csharp/language-reference/operators/modulus-operator.md) je předdefinovaná pro číselné typy vypočítat zbytek po dělení.  
  
 `%=` Operátor nemohou být přetíženy přímo, ale může přetížit uživatelem definované typy [% – operátor](../../../csharp/language-reference/operators/modulus-operator.md) (viz [– operátor (referenční dokumentace jazyka C#)](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Příklad  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace jazyka C#](../../../csharp/language-reference/index.md)  
 [Průvodce programováním v C#](../../../csharp/programming-guide/index.md)  
 [Operátory jazyka C#](../../../csharp/language-reference/operators/index.md)
