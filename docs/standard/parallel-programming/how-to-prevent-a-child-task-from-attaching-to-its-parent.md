---
title: "Postupy: Zabránění připojení podřízené úlohy ke své nadřazené úloze"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2cab2fb9c26a8ddaa868cafebac718e5dfd6baa0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>Postupy: Zabránění připojení podřízené úlohy ke své nadřazené úloze
Tento dokument ukazuje, jak zabránit v připojení k nadřazené úlohy podřízené úlohy. Brání připojení k nadřazené podřízené úlohy je užitečné, když zavoláte komponentu, která jsou zapsána třetích stran a také používající úlohy. Například komponenty třetích stran, která používá <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> možnost vytvořit <xref:System.Threading.Tasks.Task> nebo <xref:System.Threading.Tasks.Task%601> objekt může způsobit problémy ve vašem kódu, pokud je dlouhotrvající nebo k neošetřené výjimce.  
  
## <a name="example"></a>Příklad  
 Následující příklad porovnává důsledky použití výchozích možností pro důsledky z znemožňuje připojení k nadřazené podřízené úlohy. V příkladu se vytváří <xref:System.Threading.Tasks.Task> objekt, který volá do knihovny třetí strany, který také používá <xref:System.Threading.Tasks.Task> objektu. Knihovna třetích stran používá <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> možnost vytvořit <xref:System.Threading.Tasks.Task> objektu. Aplikace používá <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> možnost vytvořit úlohu nadřazené. Tato možnost dá pokyn modulu runtime odebrat <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> specifikace v podřízené úlohy.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Protože nadřazené úkolů nedokončí, dokud nedokončí všechny podřízené úlohy, dlouhodobé podřízené úlohy může způsobit celkové aplikace provést špatně. V tomto příkladu Pokud aplikace používá výchozí možnosti pro vytvoření nadřazené úlohy, podřízené úlohy musí dokončit před nadřazený úkol dokončí. Pokud aplikace používá <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> možnost, podřízený objekt není připojen k nadřazené. Proto aplikace provádět další kroky po dokončení této úlohy nadřazené a předtím, než se musí počkat na dokončení úlohy podřízené.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Příklad kódu zkopírujte a vložte ji do projektu sady Visual Studio nebo ho vložte v souboru, který je pojmenován `DenyChildAttach.cs` (`DenyChildAttach.vb` pro [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), a poté spusťte následující příkaz v okně příkazového řádku Visual Studia.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe DenyChildAttach.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **Vbc.exe DenyChildAttach.vb**  
  
## <a name="robust-programming"></a>Robustní programování  
  
## <a name="see-also"></a>Viz také  
 [Asynchronní programování založené na úlohách](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
