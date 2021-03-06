---
title: "Objektové výrazy (F#)"
description: "Naučte se používat objektové výrazy F # Pokud chcete, aby se zabránilo další kód a režijní náklady na potřebné pro vytvoření nové, s názvem typu."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c6dcf4c9-e7fd-4eee-9e4e-1176f4c27f57
ms.openlocfilehash: 28660d430473de02a8a55e37a26609827b364012
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="object-expressions"></a>Objektové výrazy

*Objektu výraz* je výraz, který vytvoří novou instanci typu dynamicky vytvořený, anonymní objekt, který je založen na existující základní typ, rozhraní nebo sadu rozhraní.


## <a name="syntax"></a>Syntaxe

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Poznámky
V předchozích syntaxi *typename* představuje existující typu třídy nebo rozhraní. *parametry typu* popisuje parametry volitelné obecného typu. *Argumenty* se používají pouze pro typy tříd, které vyžadují parametry konstruktor. *Člen definice* přepsání metody třídy base nebo implementace metod abstraktní základní třídu nebo rozhraní.

Následující příklad ukazuje několik různých typů objektové výrazy.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>Použitím objektových výrazů
Objektové výrazy používají, když budete chtít vyhnout navíc kód a režijní náklady, který je potřeba vytvořit novou, s názvem typu. Pokud používáte objektové výrazy minimalizovat počet typy vytvořené v programu, můžete snížit počet řádků kódu a zabránit zbytečné rozšíření typy. Místo vytváření mnoho typů pouze pro zpracování konkrétních situacích, můžete použít objekt výraz, který upravuje existující typ nebo poskytuje odpovídající implementace rozhraní pro konkrétní případ po ruce.


## <a name="see-also"></a>Viz také
[Referenční dokumentace jazyka F #](index.md)
