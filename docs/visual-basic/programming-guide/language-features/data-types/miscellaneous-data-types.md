---
title: "Různé datové typy (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6bb86bb6d203aa4e6bdded27a4cb78a8155ddec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="miscellaneous-data-types-visual-basic"></a>Různé datové typy (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]poskytuje několik typů dat, které nejsou orientované na číslic nebo znaků. Místo toho budou se týkají specializované data, jako Ano/ne hodnoty, hodnoty data a času a adresy objektu.  
  
 Pro tabulka zobrazující porovnání vedle sebe [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] datové typy, najdete v části [datové typy](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="boolean-type"></a>Typem logická hodnota  
 [Datový typ Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) je bez znaménka hodnota, který je považován za buď `True` nebo `False`. Šířku dat závisí na implementující platformy. Pokud proměnná může obsahovat pouze hodnoty dvou stavů například true nebo false, Ano/Ne, nebo zapnutí nebo vypnutí, deklarujte ji jako `Boolean`.  
  
## <a name="date-type"></a>Date – typ  
 [Date – datový typ](../../../../visual-basic/language-reference/data-types/date-data-type.md) je 64 bitů hodnotu, která obsahuje informace o datu a času. Každý přírůstek představuje 100 nanosekundách uplynulý čas od začátku (12:00:00) z 1. ledna roku 1 v gregoriánském kalendáři. Pokud proměnná může obsahovat hodnotu data a hodnotu čas, deklarujte ji jako `Date`.  
  
## <a name="object-type"></a>Typ objektu  
 [Object – datový typ](../../../../visual-basic/language-reference/data-types/object-data-type.md) 32-bit adresa, která odkazuje na instanci objektu v rámci vaší aplikace nebo v nějaké jiné aplikaci. `Object` Proměnná může označovat libovolného objektu rozpozná aplikace, nebo se data jakéhokoli datového typu. To zahrnuje i *typů hodnot*, jako například `Integer`, `Boolean`a struktura instance, a *odkazové typy*, které jsou instancemi třídy objekty vytvořené ze třídy, jako `String`a <xref:System.Windows.Forms.Form>a pole instance.  
  
 Pokud proměnná obsahuje ukazatel na instanci třídy, která si nejste jisti v době kompilace nebo může ukazovat na data z různých datových typů, deklarujte ji jako `Object`.  
  
 Výhodou `Object` datový typ je, že je můžete použít k ukládání dat jakéhokoli datového typu. Nevýhodou je, být účtovány další operace, které trvat delší dobu spuštění a aby vaše aplikace provést něco pomalejší. Pokud používáte `Object` proměnná pro typy hodnot, platit *zabalení* a *rozbalení*. Pokud ho používáte pro odkazové typy, způsobit *pozdní vazby*.  
  
## <a name="see-also"></a>Viz také  
 [Znaky typu](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Základní datové typy](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Číselné datové typy](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [Znakové datové typy](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Řešení potíží s datové typy](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Statické a pozdní vazby](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
