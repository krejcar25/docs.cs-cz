---
title: "Přizpůsobení výběru objektů dostupných v oboru názvů My (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e5f5be7481ee102074fe1236b91110ee6b1d2944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Přizpůsobení výběru objektů dostupných v oboru názvů My (Visual Basic)
Toto téma popisuje, jak můžete určit, které `My` objekty jsou povoleny, a to nastavením vašeho projektu `_MYTYPE` konstanty podmíněné kompilace. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Integrované vývojové prostředí (IDE) udržuje `_MYTYPE` konstanty podmíněné kompilace pro projekt synchronizována s typem projektu.  
  
## <a name="predefined-mytype-values"></a>Hodnoty předdefinovaných _MYTYPE  
 Je nutné použít `/define` – možnost kompilátoru nastavit `_MYTYPE` konstanty podmíněné kompilace. Při zadání vlastní hodnoty `_MYTYPE` konstantní, je nutné uzavřít řetězcová hodnota v zpětné lomítko nebo uvozovky (\\") pořadí. Například můžete použít:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Tato tabulka ukazuje, co `_MYTYPE` konstanty podmíněné kompilace nastavena pro několik typů projektů.  
  
|Typ projektu|Hodnota _MYTYPE|  
|------------------|--------------------|  
|Knihovna tříd|"Systém Windows"|  
|Konzolová aplikace|"Console"|  
|Web|"Web"|  
|Knihovna webových prvků|"WebControl."|  
|Aplikace systému Windows|"WindowsForms"|  
|Aplikace pro systém Windows při spuštění s vlastní`Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Knihovna ovládacích prvků Windows|"Systém Windows"|  
|Služba systému Windows|"Console"|  
|prázdný|"Prázdný"|  
  
> [!NOTE]
>  Všechny porovnání řetězců podmíněné kompilace se malá a velká písmena, bez ohledu na to, jak `Option Compare` příkaz nastavena.  
  
## <a name="dependent-my-compilation-constants"></a>Konstanty závislé _MY  
 `_MYTYPE` Konstanty podmíněné kompilace naopak řídí několik jiných hodnot `_MY` konstanty kompilace:  
  
|_MYTYPE|_MYAPPLICATIONTYPE|_MYCOMPUTERTYPE|_MYFORMS|_MYUSERTYPE|_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Systém Windows"|Nedefinovaná|"Systém Windows"|HODNOTA TRUE|  
|"Vlastní"|Nedefinovaná|Nedefinovaná|Nedefinovaná|Nedefinovaná|Nedefinovaná|  
|"Prázdný"|Nedefinovaná|Nedefinovaná|Nedefinovaná|Nedefinovaná|Nedefinovaná|  
|"Web"|Nedefinovaná|"Web"|FALSE|"Web"|FALSE|  
|"WebControl."|Nedefinovaná|"Web"|FALSE|"Web"|HODNOTA TRUE|  
|"Systém Windows" nebo ""|"Systém Windows"|"Systém Windows"|Nedefinovaná|"Systém Windows"|HODNOTA TRUE|  
|"WindowsForms"|"WindowsForms"|"Systém Windows"|HODNOTA TRUE|"Systém Windows"|HODNOTA TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Systém Windows"|HODNOTA TRUE|"Systém Windows"|HODNOTA TRUE|  
  
 Ve výchozím nastavení, nedefinované konstanty podmíněné kompilace odkazující na `FALSE`. Při kompilaci projektu přepsat výchozí chování můžete zadat hodnoty pro nedefinované konstanty.  
  
> [!NOTE]
>  Když `_MYTYPE` je nastaven na "Vlastní" projekt obsahuje `My` obor názvů, ale neobsahuje žádné objekty. Nastavení však `_MYTYPE` k "Prázdný" zabrání kompilátoru přidávání `My` obor názvů a jeho objekty.  
  
 Tato tabulka popisuje účinky předdefinované hodnoty `_MY` kompilace konstanty.  
  
|Konstanta|Význam|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Umožňuje `My.Application`, pokud je konstanta "Konzole," Windows "nebo"WindowsForms":<br /><br /> -Verze "Console" je odvozena z <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. a má méně členů, než je verze "Systém Windows".<br />-"Systém Windows" verze je odvozen z <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>a má méně členů, než je verze "WindowsForms".<br />-"WindowsForms" verze `My.Application` je odvozena z <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Pokud `TARGET` konstanta není definován pro "winexe" pak obsahuje třídy `Sub Main` metoda.|  
|`_MYCOMPUTERTYPE`|Umožňuje `My.Computer`, pokud je konstanta "Web" nebo "Systém Windows":<br /><br /> -"Web" verze je odvozena z <xref:Microsoft.VisualBasic.Devices.ServerComputer>, a má méně členů, než je verze "Systém Windows".<br />-"Systém Windows" verze `My.Computer` je odvozena z <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Umožňuje `My.Forms`, pokud je konstanta `TRUE`.|  
|`_MYUSERTYPE`|Umožňuje `My.User`, pokud je konstanta "Web" nebo "Systém Windows":<br /><br /> -"Web" verze `My.User` souvisí s identitu uživatele aktuální žádosti HTTP.<br />-"Systém Windows" verze `My.User` souvisí s aktuální objekt zabezpečení vlákna.|  
|`_MYWEBSERVICES`|Umožňuje `My.WebServices`, pokud je konstanta `TRUE`.|  
|`_MYTYPE`|Umožňuje `My.Log`, `My.Request`, a `My.Response`, pokud je konstanta "Web".|  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Jak Moje závisí na typu projektu](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 [Podmíněná kompilace](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [My.Forms – objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.Request – objekt](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [My.Response – objekt](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [My.WebServices – objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
