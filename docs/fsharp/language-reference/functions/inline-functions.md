---
title: "Vložené funkce (F#)"
description: "Další informace o použití F # vložené funkce, které jsou integrovány přímo volající kód."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3fa31178-08f8-463d-9d41-d29220a90027
ms.openlocfilehash: 0489d411e2754eaab6a10ff0feb4405491b3b511
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2017
---
# <a name="inline-functions"></a>Vložené funkce

*Vložené funkce* jsou funkce, které jsou integrovány přímo volající kód.


## <a name="using-inline-functions"></a>Pomocí vložené funkce
Použijete-li parametry statické typu, musí být všechny funkce, které jsou parametry podle parametrů typu vložené. To zaručuje, že kompilátor mohou vyřešit tyto parametry typu. Při použití parametrů obyčejnou obecného typu neexistuje žádné takových omezení.

Než povolíte využití člen omezení, může být užitečné v optimalizace kódu vložené funkce. Nadměrné vložené funkce však může způsobit kódu méně odolné na změny v kompilátoru optimalizace a provádění – funkce knihovny. Z tohoto důvodu byste neměli používat vložené funkce optimalizace, pokud Pokusili jste se všechny ostatní techniky optimalizace. Provedení vnořené funkce nebo metoda může někdy zlepšit výkon, ale není, vždy. Proto byste měli použít také měření výkonu k ověření, že provedení jakékoli dané funkce vložené ve skutečnosti mít kladný vliv.

`inline` Modifikátor lze použít pro funkce na nejvyšší úrovni, na úrovni modulu nebo na úrovni metody ve třídě.

Následující příklad kódu ukazuje vložená funkce na nejvyšší úrovni, metodu instance vloženého a statickou metodu vložené.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a>Vložené funkce a odvození typu
Přítomnost `inline` ovlivňuje odvození typu. To je proto vložené funkce mohou být statisticky vyřešené parametry typu, zatímco jiné vložené funkce nelze. Následující příklad kódu ukazuje případu kde `inline` je užitečné, protože používáte funkci, která má parametr typu určené statisticky `float` operátor převodu.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

Bez `inline` modifikátor, vynutí odvození typu funkce se má provést konkrétního typu, v takovém případě `int`. Ale `inline` modifikátor, funkce je také odvodit tak, aby měl parametr typu určené statisticky. Pomocí `inline` modifikátor, typ je odvodit být následující:

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

To znamená, že funkce přijímá žádný typ, který podporuje převod na **float**.


## <a name="see-also"></a>Viz také
[Funkce](index.md)

[Omezení](../generics/constraints.md)

[Statisticky vyřešené parametry typu](../generics/statically-resolved-type-parameters.md)
