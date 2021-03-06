---
title: "Vyladění s modifikátorem Async aplikace (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eb5f85701c3b298fea30586797c9411347e8ec84
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="fine-tuning-your-async-application-visual-basic"></a>Vyladění s modifikátorem Async aplikace (Visual Basic)
Přesnost a flexibilitu můžete přidat do aplikací asynchronní pomocí metody a vlastnosti, která <xref:System.Threading.Tasks.Task> typu, bude k dispozici. Témata v této části ukazují příklady, které používají <xref:System.Threading.CancellationToken> a důležitých `Task` metody, jako <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> a <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.  
  
 Pomocí `WhenAny` a `WhenAll`, můžete snadno zahájení více úloh a operátoru await jejich dokončení sledováním jeden úkol.  
  
-   `WhenAny`Vrátí úlohu, která se dokončí při dokončení všech úloh v kolekci.  
  
     Příklady, které používají `WhenAny`, najdete v části [zrušení zbývajících asynchronních úloh po jedné je úplná (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)a [spuštění více úloh s modifikátorem Async a proces je jako jejich dokončení (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
-   `WhenAll`Vrátí úlohu, která je dokončena po dokončení všech úloh v kolekci.  
  
     Další informace a příklad, který používá `WhenAll`, najdete v části [postupy: rozšíření návodu asynchronních podle pomocí metody Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Tato část obsahuje následující příklady.  
  
-   [Zrušení asynchronní úlohy nebo seznamu úloh (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).  
  
-   [Zrušení asynchronních úloh po uplynutí časového intervalu (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [Zrušení zbývajících asynchronních úloh po jedné z nich dokončení (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [Zahájení více úloh s modifikátorem Async a jejich zpracování po dokončení (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  Pro spuštění příkladů, musíte mít Visual Studio 2012 nebo novější a rozhraní .NET Framework 4.5 nebo novější nainstalovaný ve vašem počítači.  
  
 Projekty vytvoření uživatelského rozhraní, která obsahuje tlačítko, které zahájí proces a tlačítko, které se zruší, jak ukazuje následující obrázek. Tlačítka jsou pojmenované `startButton` a `cancelButton`.  
  
 ![Okno WPF s tlačítko Zrušit](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "zrušení")  
  
 Si můžete stáhnout kompletní projekty Windows Presentation Foundation (WPF) z [asynchronní ukázka: jemné ladění vaše aplikace](http://go.microsoft.com/fwlink/?LinkId=255046).  
  
## <a name="see-also"></a>Viz také  
 [Asynchronní programování pomocí modifikátoru Async a operátoru Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
