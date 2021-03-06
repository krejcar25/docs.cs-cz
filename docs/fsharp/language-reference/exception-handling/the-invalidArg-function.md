---
title: "Výjimky: Funkce invalidArg (F#)"
description: "Zjistěte, jak funkce 'invalidArg' F # vygeneruje výjimku argument."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d375b704-6b27-493e-bd1d-ee217a53c4b5
ms.openlocfilehash: 107bef361a6bd034e3d6a2227e18cf64b1b04576
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-invalidarg-function"></a>Výjimky: Funkce invalidArg

`invalidArg` Funkce vyvolá výjimku argumentu.


## <a name="syntax"></a>Syntaxe

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Poznámky
Název parametru v předchozí syntaxi je řetězec s názvem parametr, jehož argument byl neplatný. *Řetězec chybové zprávy* řetězcový literál nebo se hodnota typu `string`. Bude `Message` vlastnost objekt výjimky.

Výjimky generovaných `invalidArg` je `System.ArgumentException` výjimka. Následující kód ukazuje použití `invalidArg` vyvolá výjimku.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

Výstupem je následující příkaz, za nímž následuje trasování zásobníku (není vidět).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Viz také
[Zpracování výjimek](index.md)

[Typy výjimek](exception-types.md)

[Výjimky: `try...with` výraz](the-try-with-expression.md)

[Výjimky: `try...finally` výraz](the-try-finally-expression.md)

[Výjimky: `raise` – funkce](the-raise-function.md)

[Výjimky: `failwith` – funkce](the-failwith-function.md)
