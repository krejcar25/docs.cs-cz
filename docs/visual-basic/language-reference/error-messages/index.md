---
title: "Chybové zprávy (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- errors [Visual Basic]
- error messages
- trappable errors
- errors [Visual Basic], trappable
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7f5138d430e6737a4a8a47d4a800905dedff660
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="error-messages-visual-basic"></a>Chybové zprávy (Visual Basic)
Při zápisu, kompilaci nebo spuštění aplikace Visual Basic, se může objevit následující typy chyb:  
  
1.  Chyby při návrhu, ke kterým dochází při psaní aplikace v sadě Visual Studio.  
  
2.  Chyby při kompilaci, ke kterým dochází při kompilaci aplikace v sadě Visual Studio nebo na příkazovém řádku.  
  
3.  Běhové chyby, ke kterým dochází při spuštění aplikace v sadě Visual Studio nebo samostatný spustitelný soubor.  
  
 Informace o řešení potíží s konkrétní chyby najdete v tématu [další zdroje pro programátory v jazyce Visual Basic](../../../visual-basic/getting-started/additional-resources.md).  
  
## <a name="run-time-errors"></a>Chyby runtime  
 Pokud aplikace Visual Basic se pokusí provést akce, která systém nemůže spustit, dojde k chybě běhu, a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] vyvolá `Exception` objektu. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]může generovat vlastní chyby o všech datech typ, včetně `Exception` objekty, pomocí `Throw` příkaz. Aplikace můžete identifikovat chyba zobrazením číslo chyby a zprávy zachycení výjimky. Pokud není zachycena chybu, aplikace se ukončí.  
  
 Kód můžete depeše a zkontrolujte chyby. Pokud je kód, který generuje chyby v uzavřít `Try` blok, můžete zachytit chyby výjimce dojde v rámci odpovídající `Catch` bloku. Informace o tom, jak depeše chyby za běhu a reagovat na ně ve vašem kódu najdete v tématu [zkuste... Catch... Finally – příkaz](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="compile-time-errors"></a>Čas chyby kompilace  
 Pokud Visual Basic – kompilátor narazí na problém v kódu, dojde k chybě kompilace. V editoru kódu můžete snadno identifikovat které řádek kódu způsobil chybu, protože vlnovka se zobrazí v části tohoto řádku kódu. Pokud jste buď bodu vlnovkou nebo otevřené, zobrazí se chybová zpráva **seznam chyb**, který také ukazuje další zprávy.  
  
 Pokud má identifikátor vlnovkou a posledního znaku podtržen krátký, můžete vygenerovat zástupnou proceduru pro třídu, konstruktor, metoda, vlastnost, pole nebo výčet. Další informace najdete v tématu [generování před využitím](/visualstudio/ide/visual-csharp-intellisense#generate-from-usage).
  
 Vyřešte upozornění kompilátoru jazyka Visual Basic, je možné napsat kód, který běží rychleji a má méně chyby. Tato upozornění identifikovat kód, který může způsobit chyby, pokud je aplikace spuštěna. Například kompilátor varuje, můžete Pokud se pokusíte volají člena nepřiřazené objektové proměnné, vraťte zpět z funkce bez nastavení návratovou hodnotu nebo spuštění `Try` bloku s chybami v logika pro zachycení výjimky. Další informace o upozornění, včetně toho, jak je zapnout a vypnout, najdete v části [Konfigurace upozornění v jazyce Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).
