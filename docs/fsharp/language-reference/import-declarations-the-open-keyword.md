---
title: "Deklarace importu: Klíčové slovo open (F#)"
description: "Další informace o deklarace importu F # a jak určit modul nebo obor názvů jehož elementy bez použití plně kvalifikovaný název, můžete odkazovat."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1e98e48c-52e9-4314-8954-85d5583125f0
ms.openlocfilehash: a6d79bed3dd202657d06956edf9499a9b21a5f03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="import-declarations-the-open-keyword"></a>Deklarace importu: `open` – klíčové slovo

> [!NOTE]
Referenční dokumentace rozhraní API odkazů v tomto článku se dostanete na webu MSDN.  Referenční dokumentace rozhraní API docs.microsoft.com není dokončena.

*Importovat deklarace* určuje modulu nebo obor názvů, jehož elementy bez použití plně kvalifikovaný název, můžete odkazovat.


## <a name="syntax"></a>Syntaxe

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Poznámky
Odkazování na kód pomocí plně kvalifikovaná cesta oboru názvů nebo modul pokaždé, když můžete vytvořit kód, který je pevný ke čtení, zápisu a údržbu. Místo toho můžete použít `open` – klíčové slovo pro často používané moduly a obory názvů, takže když odkazujete členem tohoto modulu nebo obor názvů, můžete použít zkratka pro název místo plně kvalifikovaný název. This – klíčové slovo je podobná `using` – klíčové slovo v jazyce C#, `using namespace` v jazyce Visual C++, a `Imports` v jazyce Visual Basic.

Modul, nebo zadat obor názvů musí být ve stejném projektu nebo v odkazované projektu nebo sestavení. Pokud není, můžete přidat odkaz na projekt, nebo použít `-reference` příkaz`-`možnost řádek (nebo jeho zkratkou `-r`). Další informace najdete v tématu [– možnosti kompilátoru](compiler-options.md).

Deklarace importu zpřístupňuje názvy v kódu, který následuje deklaraci do konce nadřazených obor názvů, modulu nebo souboru.

Pokud používáte více deklarace importu, by se zobrazit na samostatné řádky.

Následující kód ukazuje použití `open` – klíčové slovo zjednodušit kód.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

Kompilátor jazyka F # není emitování chybě nebo upozornění při nejednoznačnosti dojít, když se stejným názvem v více než jeden otevřete modul nebo oboru názvů dojde. Pokud dojde k nejednoznačnosti, F # dává přednost posledních otevřených modul, nebo obor názvů. Například v následujícím kódu `empty` znamená `Seq.empty`, i když `empty` se nachází v obou `List` a `Seq` moduly.

```fsharp
open List
open Seq
printfn "%A" empty
```

Proto buďte opatrní při otevření moduly nebo obory názvů, jako `List` nebo `Seq` obsahující členy, kteří mají stejné názvy; místo toho zvažte použití kvalifikované názvy. Neměli byste každé situaci, ve kterém je závislý na pořadí deklarace importu kód.


## <a name="namespaces-that-are-open-by-default"></a>Obory názvů, které jsou otevřené ve výchozím nastavení
Některé obory názvů, často se používá v F # – kód, aby se implicitně otevřena bez nutnosti deklarace explicitní import. V následující tabulce jsou obory názvů, které jsou otevřené ve výchozím nastavení.

|Obor názvů|Popis|
|---------|-----------|
|`Microsoft.FSharp.Core`|Obsahuje základní definice typů F # pro vestavěné typy, jako `int` a `float`.|
|`Microsoft.FSharp.Core.Operators`|Obsahuje základní aritmetické operace, jako `+` a `*`.|
|`Microsoft.FSharp.Collections`|Obsahuje třídy neměnné kolekce, jako `List` a `Array`.|
|`Microsoft.FSharp.Control`|Obsahuje typy pro ovládací prvek konstrukce, jako je například opožděné vyhodnocení a asynchronní pracovní postupy.|
|`Microsoft.FSharp.Text`|Obsahuje funkce pro formátovaný vstupně-výstupní operace, jako jsou například `printf` funkce.|

## <a name="autoopen-attribute"></a>AutoOpen – atribut
Můžete použít `AutoOpen` atribut k sestavení, pokud chcete automaticky otevřít obor názvů nebo modul při odkazování na sestavení. Můžete taky použít `AutoOpen` atribut modul Tenhle modul otvírat automaticky při otevření nadřazeného modulu nebo obor názvů. Další informace najdete v tématu [Core.autoopenattribute – třída](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).


## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess – atribut
Některé moduly, záznamy nebo typy union může určovat `RequireQualifiedAccess` atribut. Když odkazujete elementy těchto modulů, záznamy nebo sjednocení, musíte použít kvalifikovaný název bez ohledu na to, zda obsahují deklarace importu. Pokud používáte tento atribut strategicky na typy, které definují běžně používat názvy, pomoci vyhnout kolize názvů a tím provést kód pružnější změny v knihovnách. Další informace najdete v tématu [Core.requirequalifiedaccessattribute – třída](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).


## <a name="see-also"></a>Viz také
[# Referenční dokumentace jazyka](index.md)

[Obory názvů](namespaces.md)

[Moduly](modules.md)

