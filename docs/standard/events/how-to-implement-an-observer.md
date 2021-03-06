---
title: 'Postupy: Implementace pozorovatele'
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
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b895739daf1f4844d6300df4788441be67b90254
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-implement-an-observer"></a>Postupy: Implementace pozorovatele
Návrhový vzor pozorovatel vyžaduje rozdělení pozorovatele, které je zaregistruje pro oznámení, a zprostředkovatele, který monitoruje data a odešle oznámení pozorovatelů jeden nebo více. Toto téma popisuje postup vytvoření pozorovatele. Související téma, [postupy: implementace poskytovatele](../../../docs/standard/events/how-to-implement-a-provider.md), popisuje, jak vytvářet poskytovatele.  
  
### <a name="to-create-an-observer"></a>Chcete-li vytvořit pozorovatele  
  
1.  Definování pozorovatel, což je typ, který implementuje <xref:System.IObserver%601?displayProperty=nameWithType> rozhraní. Například následující kód definuje typ s názvem `TemperatureReporter` který je vytvořený <xref:System.IObserver%601?displayProperty=nameWithType> implementace s argumentem obecného typu ve `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  Pokud pozorovatel zastavit příjem oznámení před volání zprostředkovatele jeho <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementace definovat soukromé proměnné, která bude obsahovat <xref:System.IDisposable> implementace vrácený poskytovatele <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> metoda. Měli byste také definovat předplatné metodu, která volá metody poskytovatele <xref:System.IObservable%601.Subscribe%2A> metoda a úložišť vrácený <xref:System.IDisposable> objektu. Například následující kód definuje soukromé proměnné s názvem `unsubscriber` a definuje `Subscribe` metoda, která volá metody poskytovatele <xref:System.IObservable%601.Subscribe%2A> metoda a přiřadí vrácený objekt, který má `unsubscriber` proměnné.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  Zadejte metodu, která umožňuje pozorovatel zastavit přijímání oznámení před volání zprostředkovatele jeho <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementace, pokud je tato funkce se vyžaduje. V následujícím příkladu definuje `Unsubscribe` metoda.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  Poskytovat implementace tři metody definované <xref:System.IObserver%601> rozhraní: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, a <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. V závislosti na zprostředkovateli a potřebám aplikace <xref:System.IObserver%601.OnError%2A> a <xref:System.IObserver%601.OnCompleted%2A> metody může být implementace se zakázaným inzerováním. Všimněte si, že <xref:System.IObserver%601.OnError%2A> metoda by nemělo vyřizovat předaný <xref:System.Exception> objektu jako výjimka a <xref:System.IObserver%601.OnCompleted%2A> metoda je bezplatná volání poskytovatele <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementace. Následující příklad ukazuje <xref:System.IObserver%601> implementace `TemperatureReporter` třídy.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a>Příklad  
 Následující příklad obsahuje kompletní zdrojový kód `TemperatureReporter` třídy, která poskytuje <xref:System.IObserver%601> implementace teplotě monitorování aplikace.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.IObserver%601>  
 [Návrhový vzor Pozorovatel](../../../docs/standard/events/observer-design-pattern.md)  
 [Postupy: Implementace poskytovatele](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [Doporučené postupy pro návrhový vzor Pozorovatel](../../../docs/standard/events/observer-design-pattern-best-practices.md)
