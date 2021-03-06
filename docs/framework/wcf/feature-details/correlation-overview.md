---
title: "Korelace – přehled"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edcc0315-5d26-44d6-a36d-ea554c418e9f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a29f761b4a3718293c1786d23d425265603f8c84
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="correlation-overview"></a>Korelace – přehled
Korelace je mechanismus pro související zprávy služby pracovního postupu k sobě navzájem nebo stav instance aplikace, jako je například odpovědět na požadavek počáteční nebo konkrétní pořadí ID trvalého stavu pracovním postupu pořadí zpracování. Toto téma obsahuje přehled korelace. Na další témata v této části poskytují další informace pro každý typ korelace.  
  
## <a name="types-of-correlation"></a>Typy korelace  
 Korelace může být založené na protokolu nebo na základě obsahu. Založené na protokolu korelací mapování mezi zprávy používá data poskytnutá infrastruktura doručení zprávy. Zprávy, které jsou korelační pomocí korelace založené na protokolu jsou ve vzájemném pomocí objektu v paměti, jako třeba <xref:System.ServiceModel.Channels.RequestContext>, nebo token poskytovaný přenosový protokol. Na základě obsahu korelací související zprávy navzájem pomocí dat určený aplikací. Zprávy, které jsou korelační pomocí korelace na základě obsahu se vztahují k sobě navzájem některá data definované aplikací ve zprávě, jako je například číslo zákazníka.  
  
 Aktivity, které jsou součástí korelace použití <xref:System.ServiceModel.Activities.CorrelationHandle> ke svázání zasílání zpráv aktivity společně. Například <xref:System.ServiceModel.Activities.Send> používané při volání služby a následné <xref:System.ServiceModel.Activities.Receive> sloužící k nebude zpětné volání ze služby, sdílet stejný <xref:System.ServiceModel.Activities.CorrelationHandle>. Tento základní vzor se používá, zda korelaci je obsah na základě nebo na základě protokolu. Popisovač korelace může být explicitně nastaveny na každou aktivitu nebo může být součástí aktivity <xref:System.ServiceModel.Activities.CorrelationScope> aktivity. Aktivity obsažené v <xref:System.ServiceModel.Activities.CorrelationScope> jejich korelace popisovači spravuje <xref:System.ServiceModel.Activities.CorrelationScope> a nevyžadují <xref:System.ServiceModel.Activities.CorrelationHandle> být explicitně nastavena. A <xref:System.ServiceModel.Activities.CorrelationScope> obor představuje <xref:System.ServiceModel.Activities.CorrelationHandle> správy pro korelace požadavku a odpovědi a jeden typ další korelace. Služby pracovních postupů, které jsou hostované pomocí <xref:System.ServiceModel.Activities.WorkflowServiceHost> mají stejné správu korelace výchozí jako <xref:System.ServiceModel.Activities.CorrelationScope> aktivity. Tato výchozí korelace správu obvykle znamená, že v mnoha scénářích aktivity v zasílání zpráv <xref:System.ServiceModel.Activities.CorrelationScope> nebo služby pracovního postupu nevyžadují, aby jejich <xref:System.ServiceModel.Activities.CorrelationHandle> nastavit, pokud jsou více aktivit zasílání zpráv v paralelní nebo překrývají, jako je například dva <xref:System.ServiceModel.Activities.Receive> aktivity paralelní nebo dva <xref:System.ServiceModel.Activities.Send> aktivity následované dvěma <xref:System.ServiceModel.Activities.Receive> aktivity. Další informace o výchozí korelace najdete v tématech v této části, které se týkají každý konkrétní typ korelace. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]aktivity zasílání zpráv najdete v části [zasílání zpráv aktivity](../../../../docs/framework/wcf/feature-details/messaging-activities.md) a [postupy: vytvoření služby pracovního postupu s aktivitami zasílání zpráv](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md).  
  
## <a name="protocol-based-correlation"></a>Založené na protokolu korelace  
 Založené na protokolu korelace používá přenosový mechanismus k související zprávy do sebe navzájem a příslušné instanci. Některé poskytované systémem protokol korelací zahrnují korelace požadavku a odpovědi a korelace na základě kontextu. Korelace požadavku a odpovědi slouží ke sladění jeden pár zasílání zpráv aktivit a vytvoří obousměrný operace, například <xref:System.ServiceModel.Activities.Send> spárované s <xref:System.ServiceModel.Activities.ReceiveReply>, nebo <xref:System.ServiceModel.Activities.Receive> spárované s <xref:System.ServiceModel.Activities.SendReply>. [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Návrhář postupu provádění také poskytuje sadu šablony aktivit k rychlé implementaci tohoto vzoru. Korelace základě kontextu je založené na mechanismu exchange kontext, který je popsané v [Exchange kontextu .NET – specifikace protokolu](http://go.microsoft.com/fwlink/?LinkID=166059). Použít na základě kontextu korelace základě kontextu vazby, jako <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> nebo <xref:System.ServiceModel.NetTcpContextBinding> na koncový bod se musí použít.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]protokol korelace najdete v tématu [kontextová výměna](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md), [trvanlivý duplexní](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md), a [požadavku a odpovědi](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]pomocí [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] šablony aktivit v Návrháři pracovních postupů, najdete v části [zasílání zpráv aktivity](../../../../docs/framework/wcf/feature-details/messaging-activities.md). Ukázkový kód, najdete [trvanlivý duplexní &#91; Ukázky WF &#93; ](../../../../docs/framework/windows-workflow-foundation/samples/durable-duplex.md) a [NetContextExchangeCorrelation](http://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) ukázky.  
  
## <a name="content-based-correlation"></a>Korelace na základě obsahu  
 Korelace na základě obsahu používá některá část informace ve zprávě k její přidružení ke konkrétní instanci. Na rozdíl od založené na protokolu korelace na základě obsahu korelace vyžaduje vytváření aplikací do explicitně stavu, kde tato data lze nalézt v každé související zprávy. Aktivity, které používají korelace na základě obsahu zadat tato zpráva data pomocí <xref:System.ServiceModel.MessageQuerySet>. Korelace na základě obsahu je užitečné při komunikaci s služby, které nepoužívají jeden z kontextu vazby, jako <xref:System.ServiceModel.BasicHttpContextBinding>. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]korelace na základě obsahu najdete v části [na základě obsahu](../../../../docs/framework/wcf/feature-details/content-based-correlation.md). Ukázkový kód, najdete [korelace na základě obsahu](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md) a [korelační kalkulačky](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md) ukázky.  
  
## <a name="see-also"></a>Viz také  
 [Korelace na základě obsahu](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [Korelovaná kalkulačka](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)  
 [Durable Duplex &#91;WF Samples&#93;](../../../../docs/framework/windows-workflow-foundation/samples/durable-duplex.md)  
 [NetContextExchangeCorrelation](http://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf)
