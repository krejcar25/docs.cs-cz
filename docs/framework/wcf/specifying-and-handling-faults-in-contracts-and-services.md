---
title: "Určování a zpracování chyb v kontraktech a službách"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: handling faults [WCF]
ms.assetid: a9696563-d404-4905-942d-1e0834c26dea
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57fc01b77379389ca4d86d241ec8f3d672b519b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-and-handling-faults-in-contracts-and-services"></a>Určování a zpracování chyb v kontraktech a službách
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]aplikace zpracování chyby situacích mapování objektů spravovaných výjimek na protokolu SOAP selhání objekty a objekty chybu protokolu SOAP na objekty spravovaných výjimek. Témata v této části popisují postup návrhu kontrakty vystavit chyba podmínek jako vlastní chyb SOAP, jak vracet tyto chyby v rámci implementace služby a jak klienti catch takové chyby.  
  
## <a name="error-handling-overview"></a>Přehled zpracování chyb  
 Ve všech spravovaných aplikací, jsou reprezentovány zpracování chyb <xref:System.Exception> objekty. V aplikacích založených na protokolu SOAP, jako [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aplikace, metody služeb komunikaci pomocí protokolu SOAP zprávy selhání informace o chybě zpracování. Chyb SOAP jsou typy zpráv, které jsou součástí metadat pro operace služby a proto vytvoření kontraktu selhání, který můžou klienti používat, aby jejich operaci více robustní nebo interaktivní. Kromě toho, protože chyb SOAP jsou vyjádřeny klientům ve formátu XML, je vysoce interoperabilní typ systému, který můžou klienti na jakékoli platformě SOAP používat, zvýšení rozsah vaší [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aplikace.  
  
 Protože [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aplikace běh oba typy systémů chyba, veškeré informace spravované výjimky, které se může odeslat klientovi je nutné převést z výjimky do chyb SOAP služby, odeslané a převést z chyb SOAP na selhání výjimky v [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klientů. V případě duplexní klientů můžete klienta kontrakty také odeslat chyb SOAP zpět do služby. V obou případech můžete použít výchozí chování výjimce služby, nebo můžete explicitně řídit zda – a jak – výjimky jsou namapované na chybové zprávy.  
  
 Dva typy chyb SOAP mohou být odesílány: *deklarovaný* a *nedeklarované*. Deklarovaný chyb SOAP jsou ty, ve kterých se operace <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> atribut, který určuje vlastní typ chybu protokolu SOAP. *Nedeklarovaný* chyb SOAP nebyly zadány v kontraktu operace.  
  
 Důrazně doporučujeme, aby operací služby deklarace jejich chyb pomocí <xref:System.ServiceModel.FaultContractAttribute> atribut oficiálně zadat všechny SOAP chyb, které klient můžete očekávat při běžném průběhu operace. Doporučujeme také, že vrátíte v rámci protokolu SOAP pouze informace, které klient musí vědět, chcete-li minimalizovat zpřístupnění informací.  
  
 Obvykle služeb (a duplexní klientů) proveďte následující kroky úspěšně integrovat do svých aplikací pro zpracování chyb:  
  
-   Mapování výjimky na vlastní chyb SOAP.  
  
-   Služby a klienti odesílat a přijímat SOAP chyby jako výjimky.  
  
 Kromě toho [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klientů a služeb můžete použít chyb nedeklarované soap pro účely ladění a můžete rozšířit výchozí chování chyby. Následující části popisují tyto úlohy a koncepty.  
  
## <a name="map-exceptions-to-soap-faults"></a>Mapování výjimky na chyb SOAP  
 Prvním krokem při vytváření operace, která zpracovává chybové stavy je rozhodnout, za jakých podmínek klientskou aplikaci informováni o chybách. Některé operace mít chybové stavy, které jsou specifické pro jejich funkce. Například `PurchaseOrder` operace může vrátit konkrétní informace pro zákazníky, kteří jsou již povolen zahájíte nákupní objednávka. V ostatních případech, jako `Calculator` služby, další Obecné `MathFault` chybu protokolu SOAP, pravděpodobně bude moci popisují všechny chybové stavy v celé služby. Jakmile chybové stavy klientů služby jsou určeny, lze sestavit vlastní chybu protokolu SOAP a operace může být označen jako vrátí tuto chybu protokolu SOAP, když dojde k jeho odpovídající chybový stav.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Tento krok vývoje služby nebo klienta, najdete v části [definiční a určení chyb](../../../docs/framework/wcf/defining-and-specifying-faults.md).  
  
## <a name="clients-and-services-handle-soap-faults-as-exceptions"></a>Služby a klienti zpracování chyb SOAP jako výjimky  
 Identifikace operace chybové stavy, definování vlastních chyb protokolu SOAP a označení tyto operace jako vrácení tyto chyby jsou první kroky v úspěšné zpracování chyb v [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aplikace. Dalším krokem je správně implementovat odesílání a příjem těchto chyb. Obvykle služby posílat chyb, které informují klientské aplikace o chybové stavy ale duplexní klientů můžete také odeslat chyb SOAP služby.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Chyby odesílání a přijímání](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="undeclared-soap-faults-and-debugging"></a>Nedeklarovaný SOAP chyb a ladění  
 Deklarované chyb SOAP jsou velmi užitečné pro vytváření robustní umožňuje vzájemnou spolupráci distribuovaných aplikací. V některých případech je užitečné pro službu (nebo duplexní klienta) k odeslání nedeklarované chybu protokolu SOAP, ten, který není uveden v webové služby WSDL (Description Language) pro tuto operaci. Například při vývoji služby, neočekávané situacích může dojít ve kterých je užitečný při ladění posílat informace zpět do klienta. Kromě toho můžete nastavit <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> vlastnost nebo <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> vlastnost `true` tak, aby povolovala [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klientům získat informace o interní služby operaci výjimky. Odesílání chyb jednotlivých i nastavení ladění chování vlastnosti jsou popsány v [odesílání a přijímání chyb](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
> [!IMPORTANT]
>  Protože spravované výjimky mohou být informace o interní aplikace, nastavení <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> nebo <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> k `true` můžete povolit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klientům získat informace o operaci výjimky interní služby, včetně osobní osobní a dalších citlivých informací.  
>   
>  Proto nastavení <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> nebo <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> k `true` se doporučuje jenom jako způsob, jak dočasně ladění aplikace služby. Kromě toho schématu WSDL pro metodu, která vrátí neošetřené se spravovanými výjimkami tímto způsobem neobsahuje kontrakt <xref:System.ServiceModel.FaultException%601> typu <xref:System.ServiceModel.ExceptionDetail>. Klienti měli očekávat možnost neznámé chybě protokolu SOAP (vrátí [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klientů jako <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> objekty) získat informace o ladění správně.  
  
## <a name="customizing-error-handling-with-ierrorhandler"></a>Přizpůsobení zpracování chyb pomocí IErrorHandler  
 Pokud máte speciální požadavky, které chcete přizpůsobit zprávu odpovědi klientovi, když dojde k výjimce na úrovni aplikace nebo provést některé vlastní zpracování poté, co se vrátí zprávu odpovědi, implementovat <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType> rozhraní.  
  
## <a name="fault-serialization-issues"></a>Selhání serializace problémy  
 Při deserializaci chyba – kontrakt, nejprve pokusí najít název kontraktu chyby v protokolu SOAP zprávy s typem chyby kontraktu WCF. Pokud nemůže najít přesnou shodu, které pak vyhledá seznam v abecedním pořadí pro kompatibilní typ smlouvy k dispozici selhání. Pokud dva poruch kontrakty jsou kompatibilní typy (jeden je podtřídou třídy jiné, například) nesprávný typ lze deserializovat poruchy. Pouze k tomu dojde, pokud chyba – kontrakt neurčuje název, obor názvů a akce. Chcete-li zabránit výskytu tohoto problému, vždy plnému určení selhání kontrakty zadáním jména, obor názvů a atributů akce. Kromě toho pokud jste definovali počet odvozování od třídy sdílené základní kontrakty související chyby, je třeba označit žádné nové členy s `[DataMember(IsRequired=true)]`. Další informace v tomto `IsRequired` najdete atribut <xref:System.Runtime.Serialization.DataMemberAttribute>. To zabrání základní třídu nebudou kompatibilní typ a vynutit selhání rekonstrukce do správné odvozený typ.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.CommunicationException>  
 <xref:System.ServiceModel.FaultContractAttribute.Action%2A>  
 <xref:System.ServiceModel.FaultException.Code%2A>  
 <xref:System.ServiceModel.FaultException.Reason%2A>  
 <xref:System.ServiceModel.FaultCode.SubCode%2A>  
 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>  
 [Definice a určení chyb](../../../docs/framework/wcf/defining-and-specifying-faults.md)
