---
title: "Bitové operátory (F#)"
description: "Další informace o bitové operátory, které jsou k dispozici v programovací jazyk F #."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8a2c87f5-b4c7-47fe-8580-82c956f605e5
ms.openlocfilehash: 61a8e6bafe97a229480c967a4afb5d2a256474c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="bitwise-operators"></a>Bitové operátory

Toto téma popisuje bitové operátory, které jsou k dispozici v jazyce F #.

## <a name="summary-of-bitwise-operators"></a>Souhrn bitové operátory
Následující tabulka popisuje bitové operátory, které jsou podporovány pro nezabalený integrální typy v jazyce F #.

|Operátor|Poznámky|
|--------|-----|
|`&&&`|Bitový operátor AND. BITS ve výsledku mít hodnotu 1, pokud odpovídající bity v obou operandy zdroje jsou 1.|
|<code>&#124;&#124;&#124;</code>|Bitový operátor OR. Služba BITS ve výsledku mít hodnotu 1, pokud buď odpovídající bitů ve zdroji jsou operandy 1.|
|`^^^`|Bitový exkluzivní operátor OR. BITS ve výsledku mít hodnotu 1, pokud bitů operandy zdroje mají nerovné hodnoty.|
|`~~~`|Operátor bitovou negaci. Toto je unární operátor a vytváří výsledek, ve kterém všechny 0 bitů operand zdroje se převedou na 1 bits a všechny 1 bits se převedou na 0 bits.|
|`<<<`|Bitový operátor posunutí doleva. Výsledkem je, že první operand s bity zapuštěno podle počtu bitů Druhý operand doleva. Nejsou BITS přesunout mimo nejvýznamnějších pozice otočen do nejméně významný pozici. Nejméně významný bits se vyplní nul. Typ druhý argument je `int32`.|
|`>>>`|Bitový operátor posunutí doprava. Výsledkem je první operand s bity zapuštěno právo podle počtu bitů Druhý operand. Nejsou BITS přesunout mimo nejméně významný pozice otočen do nejvýznamnějších pozici. Pro typy bez znaménka se vyplní nejvýznamnějších bity s nulami. Pro typy signed se s těmi, které vyplní nejvýznamnějších bits. Typ druhý argument je `int32`.|

Bitové operátory můžete použít následující typy: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, a `unativeint`.

## <a name="see-also"></a>Viz také
[Operátor referenční dokumentace symbolů a](index.md)

[Aritmetické operátory](arithmetic-operators.md)

[Logické operátory](boolean-operators.md)

