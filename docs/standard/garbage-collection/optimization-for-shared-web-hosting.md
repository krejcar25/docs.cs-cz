---
title: "Optimalizace pro sdílené hostování webů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7525ca263449da77b4b6364fd6bcfd51dcba145d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="optimization-for-shared-web-hosting"></a>Optimalizace pro sdílené hostování webů
Pokud jste správce pro server, který je sdílen hostování několik malých webových serverů, můžete optimalizovat výkon a zvýšit kapacitu lokality přidáním následující `gcTrimCommitOnLowMemory` nastavení na `runtime` uzlu v souboru Aspnet.config v rozhraní .NET adresář:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  Toto nastavení se doporučuje jenom pro sdílené webové hostování scénáře.  
  
 Vzhledem k tomu, že zachová má systém uvolňování paměti pro budoucí přidělení, lze jeho potvrdit místo více než je nezbytně nutné. Tento prostor, aby pojmulo doby můžete snížit při velkém zatížení na systémové paměti. Zmenšení potvrdit vylepšuje výkon a rozbalí kapacitu pro hostování více webů.  
  
 Když `gcTrimCommitOnLowMemory` je povolené nastavení, vyhodnotí zatížení paměti systému uvolňování paměti a vstupuje do režimu oříznutí, pokud zatížení dosáhne 90 %. Dokud zatížení klesne pod položkou 85 % udržuje režimu oříznutí.  
  
 Když podmínky povolit, bude systém uvolňování můžete rozhodnout, že `gcTrimCommitOnLowMemory` nastavení nebude pomůže aktuální aplikace a ho ignorovat.  
  
## <a name="example"></a>Příklad  
 Následující fragment kódu XML ukazuje, jak povolit `gcTrimCommitOnLowMemory` nastavení. Tři tečky znamenat další nastavení, které by se v `runtime` uzlu.  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také  
 [Uvolňování paměti](../../../docs/standard/garbage-collection/index.md)
