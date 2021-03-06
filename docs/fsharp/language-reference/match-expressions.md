---
title: "Výrazy shody (F#)"
description: "Zjistěte, jak výrazu shody F # poskytuje větvení ovládací prvek, který je založena na porovnávání výrazu sadu vzory."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8854b713-255a-408d-942a-e80ab52fd2a4
ms.openlocfilehash: c8b9be744cfa7bc76f0d663b12abd66f8757fc56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="match-expressions"></a>Výrazy shody

`match` Výraz poskytuje větvení ovládací prvek, který je založena na porovnávání výrazu sadu vzory.

## <a name="syntax"></a>Syntaxe

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a>Poznámky

Výrazy odpovídající vzor umožňují komplexní vytvoření větve na základě porovnání výraz testovací sadu vzory. V `match` výrazu *testovací výraz* se porovná se každý vzor zapnout, a pokud je nalezena shoda, odpovídající *výsledek výrazu* vyhodnotí a výsledná hodnota je Vrátí hodnotu výrazu shody.

Funkce uvedené v předchozí syntaxe pro porovnávání je v které vzor odpovídající provádí okamžitě v argumentu výrazu lambda. Funkce uvedené v předchozí syntaxe pro porovnávání je stejná jako následující.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```    

Další informace o výrazy lambda najdete v tématu [výrazy Lambda: `fun` – klíčové slovo](functions/lambda-expressions-the-fun-keyword.md).

Celou sadu vzory by mělo zahrnovat všechny možné shody vstupní proměnné. Často používají vzorec zástupný znak (`_`) jako poslední vzorek tak, aby odpovídaly všechny dříve neodpovídající vstupní hodnoty.

Následující kód ukazuje některé způsoby, ve kterém `match` použit výraz. Odkaz a příklady možných vzorů, které lze použít, najdete v části [porovnávání vzorů](pattern-matching.md).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Chrání vzory

Můžete použít `when` klauzule zadejte další podmínky, které proměnnou, musí vyhovovat tak, aby odpovídaly vzor. Tato klauzule odkazuje jako *ochrana*. Následující výraz `when` – klíčové slovo, nebude hodnocen pouze tehdy, pokud shoda se se vzorem přidružené k této ochrana.

Následující příklad ukazuje použití ochranu k určení číselný rozsah pro proměnné vzor. Všimněte si, že více podmínek jsou spojeny použitím logické operátory.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Všimněte si, že vzhledem k tomu, že hodnoty než literály nelze použít ve vzoru, musíte použít `when` klauzule, pokud máte k porovnání některé části vstup pro hodnotu. To je znázorněno v následujícím kódu.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

## <a name="see-also"></a>Viz také

[Referenční dokumentace jazyka F #](index.md)

[Aktivní vzorky](active-patterns.md)

[Shoda vzoru](pattern-matching.md)
