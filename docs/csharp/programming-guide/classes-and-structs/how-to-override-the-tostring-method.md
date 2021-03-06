---
title: "Postupy: Potlačení metody ToString (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5b0f7bf35e5bd565e0bfa46fe91cf86aedcd2d8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>Postupy: Potlačení metody ToString (Průvodce programováním v C#)
Každé třídě nebo struktuře v jazyce C# implicitně dědí <xref:System.Object> třídy. Proto získá každý objekt v jazyce C# <xref:System.Object.ToString%2A> metoda, která vrátí řetězcovou reprezentaci tohoto objektu. Například všechny proměnné typu `int` mít `ToString` metoda, která umožňuje, aby vrátila jejich obsah jako řetězec:  
  
 [!code-csharp[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 Když vytvoříte vlastní třídě nebo struktuře, by měly přepsat <xref:System.Object.ToString%2A> za účelem zadání informací o typu vašeho kódu klienta.  
  
 Informace o tom, jak používat formát řetězci a ostatními typy vlastní formátování s `ToString` metodu, najdete v části [typy formátování](../../../standard/base-types/formatting-types.md).  
  
> [!IMPORTANT]
>  Pokud se rozhodnete, jaké informace, které poskytují prostřednictvím této metody, zvažte, jestli třídě nebo struktuře někdy použije nedůvěryhodnému kódu. Dávejte pozor, aby neposkytují veškeré informace, které může zneužít škodlivý kód.  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a>K potlačení metody ToString ve třídě nebo struktuře  
  
1.  Deklarace `ToString` metoda s následující parametry a návratový typ:  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  Implementujte metodu tak, že vrátí řetězec.  
  
     Následující příklad vrátí název třídy kromě dat podle konkrétní instance třídy.  
  
     [!code-csharp[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     Můžete otestovat `ToString` metoda, jak je znázorněno v následujícím příkladu kódu:  
  
     [!code-csharp[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.IFormattable>  
 [Průvodce programováním v C#](../../../csharp/programming-guide/index.md)  
 [Třídy a struktury](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Řetězce](../../../csharp/programming-guide/strings/index.md)  
 [řetězec](../../../csharp/language-reference/keywords/string.md)  
 [Nový](../../../csharp/language-reference/keywords/new.md)  
 [přepsání](../../../csharp/language-reference/keywords/override.md)  
 [virtuální](../../../csharp/language-reference/keywords/virtual.md)  
 [Typy formátování](../../../standard/base-types/formatting-types.md)
