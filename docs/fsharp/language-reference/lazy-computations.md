---
title: "Opožděné výpočty (F#)"
description: "Zjistěte, jak vylepšit výkon aplikace a knihovny F # opožděné výpočty."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="lazy-computations"></a>Opožděné výpočty

*Opožděné výpočty* jsou výpočty, které se nevyhodnotily okamžitě, ale místo toho vyhodnocují potřeby výsledek. To vám může pomoct zlepšit výkon vašeho kódu.

## <a name="syntax"></a>Syntaxe

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Poznámky

V předchozích syntaxi *výraz* je kód, který se vyhodnotí jenom v případě, že v důsledku toho je nutné, a *identifikátor* je hodnota, která ukládá výsledek. Hodnota je typu [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), kde skutečnou typu se používá pro `'T` se určí na základě výsledku výraz.

Opožděné výpočty umožňují vylepšit výkon, omezení provádění výpočtu pouze situací, ve kterých je potřeba výsledku.

Chcete-li vynutit výpočet provést, volejte metodu `Force`. `Force`způsobí, že provádění provést pouze jednou. Následující volání `Force` vrátí stejné vést, ale nemůžou provést žádný kód.

Následující kód ukazuje použití opožděné výpočty a použití `Force`. V tomto kódu typ `result` je `Lazy<int>`a `Force` metoda vrátí `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Opožděné vyhodnocení, ale ne `Lazy` typem, se taky používá pro pořadí. Další informace najdete v tématu [pořadí](sequences.md).

## <a name="see-also"></a>Viz také

[Referenční dokumentace jazyka F #](index.md)

[Lazyextensions – modul](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
