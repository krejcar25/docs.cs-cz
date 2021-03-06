---
title: "Zámky modulů pro čtení a zápis"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d005442ee74b46a0ecb1eaafe214e7190330cfe7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="reader-writer-locks"></a>Zámky modulů pro čtení a zápis
<xref:System.Threading.ReaderWriterLockSlim> Třída umožňuje více vláken současně číst prostředek, ale vyžaduje vlákna počkat, aby bylo možné zapsat do prostředku výhradní zámek.  
  
 Můžete použít <xref:System.Threading.ReaderWriterLockSlim> ve vaší aplikaci zajistit spolupráci synchronizace mezi vláken, která přístup ke sdíleným prostředkům. Zámky jsou přesměrováni <xref:System.Threading.ReaderWriterLockSlim> sám sebe.  
  
 Jako s mechanismus synchronizace přístup z více vláken, je nutné zajistit, že nejsou žádná vlákna nepoužívat zamykání, které poskytuje <xref:System.Threading.ReaderWriterLockSlim>. Jeden způsob, jak zajistit toto je návrh třídy, který zapouzdřuje sdílený prostředek. Tato třída by poskytují členy, přístup k privátním sdílený prostředek a které používají soukromé <xref:System.Threading.ReaderWriterLockSlim> pro synchronizaci. Příklad, podívejte se na příklad kódu pro <xref:System.Threading.ReaderWriterLockSlim> třídy. <xref:System.Threading.ReaderWriterLockSlim>je dostatečně efektivní, který se má použít k synchronizaci jednotlivých objektů.  
  
 Struktury aplikace minimalizovat dobu trvání pro čtení a zápisu operace. Operace zápisu dlouho ovlivnit propustnost přímo, protože je určena výhradně uzamčení pro zápis. Dlouho čtení operations bloku čekání zapisovače a pokud alespoň jedno vlákno čeká přístup pro zápis, vláken, které požadují přístup pro čtení se zablokuje také.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Má dva zámků čtení a zápis, <xref:System.Threading.ReaderWriterLockSlim> a <xref:System.Threading.ReaderWriterLock>. <xref:System.Threading.ReaderWriterLockSlim>doporučuje se pro všechny nové vývoj. <xref:System.Threading.ReaderWriterLockSlim>je podobná <xref:System.Threading.ReaderWriterLock>, ale zjednodušila pravidla pro rekurze a pro upgrade a přechod na starší verzi Stav zámku. <xref:System.Threading.ReaderWriterLockSlim>zabraňuje mnoha případech potenciální zablokování. Kromě toho výkon <xref:System.Threading.ReaderWriterLockSlim> je výrazně lepší, než <xref:System.Threading.ReaderWriterLock>.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [Dělení na vlákna](../../../docs/standard/threading/index.md)  
 [Funkce a objekty dělení na vlákna](../../../docs/standard/threading/threading-objects-and-features.md)
