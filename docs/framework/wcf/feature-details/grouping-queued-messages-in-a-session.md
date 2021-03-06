---
title: "Seskupování zpráv zařazených do fronty v relaci"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aba045456d61b5ad687f1030dca3c26b083cdb58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="grouping-queued-messages-in-a-session"></a>Seskupování zpráv zařazených do fronty v relaci
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]poskytuje relaci, která umožňuje seskupení sady souvisejících zpráv společně pro zpracování jedné přijímající aplikací. Zprávy, které jsou součástí relace musí být součástí stejné transakci. Vzhledem k tomu, že všechny zprávy jsou součástí stejné transakci, pokud se nepodaří jednu zprávu zpracovat celé relace je vrácena zpět. Relace mají podobné chování s ohledem na fronty nedoručených zpráv a poškozených fronty. Čas potřebný k Live (TTL) vlastnost nastavte u vazbu zařazených do fronty, nakonfigurované pro relace je použita v relaci jako celek. Pokud jen některé zprávy v relaci se odesílají než hodnota TTL nevyprší, celé relace je umístěna do fronty nedoručených zpráv. Podobně když zprávy v relaci se nepodařilo odeslat do aplikace z fronty aplikace, celé relace je umístěny v poškozených frontu (Pokud je k dispozici).  
  
## <a name="message-grouping-example"></a>Příklad seskupení zpráv  
 Jedním z příkladů kde seskupování zpráv je užitečné, je při implementaci pořadí zpracování aplikace jako [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] služby. Například klient odešle pořadí do této aplikace, který obsahuje počet položek. Pro každou položku klient zavolá službu, což vede k samostatné zprávy při odesílání. Je možné, používat A přijímat první položka a server B, aby přijímal druhou položku. Pokaždé, když je položka přidána, má server zpracování daná položka k vyhledání příslušné pořadí a přidejte položku, což je velmi neefektivní. Pořád se spustit do takové umožňuje zvýšit efektivitu s pouze jedním serverem zpracování všech požadavků, protože server musí sledovat všechny objednávky právě zpracovávána a určení, která patří novou položku. Seskupování všechny požadavky pro jednoduché řazení výrazně zjednodušuje implementace takové aplikace. Klientská aplikace odešle pro jednoduché řazení všechny položky v relaci, takže Jakmile služba zpracovává pořadí, zpracuje celý relace najednou. \  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a>Nastavit kontraktu služby pro použití relací  
  
1.  Definování kontraktu služby, který vyžaduje relaci. To provést pomocí <xref:System.ServiceModel.OperationContractAttribute> atribut a seznam zadáním:  
  
    ```  
    SessionMode=SessionMode.Required  
    ```  
  
2.  Označte operace v kontraktu jako jednosměrné, protože tyto metody nic nevrátí. To lze provést pomocí <xref:System.ServiceModel.OperationContractAttribute> atribut a seznam zadáním:  
  
    ```  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3.  Implementace kontraktu služby a zadejte `InstanceContextMode` z `PerSession`. To vytvoří služba jenom jednou pro každou relaci.  
  
    ```  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4.  Každé operace služby vyžaduje transakce. Zadejte o <xref:System.ServiceModel.OperationBehaviorAttribute> atribut. Nastavte také operaci, která se dokončí transakci `TransactionAutoComplete` k `true`.  
  
    ```  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]   
    ```  
  
5.  Nakonfigurujte koncový bod, který používá zadaný systému `NetMsmqBinding` vazby.  
  
6.  Vytvoření transakční fronty pomocí <xref:System.Messaging>. Fronty můžete vytvořit také pomocí služby Řízení front zpráv (MSMQ) nebo konzoly MMC. Pokud vytvoříte, transakční fronty.  
  
7.  Vytvořit hostitele služby pro službu pomocí <xref:System.ServiceModel.ServiceHost>.  
  
8.  Otevření hostitele služby chcete zpřístupnit službu.  
  
9. Zavřete hostitele služby.  
  
#### <a name="to-set-up-a-client"></a>Nastavení klienta  
  
1.  Vytvoření oboru transakce k zápisu do transakční fronty.  
  
2.  Vytvořte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta pomocí [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) nástroj.  
  
3.  Místní pořadí.  
  
4.  Zavřít [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta.  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad obsahuje kód pro `IProcessOrder` služby a pro klienta, který tato služba používá. Ukazuje, jak [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] používá relací zajistit chování seskupení zařazených do fronty.  
  
### <a name="code-for-the-service"></a>Kód pro službu  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  
  
  
  
### <a name="code-for-the-client"></a>Kód pro klienta  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  
  
  
  
## <a name="see-also"></a>Viz také  
 [Relace a fronty](../../../../docs/framework/wcf/samples/sessions-and-queues.md)  
 [Přehled front](../../../../docs/framework/wcf/feature-details/queues-overview.md)
