---
title: "foreach, in (Referenční dokumentace jazyka C#)"
ms.date: 10/11/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d5601682d53a01ff07aba7e416aa81ded4c03e4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="foreach-in-c-reference"></a>foreach, in (Referenční dokumentace jazyka C#)
`foreach` Příkaz opakuje skupinu embedded příkazy pro každý prvek v pole nebo kolekci objekt, který implementuje <xref:System.Collections.IEnumerable?displayProperty=nameWithType> nebo <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> rozhraní. `foreach` Příkaz se používá k procházení kolekce se získat informace, které, ale nelze použít k přidání nebo odebrání položky z kolekce zdroj předejdete nepředvídatelným vedlejší účinky. Pokud potřebujete přidat nebo odebrat položky z kolekce zdroje, použijte [pro](for.md) smyčky.
  
 Vložené příkazů pokračovat provést pro každý prvek v poli nebo kolekce. Po dokončení iterace pro všechny elementy v kolekci, je ovládací prvek přenesen na další následující příkaz `foreach` bloku.
  
 Kdykoli bodu v rámci `foreach` bloku, můžete rozdělit mimo smyčky pomocí [zalomení](break.md) – klíčové slovo nebo krok do další iterace ve smyčce pomocí [pokračovat](continue.md) – klíčové slovo.

 A `foreach` smyčky můžete také měly být byl ukončen ve [goto](goto.md), [vrátit](return.md), nebo [throw](throw.md) příkazy.

 Další informace o `foreach` – klíčové slovo a ukázky kódu, najdete v následujících tématech:  

 [Použití příkazu foreach s poli](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [Postupy: přístup ke třídě kolekce pomocí příkazu foreach](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a>Příklad
 Následující kód ukazuje tři příklady.

> [!TIP]
> Příklady a experimentovat s syntaxe zkuste jinou použití, které se více podobají váš případ použití, můžete upravit. Stisknutím klávesy "Spustit" spustit kód, potom upravit a znovu stiskněte "Spustit".

-   Typické `foreach` smyčky, která zobrazí obsah pole celých čísel

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   [pro](../../../csharp/language-reference/keywords/for.md) smyčky, která má stejnou funkci

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   `foreach` smyčky, která udržuje počet prvků v poli

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a>Specifikace jazyka C#
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Viz také  

[Referenční dokumentace jazyka C#](../index.md)

[Průvodce programováním v C#](../../programming-guide/index.md)

[Klíčová slova jazyka C#](index.md)

[Příkazy iterace](iteration-statements.md)

[pro](for.md)
