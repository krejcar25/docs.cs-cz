---
title: "Typ pokynů pro návrh"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6b02abef0180b6de82e26837863849cce35c994f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="type-design-guidelines"></a>Typ pokynů pro návrh
Z pohledu CLR existují pouze dvě kategorie typů – reference a hodnotové typy – ale pro účely diskuze o návrhu framework, jsme typy rozdělit do více logických skupin, každou s vlastní pravidla konkrétní návrhu.  
  
 Třídy jsou obecné malá odkazové typy. Tvoří hromadné typů ve většině architektury. Třídy dlužíte jejich oblíbenosti bohaté sada funkce, které podporují a jejich obecné použitelnosti. Základní třídy a abstraktní třídy jsou speciální logické skupiny související s rozšíření.  
  
 Rozhraní jsou typy, které se dají implementovat odkazové typy a typy hodnot. Proto se může sloužit jako kořeny polymorfní hierarchií odkazové typy a typy hodnot. Kromě toho rozhraní slouží k simulaci vícenásobná dědičnost, což není podporováno nativně modulu CLR.  
  
 Struktury jsou obecné případ typů hodnot a by se mělo vyhradit pro malé, jednoduché typy, podobně jako primitiva jazyka.  
  
 Výčty jsou ve speciálním případě typů hodnot se používá k definování krátké sady hodnot, například dny v týdnu, barvy konzoly a tak dále.  
  
 Statické třídy jsou typy by měla být kontejnery pro statické členy. Běžně se používají k poskytování zástupce jiné operace.  
  
 Delegáti, výjimky, atributy, pole a kolekce jsou všechny zvláštních případech odkazové typy určené pro konkrétní účely a pokyny pro jejich využití a návrhu jsou popsané jinde v této příručce.  
  
 **PROVEĎTE ✓** zajistěte, aby byl každý typ dobře definované sadě souvisejících členů, nejen náhodné kolekce funkcí, které nejsou.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Volba mezi třídou a strukturou](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Návrh abstraktní třídy](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Návrh statické třídy](../../../docs/standard/design-guidelines/static-class.md)  
 [Návrh rozhraní](../../../docs/standard/design-guidelines/interface.md)  
 [Návrh struktury](../../../docs/standard/design-guidelines/struct.md)  
 [Návrh výčtu](../../../docs/standard/design-guidelines/enum.md)  
 [Vnořené typy](../../../docs/standard/design-guidelines/nested-types.md)  
 *Části © 2005, 2009 Microsoft Corporation. Všechna práva vyhrazena.*  
  
 *Provedení podle oprávnění Pearson Education, Inc. z [pokynů pro návrh Framework: konvence, Idioms a vzory pro jedno použití knihovny .NET, 2. vydání](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina a Abrams Brada publikovaná 22 Oct 2008 pomocí Designing Effective jako součást vývoj řady Microsoft Windows.*  
  
## <a name="see-also"></a>Viz také  
 [Pokyny k návrhu architektury](../../../docs/standard/design-guidelines/index.md)
