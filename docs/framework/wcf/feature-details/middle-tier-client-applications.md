---
title: "Klientské aplikace střední vrstvy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13399243994943ddf853447e2e29f3695702aa35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="middle-tier-client-applications"></a>Klientské aplikace střední vrstvy
Toto téma popisuje různé problémy, které jsou specifické pro střední vrstvy klientské aplikace, které používají [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="increasing-middle-tier-client-performance"></a>Zvýšení výkonu klienta střední vrstvy  
 Ve srovnání s předchozí komunikace technologií, jako jsou webové služby pomocí [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], vytvoření [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] instanci klienta může být složitější z důvodu bohaté funkce sadu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Například když <xref:System.ServiceModel.ChannelFactory%601> je otevřen objekt ji může vytvořit zabezpečené relaci se službou, procedury, která se prodlouží doba spuštění pro instanci klienta. Obvykle se tyto další funkce možnosti neovlivní klientské aplikace výrazně od [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta provádí několik volání a poté uzavře.  
  
 Střední vrstvy klientské aplikace, ale můžete vytvořit mnoho [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] objekty klienta rychle a v důsledku toho prostředí vyšší inicializace požadavky. Pro zvýšení výkonu aplikací střední vrstvy při volání služby dvěma způsoby:  
  
-   Mezipaměť [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta objektu a kde je to možné opakovaně ji používat pro následující volání.  
  
-   Vytvoření <xref:System.ServiceModel.ChannelFactory%601> objektu a pak použijte tento objekt pro vytváření nových [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] objekty kanálu klienta pro každé volání.  
  
 Problémy, které je třeba zvážit při použití těchto přístupů patří:  
  
-   Pokud služba je zachování stavu specifické pro klienta pomocí relace, pak nelze znovu použít střední vrstvě [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vzhledem k tomu, že stav služby je vázaný na střední vrstvě klientských o něj požádá klient s více klienta vrstvy.  
  
-   Pokud služba musí provést ověření na základě jednotlivé klienty, musíte vytvořit nového klienta pro každého příchozího požadavku na střední vrstvy, namísto opakovaného použití střední vrstvě [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta (nebo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] objekt kanálu klienta) protože klienta přihlašovací údaje střední vrstvy nelze změnit po [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta (nebo <xref:System.ServiceModel.ChannelFactory%601>) byla vytvořena.  
  
-   Kanály a klienty vytvořené kanály jsou bezpečné pro přístup z více vláken, nemusí podporují zápis více než jeden zprávy k drátové síti současně. Při odesílání zprávy velké, zvlášť pokud streamování, je operaci odeslání mohou blokovat čekání na další odeslat k dokončení. To způsobí, že dva druhy problémů: chybějících souběžnosti a možnost zablokování Pokud toku řízení vrátí ke službě opakovaného použití kanálu (to znamená, sdílené klienta zavolá službu, jejichž výsledky cesta kódu v zpětné volání pro sdílené klienta). To platí bez ohledu na typ [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta můžete znovu použít.  
  
-   Je nutné zajistit chybný kanály bez ohledu na to, jestli sdílet kanál. Když jsou opakovaně kanály, ale můžete chybující kanál vypnout více než jedno čekající žádosti o nebo odeslat.  
  
 Příklad, osvědčené postupy pro opětovné použití klienta pro víc požadavků, naleznete v části [datové vazby v klientovi ASP.NET](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md).  
  
 Kromě toho můžete zvýšit výkon při spuštění pro tyto klienty, kteří používají typy dat, které jsou serializovatelný pomocí <xref:System.Xml.Serialization.XmlSerializer> generování a kompilace kódu serializace pro tyto typy dat za běhu, což může vést k pomalé spuštění výkonu. [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) lze vylepšit výkon spuštění pro tyto aplikace generování kódu nezbytné serializace z kompilované sestavení pro aplikaci. Další informace najdete v tématu [postupy: zlepšení spuštění čas klientských aplikací WCF pomocí třídy XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Viz také  
 [Přístup ke službám pomocí klienta WCF](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
