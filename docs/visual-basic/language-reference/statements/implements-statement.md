---
title: "Implements – Příkaz"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1103305ffbf5425d9a6a6a09695437968642710d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="implements-statement"></a>Implements – Příkaz
Určuje jeden nebo více rozhraní, nebo členy rozhraní, které musí být implementována ve třídě nebo definice struktury, ve kterém se zobrazí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Součásti  
 `interfacename`  
 Požadováno. Rozhraní, jejichž vlastnosti, postupy a události se mají odpovídající členové v třídu nebo strukturu.  
  
 `interfacemember`  
 Požadováno. Členové rozhraní, které se implementuje.  
  
## <a name="remarks"></a>Poznámky  
 Rozhraní je kolekce představující členy (vlastnosti, postupy a události) prototypů zapouzdří rozhraní. Rozhraní obsahovat pouze deklarace pro členy; třídy a struktury implementovat tyto členy. Další informace najdete v tématu [rozhraní](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Implements` Příkaz okamžitě postupujte `Class` nebo `Structure` příkaz.  
  
 Při implementaci rozhraní musí implementovat všechny členy v rozhraní deklarovat. Vynechání kteréhokoli člena se považuje za chybu syntaxe. K implementaci jednotlivými členy, zadejte [implementuje](../../../visual-basic/language-reference/statements/implements-clause.md) – klíčové slovo (které jsou oddělené od `Implements` příkaz) Pokud je člen v třídu nebo strukturu deklarovat. Další informace najdete v tématu [rozhraní](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Můžete použít třídy [privátní](../../../visual-basic/language-reference/modifiers/private.md) implementace vlastností a postupy, ale tito členové jsou přístupné pouze přetypování deklarována instance implementující třídu do proměnné být typu rozhraní.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `Implements` příkaz, který má implementace členů rozhraní. Definuje rozhraní s názvem `ICustomerInfo` se událost, vlastnosti a procedury. Třída `customerInfo` implementuje všechny členy, které jsou definované v rozhraní.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 Všimněte si, že třída `customerInfo` používá `Implements` příkazem na řádku samostatného zdrojového kódu k označení, že třída implementuje všechny členy `ICustomerInfo` rozhraní. Poté každý člen ve třídě, používá `Implements` – klíčové slovo v rámci jeho deklarace členů k označení, že implementuje tohoto člena rozhraní.  
  
## <a name="example"></a>Příklad  
 Následující dva postupy ukazují, jak můžete použít rozhraní implementované v předchozím příkladu. Chcete-li otestovat implementace, přidejte tyto postupy projekt a volání `testImplements` postupu.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a>Viz také  
 [Implementuje](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [Interface – příkaz](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Rozhraní](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
