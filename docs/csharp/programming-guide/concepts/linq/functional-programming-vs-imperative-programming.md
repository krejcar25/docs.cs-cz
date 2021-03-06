---
title: "Funkční programování vs. Imperativní programování (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 5e35c5a0-c949-422a-873b-fca6b2254f57
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2c57d89120eee8c7f84d6e87b14f038378a0b3d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="functional-programming-vs-imperative-programming-c"></a>Funkční programování vs. Imperativní programování (C#)
Toto téma porovnává a výrazně liší od funkční programování s tradičnější imperativní programování (procedurální).  
  
## <a name="functional-programming-vs-imperative-programming"></a>Funkční programování vs. Imperativní programování  
 *Funkční programování* zlepší explicitně vytvořil pro podporu čistý funkční přístup k řešení problémů. Funkční programování je forma *deklarativní programování*. Na rozdíl od většiny všeobecně jazyků, včetně objektově orientované programovací jazyky (mimoprocesová aplikace VOLÁNA) například C#, Visual Basic, C++ a Java, byly navrženy pro podporu především *imperativní* programování (procedurální).  
  
 S imperativní přístup vývojář se zapisují kód, který popisuje přesnější podrobné kroky, které počítače musí provést k dosažení cíle. To se někdy označuje jako *algoritmické* programování. Naproti tomu funkční přístupu zahrnuje skládání problém jako sady funkcí, které by šlo spustit. Definujete pečlivě vstup pro jednotlivé funkce, a vrátí co jednotlivé funkce. Následující tabulka popisuje některé obecné rozdíly mezi těmito dvěma přístupy.  
  
|Vlastnosti|Imperativní přístup|Funkční přístup|  
|--------------------|-------------------------|-------------------------|  
|Fokus programátory|Jak provádět úlohy (algoritmy) a jak můžete sledovat změny ve stavu.|Jaké informace se požaduje a jaké transformace jsou povinné.|  
|Změny stavu|Důležité.|Neexistující jiného typu.|  
|Pořadí provádění|Důležité.|Nízkou důležitostí.|  
|Řízení toku na primární|Smyčky, podmínky a volání funkce (metoda).|Volání funkcí, včetně rekurze.|  
|Manipulace s primární jednotka|Instance třídy nebo struktury.|Funkce jako první třídy objektů a dat kolekce.|  
  
 I když většina jazyky byly navrženy pro podporu konkrétní programovací zlepší, mnoha jazycích Obecné jsou dostatečně flexibilní pro podporu více vzorů. Například většina jazyky, které obsahují ukazatele na funkce slouží k podpoře hrozit funkční programování. Kromě toho C# obsahuje explicitní jazyková rozšíření a podporu funkční programování, včetně výrazy lambda odvození typu. Technologie LINQ je forma deklarativní, funkční programování.  
  
## <a name="functional-programming-using-xslt"></a>Funkční programování pomocí XSLT  
 Celá řada vývojářů XSLT se seznámíte s čistě funkční přístup. Co nejúčinnější způsob, jak vyvíjet šablony stylů XSLT je považovat za každé šabloně transformaci izolovaný, bez možnosti složení. Pořadí zpracování je zcela zrušte zvýrazněné. XSLT neumožňuje vedlejší efekty (s jedinou výjimkou uvozovací znaky mechanismy pro provádění kódu procesního můžou představovat vedlejší účinky, jejichž výsledkem funkční nečistot). I když XSLT je nástroj pro efektivní, některé jeho vlastnosti jsou však není optimální. Například vyjadřující programovací konstrukce v XML díky kód relativně podrobné a proto poměrně složitá. Navíc může způsobit velkou spoléhat na rekurze pro řízení toku kód, který je těžko čitelný. Další informace o XSLT najdete v tématu [transformace XSLT](../../../../standard/data/xml/xslt-transformations.md).  
  
 XSLT se ukázalo jako hodnota použití čistý funkční přístupu pro převod XML z jednoho obrazce do jiného. Čistý funkční programování s technologie LINQ to XML je podobné jako v mnoha způsoby XSLT. Programovací konstrukce zavedených v technologii LINQ to XML a C# však umožňují zápisu čistý funkční transformace, které jsou čitelnější a udržovatelný než XSLT.  
  
## <a name="advantages-of-pure-functions"></a>Výhody čistý funkcí  
 Hlavním důvodem pro implementaci funkční transformace jako čistý funkce je, že čistý funkce bez možnosti složení: tedy samostatné a bezstavové. Tyto charakteristiky přineste řadu výhod, včetně následujících:  
  
-   Zvýšená přehlednosti a jeho udržovatelnost. To je vzhledem k tomu, že jednotlivé funkce slouží k provedení určité úlohy uveden její argumenty. Funkce nevyžaduje žádné externí stavu.  
  
-   Snadnější reiterative vývoj. Protože kód je snazší refactor, jsou často usnadňují implementaci změny návrhu. Předpokládejme například, zapsat složitý transformace a pak Uvědomte si, že nějaký kód je opakovaně transformace. Pokud jste Refaktorovat čistý metodou, můžete volat čistý metodu na bude bez obav, vedlejší účinky.  
  
-   Jednodušší testování a ladění. Protože čistý funkce lze snadno testovat v izolaci, můžete napsat testovací kód, který volá funkci čistý s typické hodnoty, platný edge případů a případů neplatný okraj.  
  
## <a name="transitioning-for-oop-developers"></a>Přechod pro vývojáře mimoprocesová aplikace VOLÁNA  
 V tradiční objektově orientované programování (mimoprocesová aplikace VOLÁNA), jsou uzpůsobené pro programování v styl imperativní nebo procedurální Většina vývojářů. Přejděte na vývoj ve stylu čistý funkční, mají proveďte přechod v jejich přemýšlení a jejich přístup pro vývoj.  
  
 K řešení problémů, vývojáři mimoprocesová aplikace VOLÁNA návrh hierarchie tříd, zaměřit na správné zapouzdření a vezměte v úvahu z hlediska kontrakty třídy. Chování a stav typy objektů jsou prvořadý a jazykové funkce, jako jsou třídy, rozhraní, dědičnost a polymorfismus, jsou dostupné k těmto problémům.  
  
 Funkční programování naopak blíží výpočetní problémy jako cvičení při vyhodnocení čistý funkční transformace dat kolekcí. Funkční programování zabraňuje stavu a měnitelný dat a místo toho klade důraz použití funkce.  
  
 Naštěstí C# nevyžaduje úplnou přestupného k programování funkční, protože podporuje imperativní a funkční programovací přístupy. Vývojář rozhodnout, jaký přístup je nejvhodnější pro konkrétní scénář. Ve skutečnosti programy často kombinací obou přístupů.  
  
## <a name="see-also"></a>Viz také  
 [Úvod do čistého funkční transformace (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [Transformace XSLT](../../../../standard/data/xml/xslt-transformations.md)  
 [Refaktoring do čistého funkcí (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
