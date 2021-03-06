---
title: "Refaktoring do čistého funkcí (C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4fe9a9250e0a87ecaa02258526b7cc796de8e387
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="refactoring-into-pure-functions-c"></a>Refaktoring do čistého funkcí (C#)

Důležitým aspektem čistý funkční transformace je naučit se Refaktorovat kódu pomocí čistý funkce.  
  
> [!NOTE]
>  Běžné klasifikace v funkční programování se, že zrefaktorujete programy pomocí čistý funkcí. V jazyce Visual Basic a C++ to zarovnaná s použití funkcí v příslušné jazyky. V jazyce C#, ale funkce se volají metody. Pro účely Tato diskuse se čistou funkci je implementovaný jako metody v jazyce C#.  
  
 Jak je uvedeno dříve v této části, čistou funkci má dva užitečné charakteristiky:  
  
-   Nemá žádné vedlejší účinky. Funkce nezmění žádné proměnné nebo data mimo funkci libovolného typu.  
  
-   Je konzistentní. Zadané stejnou sadu vstupních dat, vždy vrátí stejné výstupní hodnotu.  
  
 Přechod do funkčního programování jeden ze způsobů je refaktorovat stávajícího kódu pro vyloučení nepotřebných vedlejší efekty a externí závislosti. Tímto způsobem můžete vytvořit čistě funkce verzích existujícího kódu.  
  
 Toto téma popisuje je čistě funkce a co není. [Kurz: manipulace s obsahu v dokumentu WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) kurz ukazuje, jak pracovat s dokumentem WordprocessingML a obsahuje dva příklady, jak k refactor pomocí čistou funkci.  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a>Odstranění vedlejší efekty a externí závislosti  
 Následující příklady kontrastu dvě-čistý funkce a čistou funkci.  
  
### <a name="non-pure-function-that-changes-a-class-member"></a>Čistý funkce, která změní člena třídy  
 V následujícím kódu `HyphenatedConcat` funkce není čistou funkci, protože upravuje `aMember` – datový člen třídy:  
  
```csharp  
public class Program  
{  
    private static string aMember = "StringOne";  
  
    public static void HyphenatedConcat(string appendStr)  
    {  
        aMember += '-' + appendStr;  
    }  
  
    public static void Main()  
    {  
        HyphenatedConcat("StringTwo");  
        Console.WriteLine(aMember);  
    }  
}  
```  
  
 Tento kód vytvoří následující výstup:  
  
```  
StringOne-StringTwo  
```  
  
 Všimněte si, že je irelevantní, jestli má data upravována `public` nebo `private` získat přístup, nebo je `static` nebo členem instance. Čistý funkce nemění žádná data mimo funkci.  
  
### <a name="non-pure-function-that-changes-an-argument"></a>Čistý funkce, která změní Argument  
 Následující verze této stejné funkce navíc není čistá, protože upravuje obsah parametru, `sb`.  
  
```csharp  
public class Program  
{  
    public static void HyphenatedConcat(StringBuilder sb, String appendStr)  
    {  
        sb.Append('-' + appendStr);  
    }  
  
    public static void Main()  
    {  
        StringBuilder sb1 = new StringBuilder("StringOne");  
        HyphenatedConcat(sb1, "StringTwo");  
        Console.WriteLine(sb1);  
    }  
}  
```  
  
 Tato verze programu vytváří stejný výstup jako první verze, protože `HyphenatedConcat` funkce změnila hodnota (stav) její první parametr vyvoláním <xref:System.Text.StringBuilder.Append%2A> – členská funkce. Všimněte si, že dojde k této změnou i přes tato skutečnost, `HyphenatedConcat` používá předávání volání hodnotu parametru.  
  
> [!IMPORTANT]
>  U typů odkazu Pokud předáte parametr podle hodnoty, výsledkem kopii odkaz na objekt předávány. Tato kopie je stále spojena se stejná data jako odkaz na původní instanci (dokud proměnnou odkaz je přiřazen k vytvoření nového objektu). Volání odkazem není nezbytně nutné pro funkci, kterou chcete upravit parametr.  
  
### <a name="pure-function"></a>Čistý – funkce  
Tato další verze programu ukazuje, jak implementovat `HyphenatedConcat` fungovat jako čistou funkci.  
  
```csharp  
class Program  
{  
    public static string HyphenatedConcat(string s, string appendStr)  
    {  
        return (s + '-' + appendStr);  
    }  
  
    public static void Main(string[] args)  
    {  
        string s1 = "StringOne";  
        string s2 = HyphenatedConcat(s1, "StringTwo");  
        Console.WriteLine(s2);  
    }  
}  
```  
  
 Znovu, tato verze vytváří na stejný řádek výstupu: `StringOne-StringTwo`. Všimněte si, že pokud chcete zachovat zřetězených hodnota, je uložený v proměnnou zprostředkující `s2`.  
  
 Jeden z přístupů, může být velmi užitečná je zápis funkce, které jsou místně znečištěná (to znamená, že deklarace a upravit místní proměnné), ale jsou globálně čistý. Takové funkce mají mnoho společných vlastností s žádoucí composability, ale některé z více convoluted funkční programovací idioms, jako je například nutnosti použít rekurzi při totéž by provést jednoduché smyčky vyhnout.  
  
## <a name="standard-query-operators"></a>Standardní operátory dotazu  
 Důležitou vlastností objektu standardní operátory dotazu je, že jsou implementované jako čistý funkce.  
  
 Další informace najdete v tématu [standardní přehled operátory dotazu (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Viz také  
 [Úvod do čistého funkční transformace (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [Funkční programování vs. Imperativní programování (C#)](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
