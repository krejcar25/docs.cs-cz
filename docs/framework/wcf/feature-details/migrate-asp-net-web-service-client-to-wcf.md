---
title: "Postupy: Migrace kódu klienta webové služby ASP.NET do služby Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baf43f2bfa2175062c57f73e45835c251ac5769e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>Postupy: Migrace kódu klienta webové služby ASP.NET do služby Windows Communication Foundation
Následující postup popisuje obecné kroky, které je třeba dodržet do migrace kódu klienta webové služby ASP.NET do [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="procedure"></a>Postup  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>Do migrace kódu klienta webové služby ASP.NET do WCF  
  
1.  Ujistěte se, že o komplexní sadu testů pro klienta neexistují.  
  
2.  Pomocí sady Visual Studio 2005 můžete upgradovat klienta aplikace rozhraní .NET 2.0. Spusťte sadu testů.  
  
3.  Odebrání klientského projektu ASP.NET kód klienta. Tento kód se generuje pomocí nástroje WSDL.exe moduly.  
  
4.  Generovat [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta kódu pomocí [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Přidání tohoto kódu do projektu klienta a sloučit výstup konfigurace do klienta existující konfigurační soubor.  
  
5.  Kompilace aplikace. Oprava chyb kompilace nahrazením odkazy na bývalé typů klientů ASP.NET s odkazy na nové [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] typů klientů.  
  
6.  Spusťte sadu testů.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Migrace kódu webové služby ASP.NET na Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
