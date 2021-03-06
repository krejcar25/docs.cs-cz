---
title: "Postupy: Generování sestavení vzájemné spolupráce z knihoven typů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b8aa6bcd8817b1f432de5d54f596136f4b01bc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a>Postupy: Generování sestavení vzájemné spolupráce z knihoven typů
[Importér knihovny typů (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) je nástroj příkazového řádku, který převádí třídy typu coclass a rozhraní, které jsou součástí modelu COM knihovny typů pro metadata. Tento nástroj automaticky vytvoří sestavení vzájemné spolupráce a obor názvů pro informace o typu. Po metadata třídy je k dispozici, spravovaných klientů můžete vytvořit instance typu COM a volat její metody stejně, jako by šlo instance rozhraní .NET. Tlbimp.exe převede celý typ knihovny na metadata najednou a nelze generovat informace o typu pro podmnožinu typy definované v knihovny typů.  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a>Ke generování sestavení vzájemné spolupráce z knihovny typů  
  
1.  Použijte následující příkaz:  
  
     **Tlbimp** \< *soubor knihovny typů*>  
  
     Přidávání **/out:** přepínač vytváří sestavení spolupráce s změnit název, jako je například LOANLib.dll. Změna názvu sestavení vzájemné spolupráce může pomoci ho odlišuje od původního DLL COM a zabránit problémům, které se můžou vyskytnout s duplicitními názvy.  
  
## <a name="example"></a>Příklad  
 Následující příkaz vytvoří Loanlib.dll sestavení v `Loanlib` oboru názvů.  
  
```  
tlbimp Loanlib.dll  
```  
  
 Následující příkaz vytvoří spolupráce sestavení s názvem změněna (LOANLib.dll).  
  
```  
tlbimp LoanLib.dll /out: LOANLib.dll  
```  
  
## <a name="see-also"></a>Viz také  
 [Import knihovny typů ve formě sestavení](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [Vystavení komponent COM pro rozhraní .NET Framework](../../../docs/framework/interop/exposing-com-components.md)
