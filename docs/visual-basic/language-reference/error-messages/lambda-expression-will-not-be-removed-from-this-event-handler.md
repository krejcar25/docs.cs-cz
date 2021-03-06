---
title: "Výraz lambda nebude z této obslužné rutiny události odebrán."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords: BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a4c57d1f8f41d2d9ebb645d3f2628c32a2c4e4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a>Výraz lambda nebude z této obslužné rutiny události odebrán.
Výraz lambda nebude z této obslužné rutiny události odebrán. Přiřadit výrazu lambda proměnné a použít k přidání a odebrání události.  
  
 Když lambda – výrazy se používají s obslužné rutiny událostí, nemusíte vidět chování, které očekáváte. Kompilátor vygeneruje nová metoda pro každou definici výrazu lambda, i když jsou identické. Proto následující kód zobrazí `False`.  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 Když lambda – výrazy se používají s obslužné rutiny událostí, může to způsobit neočekávané výsledky. V následujícím příkladu výrazu lambda přidal `AddHandler` není odebraná pomocí `RemoveHandler` příkaz.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Sub Main()  
  
        ' The following line adds one listener to the event.  
        AddHandler ProcessInteger, Function(m As Integer) m  
  
        ' The following statement searches the current listeners   
        ' for a match to remove. However, this lambda is not the same  
        ' as the previous one, so nothing is removed.  
        RemoveHandler ProcessInteger, Function(m As Integer) m  
  
    End Sub  
End Module  
```  
  
 Ve výchozím nastavení je tato zpráva upozornění. Další informace o tom, jak skrytí upozornění nebo považovat upozornění jako chyby najdete v tématu [Konfigurace upozornění v jazyce Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID chyby:** BC42326  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Pokud chcete zabránit upozornění a odebrat výrazu lambda, proměnné přiřadit výrazu lambda a použít v obou `AddHandler` a `RemoveHandler` příkazy, jak je znázorněno v následujícím příkladu.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Dim PrintHandler As ProcessIntegerEventHandler  
  
    Sub Main()  
  
        ' Assign the lambda expression to a variable.  
        PrintHandler = Function(m As Integer) m  
  
        ' Use the variable to add the listener.  
        AddHandler ProcessInteger, PrintHandler  
  
        ' Use the variable again when you want to remove the listener.  
        RemoveHandler ProcessInteger, PrintHandler  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>Viz také  
 [Lambda – výrazy](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Volný převod delegáta](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Události](../../../visual-basic/programming-guide/language-features/events/index.md)
