---
title: "Zpracování souboru XML (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e8b4c078ffcf7ba7690b7f3dd61bfab4162dd2cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="processing-the-xml-file-c-programming-guide"></a>Zpracování souboru XML (Průvodce programováním v C#)
Kompilátor generuje řetězec ID pro každý konstrukce ve vašem kódu, který se označí ke generování dokumentace. (Informace o tom, jak označit kódu najdete v tématu [doporučené značky pro dokumentační komentáře](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).) ID řetězec jednoznačně identifikuje konstruktu. Programy, které zpracovávají souboru XML slouží k identifikaci příslušnou položku metadata nebo reflexe rozhraní .NET Framework, která se použije v dokumentaci k ID řetězec.  
  
 Soubor XML není znázornění hierarchické kódu; je plochý seznam, který má generovaný ID pro každý prvek.  
  
 Kompilátor dodržuje následující pravidla, když ji vygeneruje ID řetězce:  
  
-   Je bez prázdných znaků v řetězci.  
  
-   První část řetězec ID identifikuje druh člen se identifikuje, prostřednictvím jednoho znaku následovaným dvojtečkou. Se používají následující typy členů:  
  
    |Znak|Popis|  
    |---------------|-----------------|  
    |N|– obor názvů<br /><br /> Dokumentační komentáře nelze přidat do oboru názvů, ale můžete vytvořit cref odkazy, pokud je podporována.|  
    |T|Typ: třída, rozhraní, struktura, enum, delegát|  
    |F|pole|  
    |P|vlastnosti (včetně indexery nebo jiných indexované vlastnosti)|  
    |M|(včetně takových speciální metody jako konstruktory, operátory a tak dále) – metoda|  
    |E|event|  
    |!|Řetězec chyby.<br /><br /> Zbývající řetězec poskytuje informace o této chybě. Kompilátor jazyka C# generuje informace o chybě pro odkazy, které nelze vyřešit.|  
  
-   Druhá část řetězce, který je plně kvalifikovaný název položky začínající na kořen oboru názvů. Název položky, jeho nadřazených typů a obor názvů jsou odděleny tečkami. Pokud má název samotné položky období, se nahrazují znak hash (#). Předpokládá se, že žádná položka má znaménkem hash přímo v jeho názvu. Například by plně kvalifikovaný název konstruktor řetězec "System.String.#ctor".  
  
-   Pro vlastnosti a metody Pokud jsou argumenty pro metodu, seznam argumentů uzavřený v závorkách následuje. Pokud neexistují žádné argumenty, jsou k dispozici žádné závorek. Argumenty, které jsou oddělené čárkami. Kódování každý argument dodržuje přímo jak je zakódován v rozhraní .NET Framework podpis:  
  
    -   Základní typy. Regulární typy (ELEMENT_TYPE_CLASS nebo Typ ELEMENT_TYPE_VALUETYPE, který), jsou reprezentovány jako plně kvalifikovaný název typu.  
  
    -   Vnitřní typy (například ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF. a ELEMENT_TYPE_VOID) jsou reprezentovány jako plně kvalifikovaný název typu odpovídající úplné. Například System.Int32 nebo System.TypedReference.  
  
    -   ELEMENT_TYPE_PTR je reprezentován jako ' *' následující změny typu.  
  
    -   Typu ELEMENT_TYPE_BYREF je reprezentován jako ' @' následující změny typu.  
  
    -   ELEMENT_TYPE_PINNED je reprezentován jako ' ^' následující změny typu. Kompilátor jazyka C# nikdy vygeneruje.  
  
    -   ELEMENT_TYPE_CMOD_REQ je reprezentován jako "&#124; a plně kvalifikovaný název třídy modifikátor následující změny typu. Kompilátor jazyka C# nikdy vygeneruje.  
  
    -   ELEMENT_TYPE_CMOD_OPT je reprezentován jako '!' a plně kvalifikovaný název třídy modifikátor následující změny typu.  
  
    -   ELEMENT_TYPE_SZARRAY je reprezentován jako ["]" následující element typ pole.  
  
    -   ELEMENT_TYPE_GENERICARRAY je reprezentován jako "[?]" následující element typ pole. Kompilátor jazyka C# nikdy vygeneruje.  
  
    -   ELEMENT_TYPE_ARRAY je reprezentován jako [*dolní hranice*:`size`,*dolní hranice*:`size`] kde je počet čárkami pořadí - 1 a dolní meze a velikost každé dimenze, pokud Označuje, jsou reprezentovány v desítkové soustavě. Pokud není zadán dolní mez nebo velikost, je jednoduše vynechán. Pokud byly vynechány dolní mez a velikosti pro konkrétní dimenzi, ':' je také vynechán. Například dimenzionální 2 pole s 1 jako neurčené velikost a dolní meze je [1:, 1:].  
  
    -   ELEMENT_TYPE_FNPTR je reprezentován jako "= FUNC:`type`(*podpis*)", kde `type` je návratový typ a *podpis* je argumenty metody. Pokud neexistují žádné argumenty, jsou závorky vynechat. Kompilátor jazyka C# nikdy vygeneruje.  
  
     Následující součásti podpis nenachází vzhledem k tomu, že se nikdy používají rozdílné přetížené metody:  
  
    -   Konvence volání  
  
    -   Návratový typ  
  
    -   TYP ELEMENT_TYPE_SENTINEL  
  
-   Pro převod operátory pouze (op_Implicit a op_Explicit) návratovou hodnotu metody zakódován ' ~' následuje návratový typ, jako kódování výše.  
  
-   Pro obecné typy název typu bude následovat back značek a pak číslo určující počet parametrů obecného typu.  Například  
  
     `<member name="T:SampleClass`2" >` is the tag for a type that is defined as `veřejnou třídu SampleClass\<T, U >'.  
  
     Pro metody trvá obecné typy jako parametry, jsou parametry obecného typu zadané jako čísla, kterými back rysky (například \`0, 1).  Každý číslo představující zápis pole s nulovým základem pro obecné parametry typu.  
  
## <a name="examples"></a>Příklady  
 Následující příklady ukazují, jak ID řetězce pro třídu a její členy by vytvořilo:  
  
 [!code-csharp[csProgGuidePointers#21](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/processing-the-xml-file_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 [Průvodce programováním v C#](../../../csharp/programming-guide/index.md)  
 [/ DOC (možnosti kompilátoru C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [Dokumentační komentáře XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
