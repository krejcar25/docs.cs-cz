---
title: "Doporučené postupy: Prostředníci"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7aecdcecedcee98828b398f9172985d2e09fb9be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-intermediaries"></a>Doporučené postupy: Prostředníci
Musí dát pozor správně zpracování chyb při volání metody prostředníci a ujistěte se, že jsou služby straně kanály na zprostředkovatele uzavřít správně.  
  
 Vezměte v úvahu následující scénář. Klient zavolá zprostředkovatele, který pak zavolá back endové službě.  Back endové službě definuje žádná chyba – kontrakt, takže jakékoli chyby vyvolaných z dané služby budou považovány za beztypové selhání.  Vrátí back endové služby <xref:System.ApplicationException> a WCF správně zruší kanál straně služby. <xref:System.ApplicationException> Potom zobrazí jako <xref:System.ServiceModel.FaultException> , je vyvolána zprostředkovatelem. Zprostředkovatel znovu vyvolá <xref:System.ApplicationException>. WCF interpretuje jako beztypové chybu z zprostředkovatel a předává ke klientovi. Po přijetí chyby, zprostředkovatel i klienta poruch jejich kanály straně klienta. Zprostředkovatel na straně služby kanál ale zůstane otevřená, protože WCF neví, že je závažné chyby.  
  
 Osvědčeným postupem v tomto scénáři je zjistit, jestli je závažné selhání přicházející ze služby, a pokud zprostředkovatel tak by měl poruch jeho kanál straně služby, jak je znázorněno v následující fragment kódu.  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    Else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Zpracování chyb WCF](../../../docs/framework/wcf/wcf-error-handling.md)  
 [Určování a zpracování chyb v kontraktech a službách](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
