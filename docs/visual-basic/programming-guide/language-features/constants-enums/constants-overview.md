---
title: "Přehled konstant (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6526f7270602b3e1a4e8d953732c393ff252b2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="constants-overview-visual-basic"></a>Přehled konstant (Visual Basic)
Konstanta je smysluplný název, který probíhá číslo nebo řetězec, který se nemění. Konstanty ukládat hodnoty, které jak již název napovídá, zůstávají stejné v celé spuštění aplikace. Může výrazně zlepšit čitelnost kódu a bylo snazší spravovat pomocí konstanty. Použít na kód, který obsahuje hodnoty, které se znovu objeví nebo který závisí na určitých čísla, která je obtížné mějte na paměti, nebo nemají zřejmé význam.  
  
## <a name="how-to-create-and-use-constants"></a>Postup vytvoření a použití konstant  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]obsahuje řadu předdefinovaných konstanty, především pomocí pro tisk a zobrazení. Můžete také vytvořit vlastní konstanty s `Const` příkaz, pomocí stejné pokyny byste pro vytvoření název proměnné. Pokud `Option Strict` je `On`, je potřeba explicitně deklarovat typu konstanty.  
  
 Obor konstanta, což je sada všechen kód, který může na ni odkazuje bez určení názvu, je stejný jako u proměnná definovaná ve stejném umístění. Pokud chcete vytvořit konstanta, která existuje v rámci oboru určitého postupu, deklarujte ji uvnitř tohoto postupu. Pokud chcete vytvořit konstanta, která je k dispozici v celé aplikaci, deklarujte ji pomocí `Public` – klíčové slovo v sekci deklarace třídy.  
  
> [!NOTE]
>  I když konstanty poněkud vypadat proměnné, nelze je upravit ani k nim přiřadíte nové hodnoty jako do proměnné.  
  
 Konstanty používáte ve vašem kódu lze definovat pro ovládací prvky a součásti pracujete s modelem objektu, nebo mohou být uživatelem definované (tedy těch, které můžete vytvořit sami).  
  
## <a name="compile-time-and-run-time-constants"></a>Kompilace a běhu konstanty  
 Konstanta kompilace se počítá v době, kdy je zkompilovat kód, během spuštění konstanta můžete výpočtu pouze, když aplikace běží. Konstanta kompilaci bude mít stejnou hodnotu pokaždé, když je aplikace spuštěna při spuštění konstanta může změnit pokaždé, když. Konstanty kompilace jsou požadovány pro případech, jako jsou meze pole, výrazy case nebo inicializátory enumerátor.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Definice|Termín|  
|---|---|  
|[Postupy: deklarace konstanty](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Vysvětluje, jak používat `Const` příkaz deklarace konstanty a nastavení jeho hodnoty; deklarováním konstanta přiřadíte hodnotě nějaký výstižný název.|  
|[Uživatelem definované konstanty](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Popisuje, jak vytvořit vlastní konstanty, včetně informací o rozsahu a jak se vyhnout. cyklické odkazy.|  
|[Datové typy konstanty a literálu](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Poskytuje informace o tom, jak [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kompilátoru inicializuje konstanty při `Option Explicit` je vypnutý.|  
|[Postupy: seskupení souvisejících hodnot konstant společně](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Ukazuje, jak seskupit konstantní hodnoty, které se vztahují.|  
  
## <a name="reference"></a>Odkaz  
  
|Definice|Termín|  
|---|---|  
|[Konstanty a výčty](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Uvádí konstanty předdefinovaná v nástroji [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].|  
|[Const – příkaz](../../../../visual-basic/language-reference/statements/const-statement.md)|Popisuje `Const` prohlášení a jeho použití.|  
|[Option Strict – příkaz](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Popisuje `Option Strict` prohlášení a jeho použití.|  
  
## <a name="see-also"></a>Viz také  
 [Přehled výčtů](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Postupy: Inicializace proměnné pole v jazyce Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
