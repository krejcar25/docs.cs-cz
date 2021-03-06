---
title: "Postupy: Rozlišení mezi kliknutím a poklikáním"
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
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4da472b4a2cb2001953758acb0f28da77f08ac70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks"></a>Postupy: Rozlišení mezi kliknutím a poklikáním
Obvykle jedné *klikněte na tlačítko* zahájí akci uživatele rozhraní (UI) a *dvakrát klikněte na* rozšiřuje akce. Například jedním kliknutím obvykle vybere položku a poklepání upravuje vybranou položku. Windows Forms události kliknutí není pojmout snadno scénář, kde kliknutí a dvojitým kliknutím udělejte nekompatibilní, protože akce vázáno <xref:System.Windows.Forms.Control.Click> nebo <xref:System.Windows.Forms.Control.MouseClick> událostí se provádí před akci vázáno <xref:System.Windows.Forms.Control.DoubleClick>nebo <xref:System.Windows.Forms.Control.MouseDoubleClick> událostí. Toto téma popisuje dvě řešení tohoto problému. Jedno řešení je zpracování události poklikejte na soubor a vrácení akce při zpracování události, klikněte na tlačítko. Ve výjimečných případech budete muset simulovat kliknutím a dvakrát klikněte na chování ve zpracování <xref:System.Windows.Forms.Control.MouseDown> událostí a pomocí <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> a <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> vlastnosti <xref:System.Windows.Forms.SystemInformation> – třída. Měření čas mezi kliknutí a druhý klikněte na tlačítko nastane před hodnotu <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> je dosaženo a kliknutím na možnost se v obdélníku definované <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, proveďte akci, poklikejte na soubor; jinak, proveďte akci, klikněte na tlačítko.  
  
### <a name="to-roll-back-a-click-action"></a>Vrácení akce klikněte na  
  
-   Zkontrolujte, zda pracujete s ovládacího prvku standard klikněte dvakrát na chování. Pokud ne, povolte pomocí ovládacího prvku <xref:System.Windows.Forms.Control.SetStyle%2A> metoda. Zpracovat událost poklikejte na soubor a vrátit zpět, klikněte na akci, jakož i akce poklikejte na soubor. Následující příklad kódu ukazuje, jak vytvořit vlastní tlačítko s dvojitým kliknutím povolena, a také pro návrat akce klikněte na tlačítko v kód pro zpracování události poklikejte na soubor.  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### <a name="to-distinguish-between-clicks-in-the-mousedown-event"></a>K rozlišení mezi kliknutím v MouseDown – událost  
  
-   Zpracování <xref:System.Windows.Forms.Control.MouseDown> událostí a určete umístění a čas span mezi kliknutím odpovídající pomocí <xref:System.Windows.Forms.SystemInformation> vlastnosti a <xref:System.Windows.Forms.Timer> součásti. Proveďte příslušné akce v závislosti na tom, jestli klikněte na tlačítko nebo poklikejte na soubor probíhá. Následující příklad kódu ukazuje, jak to lze provést.  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tyto příklady vyžadují:  
  
-   Odkazy na systém, System.Drawing a System.Windows.Forms sestavení.  
  
 Informace o vytváření těchto příkladech z příkazového řádku pro [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] nebo [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], najdete v části [sestavení z příkazového řádku](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [vytváření pomocí příkazového řádku csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Můžete také vytvořit tyto příklady [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] zadáním nebo vložením kód do nové projekty.  Viz také [postupy: zkompilování a spuštění dokončení Windows Forms kód příklad pomocí sady Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Viz také  
 [Vstup z myši v aplikaci Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
