---
title: "Doporučené postupy pro komunikaci ve frontě"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queues [WCF], best practices
- best practices [WCF], queued communication
ms.assetid: 446a6383-cae3-4338-b193-a33c14a49948
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: db0506f6fbbda7758d4cbfc3624d68277a301268
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="best-practices-for-queued-communication"></a><span data-ttu-id="f5729-102">Doporučené postupy pro komunikaci ve frontě</span><span class="sxs-lookup"><span data-stu-id="f5729-102">Best Practices for Queued Communication</span></span>
<span data-ttu-id="f5729-103">Toto téma obsahuje doporučené postupy pro komunikaci ve frontě v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5729-103">This topic provides recommended practices for queued communication in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="f5729-104">Následující části popisují doporučené postupy z hlediska scénář.</span><span class="sxs-lookup"><span data-stu-id="f5729-104">The following sections discuss recommended practices from a scenario perspective.</span></span>  
  
## <a name="fast-best-effort-queued-messaging"></a><span data-ttu-id="f5729-105">Rychlé a Best Effort zařazených do fronty zasílání zpráv</span><span class="sxs-lookup"><span data-stu-id="f5729-105">Fast, Best-Effort Queued Messaging</span></span>  
 <span data-ttu-id="f5729-106">Pro scénáře, které vyžadují poskytuje oddělení, který zařazených do fronty zasílání zpráv a fast, vysoce výkonné zasílání zpráv s best effort záruky netransakční frontu použít a nastavte <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> vlastnost `false`.</span><span class="sxs-lookup"><span data-stu-id="f5729-106">For scenarios that require separation that queued messaging provides and fast, high-performance messaging with best-effort assurances, use a non-transactional queue and set the <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> property to `false`.</span></span>  
  
 <span data-ttu-id="f5729-107">Kromě toho můžete není zabývat náklady zápisy na disk nastavením <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> vlastnost `false`.</span><span class="sxs-lookup"><span data-stu-id="f5729-107">In addition, you can choose not to incur the cost of disk writes by setting the <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> property to `false`.</span></span>  
  
 <span data-ttu-id="f5729-108">Zabezpečení má dopad na výkon.</span><span class="sxs-lookup"><span data-stu-id="f5729-108">Security has implications on performance.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f5729-109">[Faktory ovlivňující výkon](../../../../docs/framework/wcf/feature-details/performance-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="f5729-109"> [Performance Considerations](../../../../docs/framework/wcf/feature-details/performance-considerations.md).</span></span>  
  
## <a name="reliable-end-to-end-queued-messaging"></a><span data-ttu-id="f5729-110">Spolehlivé začátku do konce zasílání zpráv zařazených do fronty.</span><span class="sxs-lookup"><span data-stu-id="f5729-110">Reliable End-to-End Queued Messaging</span></span>  
 <span data-ttu-id="f5729-111">Následující části popisují doporučené postupy pro scénáře, které vyžadují začátku do konce spolehlivé zasílání zpráv.</span><span class="sxs-lookup"><span data-stu-id="f5729-111">The following sections describe recommended practices for scenarios that require end-to-end reliable messaging.</span></span>  
  
### <a name="basic-reliable-transfer"></a><span data-ttu-id="f5729-112">Základní spolehlivé přenosu</span><span class="sxs-lookup"><span data-stu-id="f5729-112">Basic Reliable Transfer</span></span>  
 <span data-ttu-id="f5729-113">Spolehlivost začátku do konce, nastavte <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> vlastnost `true` k zajištění přenosu.</span><span class="sxs-lookup"><span data-stu-id="f5729-113">For end-to-end reliability, set the <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> property to `true` to ensure transfer.</span></span> <span data-ttu-id="f5729-114"><xref:System.ServiceModel.MsmqBindingBase.Durable%2A> Může být nastavena `true` nebo `false` v závislosti na požadavcích (výchozí hodnota je `true`).</span><span class="sxs-lookup"><span data-stu-id="f5729-114">The <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> property can be set to `true` or `false` depending on your requirements (the default is `true`).</span></span> <span data-ttu-id="f5729-115">Obecně platí <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> je nastavena na `true` jako součást spolehlivost začátku do konce.</span><span class="sxs-lookup"><span data-stu-id="f5729-115">Generally, the <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> property is set to `true` as part of end-to-end reliability.</span></span> <span data-ttu-id="f5729-116">Ohrožení snížení výkonu, ale provádí zpráva trvanlivý tak, aby zpráva není ztraceny, pokud dojde k chybě správce front.</span><span class="sxs-lookup"><span data-stu-id="f5729-116">The compromise is a performance cost, but makes the message durable so that the message is not lost if a queue manager crashes.</span></span>  
  
### <a name="use-of-transactions"></a><span data-ttu-id="f5729-117">Použití transakcí</span><span class="sxs-lookup"><span data-stu-id="f5729-117">Use of Transactions</span></span>  
 <span data-ttu-id="f5729-118">Transakce je nutné použít zajistit spolehlivost začátku do konce.</span><span class="sxs-lookup"><span data-stu-id="f5729-118">You must use transactions to ensure end-to-end reliability.</span></span> <span data-ttu-id="f5729-119">`ExactlyOnce`záruky pouze zkontrolujte doručování zpráv do cílové fronty.</span><span class="sxs-lookup"><span data-stu-id="f5729-119">`ExactlyOnce` assurances only ensure that messages are delivered to the target queue.</span></span> <span data-ttu-id="f5729-120">K zajištění, že se zobrazila zpráva, použijte transakce.</span><span class="sxs-lookup"><span data-stu-id="f5729-120">To ensure that the message is received, use transactions.</span></span> <span data-ttu-id="f5729-121">Bez transakcí Pokud dojde k chybě služby, přijdete o zprávu, která je doručování, ale ve skutečnosti doručí se do aplikace.</span><span class="sxs-lookup"><span data-stu-id="f5729-121">Without transactions, if the service crashes, you lose the message that is being delivered but is actually delivered to the application.</span></span>  
  
### <a name="use-of-dead-letter-queues"></a><span data-ttu-id="f5729-122">Použití fronty nedoručených zpráv</span><span class="sxs-lookup"><span data-stu-id="f5729-122">Use of Dead-letter Queues</span></span>  
 <span data-ttu-id="f5729-123">Fronty nedoručených zpráv Ujistěte se, že jsou upozorněni, pokud zpráva se nepodaří doručit do cílové fronty.</span><span class="sxs-lookup"><span data-stu-id="f5729-123">Dead-letter queues ensure that you are notified if a message fails to be delivered to the target queue.</span></span> <span data-ttu-id="f5729-124">Můžete použít frontu nedoručených zpráv poskytované systémem nebo vlastní frontu nedoručených zpráv.</span><span class="sxs-lookup"><span data-stu-id="f5729-124">You can use the system-provided dead-letter queue or a custom dead-letter queue.</span></span> <span data-ttu-id="f5729-125">Obecně platí pomocí vlastní frontu nedoručených zpráv je osvědčených vzhledem k tomu, že umožňuje odesílání zpráv nedoručených zpráv z jedné aplikace do jediné fronty nedoručených zpráv.</span><span class="sxs-lookup"><span data-stu-id="f5729-125">In general, using a custom dead-letter queue is best because it enables you to send dead-letter messages from one application into a single dead-letter queue.</span></span> <span data-ttu-id="f5729-126">Všechny zprávy nedoručených zpráv, ke kterým dochází pro všechny aplikace spuštěné v systému, jinak hodnota doručovány do jedné frontě.</span><span class="sxs-lookup"><span data-stu-id="f5729-126">Otherwise, all dead-letter messages that occur for all applications running on the system are delivered to a single queue.</span></span> <span data-ttu-id="f5729-127">Každá aplikace musí ale vyhledávat frontu nedoručených zpráv najít nedoručených zpráv, které jsou relevantní pro tuto aplikaci.</span><span class="sxs-lookup"><span data-stu-id="f5729-127">Each application must then search though the dead-letter queue to find the dead-letter messages that are relevant to that application.</span></span> <span data-ttu-id="f5729-128">V některých případech pomocí vlastní frontu nedoručených zpráv není možné, například při použití služby MSMQ 3.0.</span><span class="sxs-lookup"><span data-stu-id="f5729-128">Sometimes, using a custom dead-letter queue is not feasible, such as when using MSMQ 3.0.</span></span>  
  
 <span data-ttu-id="f5729-129">Vypnutí fronty nedoručených zpráv pro komunikaci spolehlivé začátku do konce se nedoporučuje.</span><span class="sxs-lookup"><span data-stu-id="f5729-129">Turning off dead-letter queues for end-to-end reliable communication is not recommended.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f5729-130">[Chyb přenosu pomocí fronty nedoručených zpráv pro zpracování zprávy](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span><span class="sxs-lookup"><span data-stu-id="f5729-130"> [Using Dead-Letter Queues to Handle Message Transfer Failures](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
### <a name="use-of-poison-message-handling"></a><span data-ttu-id="f5729-131">Použití zpracování Poison zpráv</span><span class="sxs-lookup"><span data-stu-id="f5729-131">Use of Poison-Message Handling</span></span>  
 <span data-ttu-id="f5729-132">Zpracování zpráv Poison poskytuje možnost obnovení po selhání zpracování zpráv.</span><span class="sxs-lookup"><span data-stu-id="f5729-132">Poison-message handling provides the ability to recover from the failure to process messages.</span></span>  
  
 <span data-ttu-id="f5729-133">Když používáte funkci zpracování zpráv poison, ujistěte se, že <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> je nastavena na odpovídající hodnotu.</span><span class="sxs-lookup"><span data-stu-id="f5729-133">When using the poison-message handling feature, ensure that the <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> property is set to the appropriate value.</span></span> <span data-ttu-id="f5729-134">Jeho nastavení na hodnotu <xref:System.ServiceModel.ReceiveErrorHandling.Drop> znamená data budou ztracena.</span><span class="sxs-lookup"><span data-stu-id="f5729-134">Setting it to <xref:System.ServiceModel.ReceiveErrorHandling.Drop> means the data is lost.</span></span> <span data-ttu-id="f5729-135">Na druhé straně jeho nastavení na hodnotu <xref:System.ServiceModel.ReceiveErrorHandling.Fault> závady hostitele služby, když zjistí poškozená zpráva.</span><span class="sxs-lookup"><span data-stu-id="f5729-135">On the other hand, setting it to <xref:System.ServiceModel.ReceiveErrorHandling.Fault> faults the service host when it detects a poison message.</span></span> <span data-ttu-id="f5729-136">Pomocí služby MSMQ 3.0 <xref:System.ServiceModel.ReceiveErrorHandling.Fault> je nejlepší možnost nedošlo ke ztrátě dat a přesuňte nezpracovatelná zpráva stranou.</span><span class="sxs-lookup"><span data-stu-id="f5729-136">Using MSMQ 3.0, <xref:System.ServiceModel.ReceiveErrorHandling.Fault> is the best option to avoid data loss and move the poison message out of the way.</span></span> <span data-ttu-id="f5729-137">Pomocí služby MSMQ 4.0 <xref:System.ServiceModel.ReceiveErrorHandling.Move> se o doporučený postup.</span><span class="sxs-lookup"><span data-stu-id="f5729-137">Using MSMQ 4.0, <xref:System.ServiceModel.ReceiveErrorHandling.Move> is the recommended approach.</span></span> <span data-ttu-id="f5729-138"><xref:System.ServiceModel.ReceiveErrorHandling.Move>Přesune poškozená po zprávu z fronty, tak, aby služba můžou dál zpracovávat nové zprávy.</span><span class="sxs-lookup"><span data-stu-id="f5729-138"><xref:System.ServiceModel.ReceiveErrorHandling.Move> moves a poisoned message out of the queue so the service can continue to process new messages.</span></span> <span data-ttu-id="f5729-139">Služba poison zpráva může pak zpracovat nezpracovatelná zpráva samostatně.</span><span class="sxs-lookup"><span data-stu-id="f5729-139">The poison-message service can then process the poison message separately.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f5729-140">[Zpracování škodlivých zpráv](../../../../docs/framework/wcf/feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="f5729-140"> [Poison Message Handling](../../../../docs/framework/wcf/feature-details/poison-message-handling.md).</span></span>  
  
## <a name="achieving-high-throughput"></a><span data-ttu-id="f5729-141">Dosahuje vysoké propustnosti</span><span class="sxs-lookup"><span data-stu-id="f5729-141">Achieving High Throughput</span></span>  
 <span data-ttu-id="f5729-142">K dosažení vysoké propustnosti na jednom koncovém bodě, použijte tento příkaz:</span><span class="sxs-lookup"><span data-stu-id="f5729-142">To achieve high throughput on a single endpoint, use the following:</span></span>  
  
-   <span data-ttu-id="f5729-143">Transakční dávkování.</span><span class="sxs-lookup"><span data-stu-id="f5729-143">Transacted batching.</span></span> <span data-ttu-id="f5729-144">Dávkové zajistí, že mnoho zpráv lze číst v rámci jedné transakce.</span><span class="sxs-lookup"><span data-stu-id="f5729-144">Transacted batching ensures that many messages can be read in a single transaction.</span></span> <span data-ttu-id="f5729-145">Tím se optimalizuje potvrzení transakcí, zvýšit celkový výkon.</span><span class="sxs-lookup"><span data-stu-id="f5729-145">This optimizes transaction commits, increasing overall performance.</span></span> <span data-ttu-id="f5729-146">Náklady na dávkování je, že pokud dojde k selhání do jedné zprávy v dávce, pak celý batch je vrácena zpět a zprávy musí být zpracovaná jeden po druhém, dokud je bezpečné batch znovu.</span><span class="sxs-lookup"><span data-stu-id="f5729-146">The cost of batching is that if a failure occurs in a single message within a batch, then the entire batch is rolled back and the messages must be processed one at a time until it is safe to batch again.</span></span> <span data-ttu-id="f5729-147">Ve většině případů jsou taková situace vzácná, poškozených zpráv, takže dávkování je upřednostňovaný způsob, jak zvýšit výkon systému, zejména v případě, že máte další správci prostředků, které jsou součástí transakce.</span><span class="sxs-lookup"><span data-stu-id="f5729-147">In most cases, poison messages are rare, so batching is the preferred way to increase system performance, particularly when you have other resource managers that participate in the transaction.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f5729-148">[Dávkování zpráv v transakci](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="f5729-148"> [Batching Messages in a Transaction](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md).</span></span>  
  
-   <span data-ttu-id="f5729-149">Souběžnosti.</span><span class="sxs-lookup"><span data-stu-id="f5729-149">Concurrency.</span></span> <span data-ttu-id="f5729-150">Concurrency zvyšuje propustnost, ale souběžnosti ovlivní také kolizí ke sdíleným prostředkům.</span><span class="sxs-lookup"><span data-stu-id="f5729-150">Concurrency increases throughput, but concurrency also affects contention to shared resources.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f5729-151">[Souběžnosti](../../../../docs/framework/wcf/samples/concurrency.md).</span><span class="sxs-lookup"><span data-stu-id="f5729-151"> [Concurrency](../../../../docs/framework/wcf/samples/concurrency.md).</span></span>  
  
-   <span data-ttu-id="f5729-152">Omezení šířky pásma.</span><span class="sxs-lookup"><span data-stu-id="f5729-152">Throttling.</span></span> <span data-ttu-id="f5729-153">Pro optimální výkon omezit počet zpráv v dispečeru kanálu.</span><span class="sxs-lookup"><span data-stu-id="f5729-153">For optimal performance, throttle the number of messages in the dispatcher pipeline.</span></span> <span data-ttu-id="f5729-154">Příklad toho, jak to provést, naleznete v části [omezování](../../../../docs/framework/wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="f5729-154">For an example of how to do this, see [Throttling](../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
 <span data-ttu-id="f5729-155">Při použití dávkování, mějte na paměti, že souběžnosti a omezování nepřeloží na souběžných dávky.</span><span class="sxs-lookup"><span data-stu-id="f5729-155">When using batching, be aware that concurrency and throttling translate to concurrent batches.</span></span>  
  
 <span data-ttu-id="f5729-156">K dosažení vyšší propustnost a dostupnost, použít farmu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] služby, které číst zprávy z fronty.</span><span class="sxs-lookup"><span data-stu-id="f5729-156">To achieve higher throughput and availability, use a farm of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services that read from the queue.</span></span> <span data-ttu-id="f5729-157">To vyžaduje, aby všechny tyto služby vystavit stejné smlouvy na stejný koncový bod.</span><span class="sxs-lookup"><span data-stu-id="f5729-157">This requires that all of these services expose the same contract on the same endpoint.</span></span> <span data-ttu-id="f5729-158">Přístup farmy je nejvhodnější pro aplikace, které mají vysokou produkční počty zpráv, protože umožní několik služeb pro všechny číst ze stejné fronty.</span><span class="sxs-lookup"><span data-stu-id="f5729-158">The farm approach works best for applications that have high production rates of messages because it enables a number of services to all read from the same queue.</span></span>  
  
 <span data-ttu-id="f5729-159">Při použití farmy, mějte na paměti, že služby MSMQ 3.0 nepodporuje vzdálené zpracovaných čtení.</span><span class="sxs-lookup"><span data-stu-id="f5729-159">When using farms, be aware that MSMQ 3.0 does not support remote transacted reads.</span></span> <span data-ttu-id="f5729-160">MSMQ 4.0 podporuje vzdálené zpracovaných čtení.</span><span class="sxs-lookup"><span data-stu-id="f5729-160">MSMQ 4.0 does support remote transacted reads.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f5729-161">[Dávkování zpráv v transakci](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md) a [rozdíly funkcí front zpráv v systému Windows Vista, Windows Server 2003 a Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).</span><span class="sxs-lookup"><span data-stu-id="f5729-161"> [Batching Messages in a Transaction](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md) and [Differences in Queuing Features in Windows Vista, Windows Server 2003, and Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).</span></span>  
  
## <a name="queuing-with-unit-of-work-semantics"></a><span data-ttu-id="f5729-162">Služba Řízení front s jednotkou pracovní sémantiku</span><span class="sxs-lookup"><span data-stu-id="f5729-162">Queuing with Unit of Work Semantics</span></span>  
 <span data-ttu-id="f5729-163">V některých případech může souviset skupinu zpráv ve frontě, a proto je důležité pořadí těchto zpráv.</span><span class="sxs-lookup"><span data-stu-id="f5729-163">In some scenarios a group of messages in a queue may be related and, therefore, the ordering of these messages is significant.</span></span> <span data-ttu-id="f5729-164">V takových případech zpracovat skupinu související zprávy společně jako jednu jednotku: buď všechny zprávy úspěšně zpracovat, nebo žádný.</span><span class="sxs-lookup"><span data-stu-id="f5729-164">In such scenarios, process a group of related messages together as a single unit: either all of the messages are processed successfully or none are.</span></span> <span data-ttu-id="f5729-165">Chcete-li implementovat takové chování, použijte relace s fronty.</span><span class="sxs-lookup"><span data-stu-id="f5729-165">To implement such behavior, use sessions with queues.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f5729-166">[Seskupování zpráv zařazených do fronty v relaci](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md).</span><span class="sxs-lookup"><span data-stu-id="f5729-166"> [Grouping Queued Messages in a Session](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md).</span></span>  
  
## <a name="correlating-request-reply-messages"></a><span data-ttu-id="f5729-167">Korelace zprávy požadavku a odpovědi</span><span class="sxs-lookup"><span data-stu-id="f5729-167">Correlating Request-Reply Messages</span></span>  
 <span data-ttu-id="f5729-168">I když fronty jsou obvykle jednosměrné, v některých případech můžete chtít korelovat odpověď přijata na žádost odeslány dříve.</span><span class="sxs-lookup"><span data-stu-id="f5729-168">Though queues are typically one-way, in some scenarios you may want to correlate a reply received to a request sent earlier.</span></span> <span data-ttu-id="f5729-169">Pokud budete potřebovat takové korelace, doporučujeme, abyste použili vlastní záhlaví zprávy protokolu SOAP, který obsahuje informace o korelace se zprávou.</span><span class="sxs-lookup"><span data-stu-id="f5729-169">If you require such correlation, it is recommended that you apply your own SOAP message header that contains correlation information with the message.</span></span> <span data-ttu-id="f5729-170">Obvykle odesílatel připojí tuto hlavičku se zprávou a příjemce při zpracování zprávy a odeslání odpovědi zpět s novou zprávu ve frontě s odpovědí, připojí záhlaví zprávy odesílatele, obsahující informace o korelace tak, aby odesílatel možné Identifikujte zprávu odpovědi s zprávu požadavku.</span><span class="sxs-lookup"><span data-stu-id="f5729-170">Typically, the sender attaches this header with the message, and the receiver, upon processing the message and replying back with a new message on a reply queue, attaches the sender's message header that contains the correlation information so that the sender can identify the reply message with the request message.</span></span>  
  
## <a name="integrating-with-non-wcf-applications"></a><span data-ttu-id="f5729-171">Integrace s aplikacemi bez WCF</span><span class="sxs-lookup"><span data-stu-id="f5729-171">Integrating with Non-WCF Applications</span></span>  
 <span data-ttu-id="f5729-172">Použití `MsmqIntegrationBinding` při integraci [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] služby nebo klientů s jinou hodnotu než[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] služby nebo klientů.</span><span class="sxs-lookup"><span data-stu-id="f5729-172">Use `MsmqIntegrationBinding` when integrating [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services or clients with non-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services or clients.</span></span> <span data-ttu-id="f5729-173">Jinou hodnotu než[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] MSMQ aplikace napsané v System.Messaging, COM +, může se aplikace [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], nebo C++.</span><span class="sxs-lookup"><span data-stu-id="f5729-173">The non-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application can be an MSMQ application written using System.Messaging, COM+, [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], or C++.</span></span>  
  
 <span data-ttu-id="f5729-174">Při použití `MsmqIntegrationBinding`, mít na paměti následující:</span><span class="sxs-lookup"><span data-stu-id="f5729-174">When using `MsmqIntegrationBinding`, be aware of the following:</span></span>  
  
-   <span data-ttu-id="f5729-175">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tělo zprávy není stejný jako text zprávy služby MSMQ.</span><span class="sxs-lookup"><span data-stu-id="f5729-175">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message body is not the same as a MSMQ message body.</span></span> <span data-ttu-id="f5729-176">Při odesílání [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zprávu pomocí vazbu zařazených do fronty [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] text zprávy je umístěn uvnitř zprávu služby MSMQ.</span><span class="sxs-lookup"><span data-stu-id="f5729-176">When sending a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message using a queued binding, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message body is placed inside of a MSMQ message.</span></span> <span data-ttu-id="f5729-177">Infrastruktura služby MSMQ je oblivious na tyto doplňující informace; se zobrazí pouze zprávy služby MSMQ.</span><span class="sxs-lookup"><span data-stu-id="f5729-177">The MSMQ infrastructure is oblivious to this extra information; it sees only the MSMQ message.</span></span>  
  
-   <span data-ttu-id="f5729-178">`MsmqIntegrationBinding`podporuje typy oblíbených serializace.</span><span class="sxs-lookup"><span data-stu-id="f5729-178">`MsmqIntegrationBinding` supports popular serialization types.</span></span> <span data-ttu-id="f5729-179">Na základě serializace typu, typ těla zprávy obecné zprávy <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, používá jiný typ parametry.</span><span class="sxs-lookup"><span data-stu-id="f5729-179">Based on the serialization type, the body type of the generic message, <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, takes different type parameters.</span></span> <span data-ttu-id="f5729-180">Například <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.ByteArray> vyžaduje `MsmqMessage\<byte[]>` a <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.Stream> vyžaduje `MsmqMessage<Stream>`.</span><span class="sxs-lookup"><span data-stu-id="f5729-180">For example, <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.ByteArray> requires `MsmqMessage\<byte[]>` and <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.Stream> requires `MsmqMessage<Stream>`.</span></span>  
  
-   <span data-ttu-id="f5729-181">S serializace XML, můžete zadat pomocí známého typu `KnownTypes` atributu u [ \<chování >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element, který se pak použije k určení jak k deserializaci. zprávu XML.</span><span class="sxs-lookup"><span data-stu-id="f5729-181">With XML serialization, you can specify the known type using the `KnownTypes` attribute on the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element that is then used to determine how to deserialize the XML message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5729-182">Viz také</span><span class="sxs-lookup"><span data-stu-id="f5729-182">See Also</span></span>  
 [<span data-ttu-id="f5729-183">Fronty ve WCF</span><span class="sxs-lookup"><span data-stu-id="f5729-183">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="f5729-184">Postupy: výměna zpráv pomocí koncových bodů WCF zařazených do fronty.</span><span class="sxs-lookup"><span data-stu-id="f5729-184">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [<span data-ttu-id="f5729-185">Postupy: výměna zpráv pomocí koncových bodů WCF a aplikací služby Řízení front zpráv</span><span class="sxs-lookup"><span data-stu-id="f5729-185">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="f5729-186">Seskupování zpráv zařazených do fronty v relaci</span><span class="sxs-lookup"><span data-stu-id="f5729-186">Grouping Queued Messages in a Session</span></span>](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)  
 [<span data-ttu-id="f5729-187">Dávkování zpráv v transakci</span><span class="sxs-lookup"><span data-stu-id="f5729-187">Batching Messages in a Transaction</span></span>](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
 [<span data-ttu-id="f5729-188">Zpracování chyb přenosu zpráv pomocí front nedoručených zpráv</span><span class="sxs-lookup"><span data-stu-id="f5729-188">Using Dead-Letter Queues to Handle Message Transfer Failures</span></span>](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 [<span data-ttu-id="f5729-189">Zpracování škodlivých zpráv</span><span class="sxs-lookup"><span data-stu-id="f5729-189">Poison Message Handling</span></span>](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)  
 [<span data-ttu-id="f5729-190">Rozdíly funkcí front zpráv v systému Windows Vista, Windows Server 2003 a Windows XP</span><span class="sxs-lookup"><span data-stu-id="f5729-190">Differences in Queuing Features in Windows Vista, Windows Server 2003, and Windows XP</span></span>](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)  
 [<span data-ttu-id="f5729-191">Zabezpečení zpráv pomocí zabezpečení přenosu</span><span class="sxs-lookup"><span data-stu-id="f5729-191">Securing Messages Using Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 [<span data-ttu-id="f5729-192">Zabezpečení zpráv pomocí zabezpečení zpráv</span><span class="sxs-lookup"><span data-stu-id="f5729-192">Securing Messages Using Message Security</span></span>](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)  
 [<span data-ttu-id="f5729-193">Řešení potíží s zasílání zpráv ve frontě</span><span class="sxs-lookup"><span data-stu-id="f5729-193">Troubleshooting Queued Messaging</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)