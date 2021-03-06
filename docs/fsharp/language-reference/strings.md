---
title: "Řetězce (F#)"
description: "Zjistěte, jak typu 'řetězec' F # představuje neměnné text jako posloupnosti znaků Unicode."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: df7624e5-ca6c-4e77-9e2b-87ca7e5e6f52
ms.openlocfilehash: 96a398ebcd53681481b10d1a2bee5f1e5442a5cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="strings"></a>Řetězce

> [!NOTE]
Referenční dokumentace rozhraní API odkazů v tomto článku se dostanete na webu MSDN.  Referenční dokumentace rozhraní API docs.microsoft.com není dokončena.

`string` Typ představuje neměnné text jako posloupnosti znaků Unicode. `string`je alias `System.String` v rozhraní .NET Framework.

## <a name="remarks"></a>Poznámky
Textové literály jsou odděleny znak dvojité uvozovky ("). Znak zpětného lomítka (\) se používá ke kódování některé speciální znaky. Zpětné lomítko a další znak, který je společně se označují jako *řídicí sekvenci*. Řídicí sekvence v F # řetězec, který v následující tabulce jsou uvedeny literály podporovány.

|Znak|Řídicí sekvence|
|---------|---------------|
|Backspace|\b|
|Nový řádek|\n|
|Návrat na začátek řádku|\r|
|Tabulátor|\t|
|Zpětné lomítko|\\|
|Uvozovky|\"|
|Apostrof|\'|
|znak Unicode|\u*XXXX* nebo \U*XXXXXXXX* (kde *X* označuje šestnáctková číslice)|

Pokud před sebou symbolem @, je literál typu verbatim řetězec. To znamená, že jsou ignorovány všechny řídicí sekvence, s tím rozdílem, že dva znaky uvozovek se interpretují jako uvozovky jeden znak.

Kromě toho může být řetězec uzavřena do uvozovek. Trojitá. V takovém případě jsou ignorovány všechny řídicí sekvence, včetně znaků dvojité uvozovky. Pokud chcete zadat řetězec, který obsahuje vložený řetězec v uvozovkách, můžete použít buď typu verbatim řetězec nebo řetězec uvozené třemi uvozovkami. Pokud používáte řetězec typu verbatim, musíte zadat dva znaky uvozovek udávajících znak jednoduché uvozovky. Pokud používáte řetězce uvozené třemi uvozovkami, můžete vytvořit jednoduché uvozovky znaky bez nich při analýze jako konci řetězce. Tento postup může být užitečné při práci s XML nebo jiné struktury, které zahrnují uvozovky.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

V kódu jsou podmínky přijaty řetězce, které mají konce řádků a konce řádků se interpretují oznámena jako vložení znaků newline, pokud je znak zpětného lomítka poslední znak před koncem řádku. Úvodní mezery na další řádek je ignorována, pokud se používá znak zpětného lomítka. Následující kód vytvoří řetězec `str1` s hodnotou `"abc\n     def"` řetězec a `str2` s hodnotou `"abcdef"`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

Pomocí syntaxe pro pole, dostanete jednotlivé znaky v řetězci.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

Výstupem je `b`.

Nebo můžete rozbalit dílčích řetězců pomocí syntaxe řez pole, jak je znázorněno v následujícím kódu.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

Výstup je následující.

```
abc
def
```

Může představovat ASCII řetězce podle pole bajtů bez znaménka, typ `byte[]`. Můžete přidat příponu `B` na řetězcový literál to znamená, že je řetězec ve formátu ASCII. Použít s pole bajtů ASCII textové literály podporují stejné řídicí sekvence jako řetězců v kódu Unicode, s výjimkou řídicích sekvencí kódování Unicode.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a>Operátory řetězce
Zřetězení řetězců dvěma způsoby: pomocí `+` operátor nebo pomocí `^` operátor. `+` Operátor udržuje kompatibilitu s zpracování funkce řetězce rozhraní .NET Framework.

Následující příklad ilustruje zřetězení řetězců.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a>Řetězec – třída
Protože je ve skutečnosti rozhraní .NET Framework typ řetězce v jazyce F # `System.String` typ, všechny `System.String` členové jsou k dispozici. To zahrnuje `+` operátor, který slouží ke zřetězení řetězců `Length` vlastnost a `Chars` vlastnost, která vrací řetězec jako pole znaků Unicode. Další informace o řetězcích najdete v tématu `System.String`.

Pomocí `Chars` vlastnost `System.String`, dostanete jednotlivé znaky v řetězci zadáním index, jak je znázorněno v následujícím kódu.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a>Řetězec modulu
Další funkce pro zpracování řetězce je součástí `String` modulu v `FSharp.Core` oboru názvů. Další informace najdete v tématu [Core.String – modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Viz také
[Referenční dokumentace jazyka F #](index.md)
