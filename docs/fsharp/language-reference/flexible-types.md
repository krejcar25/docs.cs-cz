---
title: "Flexibilní typy (F#)"
description: "Další informace o použití F # anotaci typu flexibilní, což znamená, že parametr, proměnné nebo hodnota má typ, který je kompatibilní s zadaného typu."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c8b510f2-3405-4cc9-b55b-e47b35e2b15b
ms.openlocfilehash: 7c5e4eb97791b9c6c56fe2847755866e8240e038
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="flexible-types"></a>Flexibilní typy

A *anotaci typu flexibilní* znamená, že parametr, proměnné nebo hodnota má typ, který je kompatibilní s zadaného typu, kde je určen kompatibility pozici v hierarchii objektově orientované třídy nebo rozhraní. Flexibilní typy jsou užitečné, konkrétně v případě, že automatický převod na typy v hierarchii typu nedojde ale přesto chcete povolit vaší funkce pro práci s libovolného typu v hierarchii nebo žádný typ, který implementuje rozhraní.

## <a name="syntax"></a>Syntaxe

```fsharp
#type
```

## <a name="remarks"></a>Poznámky

V předchozích syntaxi *typ* představuje základní třídu nebo rozhraní.

Flexibilní typ je stejná jako obecný typ, který obsahuje omezení, která omezuje povolené typy pro typy, které jsou kompatibilní s typem základní nebo rozhraní. To znamená že následující dva řádky kódu jsou ekvivalentní.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Flexibilní typy jsou užitečné v situacích několik typů. Například pokud máte vyšší funkci order (funkce, která přebírá funkce jako argument), je často užitečné používat funkce vrátí flexibilní typu. V následujícím příkladu, použití flexibilní typu s argumentem pořadí v `iterate2` umožňuje vyšší pořadí funkce pro práci s funkcí, které generují pořadí, pole, seznamy a další vyčíslitelná typu.

Vezměte v úvahu následující dvě funkce, jeden z které vrátí pořadí, druhé straně, který vrátí typ, flexibilní.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Další příklad, zvažte [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) funkce knihovny:

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

Této funkci můžete projít žádnou z následujících vyčíslitelná pořadí:

- Seznam seznamů
- Seznam polí
- Pole seznamy
- Pole sekvence
- Jiné kombinace vyčíslitelná pořadí

Následující kód používá `Seq.concat` k předvedení scénáře, které můžete podporovat pomocí flexibilní typy.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

Výstup je následující.

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

V F # jako v dalších jazycích objektově orientované jsou kontexty, ve kterých odvozené typy nebo typy, které implementují rozhraní jsou automaticky převedeny na základní typ nebo typ rozhraní. Tyto automatické převody dojít přímé argumenty, ale ne v případě, že typ je v podřízené pozice, v rámci více komplexního typu, jako je například návratovým typem funkce typ, nebo jako argument typu. Flexibilní typu notation tedy užitečné hlavně pokud je součást složitější typu typ, které jsou jeho použití.

## <a name="see-also"></a>Viz také

[Referenční dokumentace jazyka F #](index.md)

[Obecné typy](generics/index.md)
