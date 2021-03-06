---
title: "New – operátor (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74f0352379e861ad135ea23d31ea07d638f9e6c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-visual-basic"></a>New – operátor (Visual Basic)
Zavádí `New` klauzuli k vytvoření nové instance objektu, určuje omezení konstruktor parametr typu nebo identifikuje `Sub` postupu jako konstruktoru třídy.  
  
## <a name="remarks"></a>Poznámky  
 V deklaraci nebo příkaz přiřazení `New` klauzuli musí být zadána definované třídy, ze kterého lze vytvořit instance. To znamená, že třída musí vystavit jeden nebo více konstruktory, kteří mohou přistupovat k volání kódu.  
  
 Můžete použít `New` klauzuli v deklaraci příkaz nebo příkazu přiřazení. Při spuštění příkazu, zavolá vhodný konstruktor pro zadanou třídu předání argumentů, které jste zadali. Následující příklad ukazuje to tak, že vytvoříte instancí `Customer` třídu, která má dva konstruktory, jeden, které nepřijímá žádné parametry a ten, který použije parametr řetězce.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 Vzhledem k tomu, že pole jsou třídy, `New` můžete vytvořit novou instanci pole, jak je znázorněno v následujících příkladech.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 Modul CLR (CLR), vyvolá <xref:System.OutOfMemoryException> chyby, pokud je nedostatek paměti k vytvoření nové instance.  
  
> [!NOTE]
>  `New` – Klíčové slovo se také používá v seznamech typu parametr k určení, zda zadaný typ musí vystavit přístupné bezparametrový konstruktor. Další informace o parametry typu a omezení najdete v tématu [seznam typů](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Chcete-li vytvořit proceduru konstruktor pro třídu, nastavte název `Sub` postup `New` – klíčové slovo. Další informace najdete v tématu [doba života objektu: jak jsou objekty vytvořen a Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 `New` – Klíčové slovo lze použít v těchto kontexty:  
  
 [Dim – příkaz](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Z](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub – příkaz](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.OutOfMemoryException>  
 [Klíčová slova](../../../visual-basic/language-reference/keywords/index.md)  
 [Seznam typů](../../../visual-basic/language-reference/statements/type-list.md)  
 [Obecné typy v jazyce Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Doba života objektu: Objekty vytváření a zničení](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
