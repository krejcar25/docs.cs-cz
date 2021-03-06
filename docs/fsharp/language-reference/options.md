---
title: "Možnosti (F#)"
description: "Naučte se používat možnost F #, nemusí existovat typy při skutečnou hodnotu s názvem hodnota nebo proměnná."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a15b5cf1-9055-4481-918c-4c8a051b5829
ms.openlocfilehash: 537ba69aecc1ab489de63d67c5f9ff857afb4a28
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="options"></a>Možnosti

Typ možnosti v jazyce F # se používá při skutečnou hodnotu nemusí existovat pojmenovaná hodnota nebo proměnná. Možnost má základní typ a může obsahovat hodnotu daného typu, nebo se nemusí mít hodnotu.

## <a name="remarks"></a>Poznámky
Následující kód ukazuje funkci, která generuje typ možnost.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Jak můžete vidět, pokud vstupní `a` je větší než 0, `Some(a)` se vygeneruje.  V opačném `None` se vygeneruje.

Hodnota `None` se používá při možnost nemá skutečnou hodnotu. V opačném výraz `Some( ... )` dává možnost hodnotu. Hodnoty `Some` a `None` jsou užitečné v porovnávání vzorů, stejně jako následující funkce `exists`, která vrátí `true` Pokud možnost má hodnotu a `false` Pokud neexistuje.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Pomocí možnosti
Možnosti běžně se používají při hledání nevrací odpovídající výsledek, jak je znázorněno v následujícím kódu.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

V předchozí kód je seznam vyhledávaná rekurzivně. Funkce `tryFindMatch` trvá funkce predikátu `pred` která vrací logickou hodnotu a seznamu pro vyhledávání. Pokud je nalezen element, který splňuje predikátu, elementy end rekurze a funkce vrátí hodnotu jako možnost ve výrazu `Some(head)`. Rekurze ukončí, pokud je nalezena shoda prázdný seznam. V tomto bodě hodnota `head` nebyl nalezen, a `None` je vrácen.

Mnoho F # knihovny funkce, které vyhledávání kolekci pro hodnotu, která mohou nebo nemusí existovat vraťte se `option` typu. Podle konvence těchto funkcí začínají `try` předpony, například [ `Seq.tryFindIndex` ](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a).

Možnosti může být užitečné také při hodnotu, nemusí existovat, například pokud je možné, že bude vyvolána výjimka, když jste pokusily vytvořit hodnotu. Následující příklad kódu to dokládá.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

`openFile` Funkce v předchozím příkladu má typ `string -> File option` protože vrátí `File` objektu, pokud soubor se otevře úspěšně a `None` Pokud dojde k výjimce. V závislosti na situaci nemusí být na odpovídající návrh volbu k zachycení výjimku namísto povolení její šíření.


## <a name="option-properties-and-methods"></a>Možnost Vlastnosti a metody
Typ možnosti podporuje následující vlastnosti a metody.



|Vlastnosti nebo metody|Typ|Popis|
|------------------|----|-----------|
|[None](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|Statické vlastnosti, která vám umožní vytvořit hodnotu možnosti, který má `None` hodnotu.|
|[Isnone –](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|Vrátí `true` Pokud má možnost `None` hodnotu.|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|Vrátí `true` Pokud možnost má hodnotu, která není `None`.|
|[Některé](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|Statický člen, který vytvoří možnost, která má hodnotu, která není `None`.|
|[Hodnota](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|Vrátí základní hodnotu, nebo vyvolá `System.NullReferenceException` Pokud je hodnota `None`.|

## <a name="option-module"></a>Option – modul
Je-li modul [možnost](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), který obsahuje užitečné funkce, které provádění operací na možnosti. Některé funkce opakujte funkci vlastností, ale jsou užitečné v kontextu, kde je potřeba funkce. [Option.issome –](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) a [Option.isnone –](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) jsou obě funkce modulu, které otestovat, zda je možnost obsahuje hodnotu. [Option.Get –](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) získá hodnotu, pokud existuje. Pokud není žádná hodnota, vyvolá `System.ArgumentException`.

[Option.Bind –](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) funkce provádí funkce na hodnotu, pokud je hodnota. Funkce musí mít právě jeden argument a její typ parametru musí být typ možnosti. Vrácená hodnota funkce je jiný typ možnost.

Modul možnost také obsahuje funkce, které odpovídají na funkce, které jsou k dispozici pro seznamy, pole, pořadí a ostatní typy kolekcí. Tyto funkce patří [ `Option.map` ](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622), [ `Option.iter` ](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191), [ `Option.forall` ](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428), [ `Option.exists` ](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99), [ `Option.foldBack` ](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb), [ `Option.fold` ](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8), a [ `Option.count` ](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876). Tyto funkce povolit možnosti, které má být použit jako kolekci elementů žádnou nebo jednu. Další informace a příklady naleznete v tématu diskuzi o kolekce funkcí v [uvádí](lists.md).


## <a name="converting-to-other-types"></a>Převod na jiné typy
Možnosti lze převést na seznamů nebo polí. Při možnost na některou z těchto datových struktur, výsledná datová struktura má nula nebo jeden element. Chcete-li možnost převod na pole, použijte [ `Option.toArray` ](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64). Chcete-li možnost převést do seznamu, použijte [ `Option.toList` ](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1).


## <a name="see-also"></a>Viz také
[Referenční dokumentace jazyka F #](index.md)

[Typy F #](fsharp-types.md)
