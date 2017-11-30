---
title: "Postupy: Zpracování chyb a výjimek, k nimž došlo v souvislosti s datovou vazbou"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a78612fc17eea01508dcba9247ece68be2e19a76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a>Postupy: Zpracování chyb a výjimek, k nimž došlo v souvislosti s datovou vazbou
Často výjimek a chyb dojde na základní objekty obchodní vazby na ovládací prvky. Tyto chyby a výjimky zachytit a potom můžete buď obnovit nebo předávat informace o chybě pro uživatele ve zpracování <xref:System.Windows.Forms.Binding.BindingComplete> událostí pro konkrétní <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, nebo <xref:System.Windows.Forms.CurrencyManager> součásti.  
  
## <a name="example"></a>Příklad  
 Tento příklad kódu ukazuje, jak zpracování chyb a výjimek, ke kterým došlo během vazby dat operace. Ukazuje, jak zachytávat chyby ve zpracování <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> události <xref:System.Windows.Forms.Binding> objekty. Při zpracování této událost zachytávat chyby a výjimky, je nutné aktivovat formátování pro vazbu. Můžete povolit formátování, pokud vazba je vytvořená nebo přidat do kolekce vazby, nebo nastavením <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> vlastnost `true`.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 Kdy kód běží a je prázdný řetězec zadaný pro název součásti nebo hodnotu menší než 100 je zadán pro výrobní číslo, zobrazí se okno se zprávou. To je způsobeno tím, zpracování <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> událost pro tyto vazby textové pole.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Odkazy na systém, System.Drawing a System.Windows.Forms sestavení.  
  
 Informace o sestavení z příkazového řádku pro tento příklad [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] nebo [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], najdete v části [sestavení z příkazového řádku](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [vytváření pomocí příkazového řádku csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). V tomto příkladu můžete také vytvořit [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] zadáním nebo vložením kódu do nového projektu.  Viz také [postupy: zkompilování a spuštění dokončení Windows Forms kód příklad pomocí sady Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>  
 [BindingSource – komponenta](../../../../docs/framework/winforms/controls/bindingsource-component.md)