---
title: "Pracovní postup zabezpečení"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dbb1d1efc0758410f12f2c669cca85b9f0e38406
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-security"></a>Pracovní postup zabezpečení
[!INCLUDE[wf](../../../includes/wf-md.md)]je integrován s několika různých technologií, jako je Microsoft SQL Server a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Interakci s těmito technologiemi může znamenat problémy se zabezpečením do vašeho pracovního postupu, pokud se to udělá nesprávně.  
  
## <a name="persistence-security-concerns"></a>Otázky zabezpečení trvalost  
  
1.  Pracovní postupy, které používají <xref:System.Activities.Statements.Delay> aktivity a trvalost potřeba znovu aktivovat pomocí služby. Windows AppFabric používá pracovní postup správy služby (WMS) s vypršenou platností časovače znovu aktivovat pracovních postupů. Vytvoří WMS <xref:System.ServiceModel.WorkflowServiceHost> k hostování opětovně aktivovaných pracovního postupu. Pokud WMS služba je zastavena, trvalé pracovní postupy nebudou znovu aktivovat po vypršení jejich časovače.  
  
2.  Přístup k vytváření instancí trvanlivý by měl chráněná před zlými úmysly externí do domény aplikace. Kromě toho vývojáři měli zkontrolujte, zda škodlivý kód nemůže být ve stejné doméně jako kód trvanlivý zřizování instancí aplikace.  
  
3.  Trvanlivý vytváření instancí nemůže spouštět se zvýšenými oprávněními (správce).  
  
4.  Je třeba chránit data, která zpracovává mimo doménu aplikace.  
  
5.  Aplikace, které vyžadují izolaci zabezpečení by neměly sdílet stejnou instanci abstrakci schématu. Takové aplikace by měl použít poskytovatelé jiné úložiště nebo uložit nakonfigurovaný na použití různých úložiště konkretizací poskytovatelů.  
  
## <a name="sql-server-security-concerns"></a>Aspekty zabezpečení serveru SQL  
  
-   V případě velkého počtu podřízené aktivity, umístění, záložky, rozšíření hostitele nebo obory používají, nebo když se používají záložky s velmi rozsáhlých datových částí, může dojít k vyčerpání paměti nebo zbytečného množství volného místa databáze může být přidělen během trvalost. To může být omezeny pomocí zabezpečení na úrovni objektů a úroveň databáze.  
  
-   Při použití <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, musí být zabezpečená úložiště instance. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Osvědčené postupy pro SQL Server](http://go.microsoft.com/fwlink/?LinkId=164972).  
  
-   Citlivá data v úložišti instance by měla šifrovat. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Šifrování zabezpečení SQL](http://go.microsoft.com/fwlink/?LinkId=164976).  
  
-   Vzhledem k tomu, že připojovací řetězec databáze je často zahrnutý v konfiguračním souboru, windows řízení přístupu (ACL) by měla sloužit k zkontrolujte, zda je konfigurační soubor (obvykle Web.Config) zabezpečené a informace přihlašovací jméno a heslo nejsou součástí připojovací řetězec. Ověřování systému Windows by měla místo toho použít mezi databází a webový server.  
  
## <a name="considerations-for-workflowservicehost"></a>Důležité informace týkající se hostitele služby pracovního postupu  
  
-   [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]musí být zabezpečená koncových bodů použitých v pracovních postupech. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF – Přehled zabezpečení](http://go.microsoft.com/fwlink/?LinkID=164975).  
  
-   Ověřování na úrovni hostitele můžete implementovat pomocí <xref:System.ServiceModel.ServiceAuthorizationManager>. V tématu [postupy: vytvoření vlastního Správce autorizací pro službu](http://go.microsoft.com/fwlink/?LinkId=192228) podrobnosti. To také ukazují následující ukázka: [zabezpečení služeb pracovních postupů](../../../docs/framework/windows-workflow-foundation/samples/securing-workflow-services.md).  
  
-   ServiceSecurityContext pro příchozí zprávy je také k dispozici v rámci pracovního postupu přístup k informacím OperationContext.  V tématu [přístup k informacím OperationContext ze služby pracovních postupů](../../../docs/framework/wcf/feature-details/accessing-operationcontext-from-a-workflow-service.md) podrobnosti.  
  
## <a name="wf-security-pack-ctp"></a>WF zabezpečení Pack CTP  
 Microsoft WF zabezpečení Pack CTP 1 je první verze preview (CTP) technologie komunity sadu aktivit a jejich provedení na základě [modelu Windows Workflow Foundation](http://msdn.microsoft.com/netframework/aa663328.aspx)v [rozhraní .NET Framework 4](http://msdn.microsoft.com/netframework/default.aspx) (WF (4) a [technologie Windows Identity Foundation (WIF)](http://msdn.microsoft.com/security/aa570351.aspx).  Microsoft WF zabezpečení Pack CTP 1 obsahuje aktivity a jejich návrhářů, které ukazují, jak snadno povolit různé scénáře související se zabezpečením pomocí pracovního postupu, včetně:  
  
1.  Zosobnění identita klienta v pracovním postupu  
  
2.  V pracovním postupu autorizace, jako je například PrincipalPermission a ověřování deklarací identity  
  
3.  Ověřené zasílání zpráv pomocí ClientCredentials určeným v pracovním postupu, jako je například uživatelské jméno a heslo, nebo token načíst z zabezpečení tokenu služby (STS)  
  
4.  Token zabezpečení klienta k službě back-end (delegování založené na deklaracích identity) pomocí protokolu WS-Trust ActAs toku  
  
Další informace a stáhnout Pack CTP WF zabezpečení, najdete v tématu: [WF zabezpečení Pack CTP](http://wf.codeplex.com/releases/view/48114)