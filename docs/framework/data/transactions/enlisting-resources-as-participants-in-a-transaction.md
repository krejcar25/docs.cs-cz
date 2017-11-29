---
title: "Uvedení prostředky jako účastníky v transakci"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 786a12c2-d530-49f4-9c59-5c973e15a11d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: abd80187d6dac9f94aa49d9cd9b9eb94671a7c66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="enlisting-resources-as-participants-in-a-transaction"></a><span data-ttu-id="9be36-102">Uvedení prostředky jako účastníky v transakci</span><span class="sxs-lookup"><span data-stu-id="9be36-102">Enlisting Resources as Participants in a Transaction</span></span>
<span data-ttu-id="9be36-103">Každý zdroj účasti na transakci spravuje správce prostředků, jejichž akce jsou koordinovaný správcem transakcí.</span><span class="sxs-lookup"><span data-stu-id="9be36-103">Each resource participating in a transaction is managed by a resource manager, whose actions are coordinated by a transaction manager.</span></span> <span data-ttu-id="9be36-104">Koordinace se provádí prostřednictvím oznámením na účastníky, kteří mají uveden v transakci prostřednictvím Správce transakcí.</span><span class="sxs-lookup"><span data-stu-id="9be36-104">The coordination is done through notifications given to subscribers who have enlisted in a transaction through the transaction manager.</span></span>  
  
 <span data-ttu-id="9be36-105">Toto téma popisuje, jak prostředek (nebo více zdrojů) může být uveden v transakci, jakož i různé typy zařazení.</span><span class="sxs-lookup"><span data-stu-id="9be36-105">This topic covers how a resource (or multiple resources) can be enlisted in a transaction, as well as the different types of enlistment.</span></span> <span data-ttu-id="9be36-106">[Potvrzení transakce v několika fázi a jednofázové](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md) téma popisuje, jak lze transakce závazků koordinovat mezi zařazené zdroje.</span><span class="sxs-lookup"><span data-stu-id="9be36-106">The [Committing a Transaction in Single-Phase and Multi-Phase](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md) topic covers how transaction commitment can be coordinated among enlisted resources.</span></span>  
  
## <a name="enlisting-resources-in-a-transaction"></a><span data-ttu-id="9be36-107">Uvedení prostředků v transakci</span><span class="sxs-lookup"><span data-stu-id="9be36-107">Enlisting Resources in a Transaction</span></span>  
 <span data-ttu-id="9be36-108">Chcete-li, aby zdroj k účasti v transakci musí zařadit do transakce.</span><span class="sxs-lookup"><span data-stu-id="9be36-108">In order for a resource to participate in a transaction, it must enlist in the transaction.</span></span> <span data-ttu-id="9be36-109"><xref:System.Transactions.Transaction> Třída definuje sadu metod, jejichž názvy začínají řetězcem **Enlist** , zadejte tuto funkci.</span><span class="sxs-lookup"><span data-stu-id="9be36-109">The <xref:System.Transactions.Transaction> class defines a set of methods whose names begin with **Enlist** that provide this functionality.</span></span> <span data-ttu-id="9be36-110">Různými **Enlist** metody odpovídají na různé typy zařazení, který mohl být správce prostředků.</span><span class="sxs-lookup"><span data-stu-id="9be36-110">The different **Enlist** methods correspond to the different types of enlistment that a resource manager may have.</span></span> <span data-ttu-id="9be36-111">Konkrétně používají <xref:System.Transactions.Transaction.EnlistVolatile%2A> metody pro těkavých materiály a <xref:System.Transactions.Transaction.EnlistDurable%2A> metody pro trvalý zdroje.</span><span class="sxs-lookup"><span data-stu-id="9be36-111">Specifically, you use the <xref:System.Transactions.Transaction.EnlistVolatile%2A> methods for volatile resources, and the <xref:System.Transactions.Transaction.EnlistDurable%2A> method for durable resources.</span></span> <span data-ttu-id="9be36-112">Životnost (nebo naopak nestálosti) materiálu manager odkazuje na tom, zda správce prostředků podporuje obnovení po selhání.</span><span class="sxs-lookup"><span data-stu-id="9be36-112">The durability (or conversely the volatility) of a resource manager refers to whether the resource manager supports failure recovery.</span></span> <span data-ttu-id="9be36-113">Pokud správce prostředků podporuje obnovení po selhání, přenese data do trvalého úložiště během fáze 1 (připravit) tak, pokud správce prostředků nebude fungovat, můžete zařadit do transakce při obnovení, znovu a správné činnostem podle oznámení obdržená z správce TM.</span><span class="sxs-lookup"><span data-stu-id="9be36-113">If a resource manager supports failure recovery, it persists data to durable storage during Phase1 (prepare) such that if the resource manager goes down, it can re-enlist in the transaction upon recovery and perform the proper actions based on the notifications received from the TM.</span></span> <span data-ttu-id="9be36-114">Obecně platí správci těkavých prostředků spravovat těkavých prostředků, jako jsou například struktury dat v paměti (například v paměti zpracováván jako transakce hashtable) a správci trvalý prostředků spravovat prostředky, které mají více trvalé záložní úložiště (například databáze jehož záložní úložiště je disku).</span><span class="sxs-lookup"><span data-stu-id="9be36-114">In general, volatile resource managers manage volatile resources such as an in-memory data structure (for example, an in-memory transacted-hashtable), and durable resource managers manage resources that have a more persistent backing store (for example, a database whose backing store is disk).</span></span>  
  
 <span data-ttu-id="9be36-115">Pro jednoduchost, jakmile se rozhodnete, zda se má použít <xref:System.Transactions.Transaction.EnlistDurable%2A> nebo <xref:System.Transactions.Transaction.EnlistVolatile%2A> metoda založená na podporu své prostředků životnost, by měl zařazení materiálu k účasti na dvě fáze potvrzení (2PC) implementací <xref:System.Transactions.IEnlistmentNotification> rozhraní pro váš správce prostředků.</span><span class="sxs-lookup"><span data-stu-id="9be36-115">For simplicity, after deciding whether to use the <xref:System.Transactions.Transaction.EnlistDurable%2A> or <xref:System.Transactions.Transaction.EnlistVolatile%2A> method based on your resource's durability support, you should enlist your resource to participate in Two Phase Commit (2PC) by implementing the <xref:System.Transactions.IEnlistmentNotification> interface for your resource manager.</span></span> <span data-ttu-id="9be36-116">Další informace o 2PC najdete v tématu [potvrzení transakce v několika fázi a jednofázové](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md).</span><span class="sxs-lookup"><span data-stu-id="9be36-116">For more information on 2PC, see [Committing a Transaction in Single-Phase and Multi-Phase](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md).</span></span>  
  
 <span data-ttu-id="9be36-117">Jeden účastník může zařazení pro více než jedním z těchto protokolů voláním <xref:System.Transactions.Transaction.EnlistDurable%2A> a <xref:System.Transactions.Transaction.EnlistVolatile%2A> více než jednou.</span><span class="sxs-lookup"><span data-stu-id="9be36-117">A single participant can enlist for more than one of these protocols by calling <xref:System.Transactions.Transaction.EnlistDurable%2A> and <xref:System.Transactions.Transaction.EnlistVolatile%2A> multiple times.</span></span>  
  
### <a name="durable-enlistment"></a><span data-ttu-id="9be36-118">Trvalý zařazení</span><span class="sxs-lookup"><span data-stu-id="9be36-118">Durable Enlistment</span></span>  
 <span data-ttu-id="9be36-119"><xref:System.Transactions.Transaction.EnlistDurable%2A> Metody se používají k zařazení správce prostředků pro účast v transakci jako trvalý prostředek.</span><span class="sxs-lookup"><span data-stu-id="9be36-119">The <xref:System.Transactions.Transaction.EnlistDurable%2A> methods are used to enlist a resource manager for participation in the transaction as a durable resource.</span></span>  <span data-ttu-id="9be36-120">Očekává se, že je-li správce prostředků trvalý uprostřed transakcí, lze provádět obnovení poté, co načtením zpět do režimu online podle reenlisting (pomocí <xref:System.Transactions.TransactionManager.Reenlist%2A> metoda) ve všech transakcích, v nichž byl účastník a nebyla dokončena, fáze 2 a volat <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> po dokončení zpracování obnovení.</span><span class="sxs-lookup"><span data-stu-id="9be36-120">It is expected that if a durable resource manager is brought down in the middle of a transaction, it can perform recovery once it is brought back online by reenlisting (using the <xref:System.Transactions.TransactionManager.Reenlist%2A> method) in all transactions in which it was a participant and did not complete phase 2, and call <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> once it finishes recovery processing.</span></span> <span data-ttu-id="9be36-121">Další informace o obnovení najdete v tématu [provádění obnovení](../../../../docs/framework/data/transactions/performing-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="9be36-121">For more information on recovery, see [Performing Recovery](../../../../docs/framework/data/transactions/performing-recovery.md).</span></span>  
  
 <span data-ttu-id="9be36-122"><xref:System.Transactions.Transaction.EnlistDurable%2A> Provést všechny metody <xref:System.Guid> objektu jako svůj první parametr.</span><span class="sxs-lookup"><span data-stu-id="9be36-122">The <xref:System.Transactions.Transaction.EnlistDurable%2A> methods all take a <xref:System.Guid> object as their first parameter.</span></span> <span data-ttu-id="9be36-123"><xref:System.Guid> Slouží správcem transakcí, které pokud chcete přidružit trvalý zařazení správce prostředků konkrétní.</span><span class="sxs-lookup"><span data-stu-id="9be36-123">The <xref:System.Guid> is used by the transaction manager to associate a durable enlistment with a particular resource manager.</span></span> <span data-ttu-id="9be36-124">Jako takové, je nezbytné, že správce prostředků konzistentně používá stejný <xref:System.Guid> k identifikaci i přes správci různých prostředků při restartování, v opačném případě obnovení může selhat.</span><span class="sxs-lookup"><span data-stu-id="9be36-124">As such, it is imperative that a resource manager consistently uses the same <xref:System.Guid> to identify itself even across different resource managers upon restarting, otherwise the recovery can fail.</span></span>  
  
 <span data-ttu-id="9be36-125">Druhý parametr <xref:System.Transactions.Transaction.EnlistDurable%2A> metoda je odkaz na objekt, který implementuje správce prostředků k odběru oznámení transakce.</span><span class="sxs-lookup"><span data-stu-id="9be36-125">The second parameter of the <xref:System.Transactions.Transaction.EnlistDurable%2A> method is a reference to the object that the resource manager implements to receive transaction notifications.</span></span> <span data-ttu-id="9be36-126">Přetížení, které využíváte informuje správce transakcí, zda váš správce prostředků podporuje optimalizaci jedné fáze potvrzení (SPC).</span><span class="sxs-lookup"><span data-stu-id="9be36-126">The overload you use informs the transaction manager whether your resource manager supports the Single Phase Commit (SPC) optimization.</span></span> <span data-ttu-id="9be36-127">Ve většině případů, měli byste implementovat <xref:System.Transactions.IEnlistmentNotification> rozhraní k účasti na dvoufázový potvrzení (2PC).</span><span class="sxs-lookup"><span data-stu-id="9be36-127">Most of the time you would implement the <xref:System.Transactions.IEnlistmentNotification> interface to take part in Two-Phase Commit (2PC).</span></span> <span data-ttu-id="9be36-128">Nicméně pokud chcete k optimalizaci procesu potvrzení, můžete zvážit implementaci <xref:System.Transactions.ISinglePhaseNotification> rozhraní pro certifikát SPC.</span><span class="sxs-lookup"><span data-stu-id="9be36-128">However, if you want to optimize the commit process, you can consider implementing the <xref:System.Transactions.ISinglePhaseNotification> interface for SPC.</span></span> <span data-ttu-id="9be36-129">Další informace o SPC najdete v tématu [potvrzení transakce v několika fázi a jednofázové](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md) a [optimalizace pomocí jednoho potvrdit fáze a možné zvýšit jeden oznámení fáze](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="9be36-129">For more information on SPC, see [Committing a Transaction in Single-Phase and Multi-Phase](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md) and [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
 <span data-ttu-id="9be36-130">Třetí parametr je <xref:System.Transactions.EnlistmentOptions> výčtu, jehož hodnota může být buď <xref:System.Transactions.EnlistmentOptions.None> nebo <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired>.</span><span class="sxs-lookup"><span data-stu-id="9be36-130">The third parameter is an <xref:System.Transactions.EnlistmentOptions> enumeration, whose value can be either <xref:System.Transactions.EnlistmentOptions.None> or <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired>.</span></span> <span data-ttu-id="9be36-131">Pokud hodnota je nastavena <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired>, zařazení může zahrnovat správci dalších prostředků při přijetí oznámení připravit z správce transakcí.</span><span class="sxs-lookup"><span data-stu-id="9be36-131">If the value is set to <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired>, the enlistment may enlist additional resource managers upon receiving the Prepare notification from the transaction manager.</span></span> <span data-ttu-id="9be36-132">Nicméně je třeba upozornit na to, že tento typ zařazení není nárok optimalizace jedné fáze potvrzení.</span><span class="sxs-lookup"><span data-stu-id="9be36-132">However, you should be aware that this type of enlistment is not eligible for the Single Phase Commit optimization.</span></span>  
  
### <a name="volatile-enlistment"></a><span data-ttu-id="9be36-133">Nestálá zařazení</span><span class="sxs-lookup"><span data-stu-id="9be36-133">Volatile Enlistment</span></span>  
 <span data-ttu-id="9be36-134">Správa těkavých prostředků, jako je například mezipaměť by měl zařazení pomocí účastníci <xref:System.Transactions.Transaction.EnlistVolatile%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="9be36-134">Participants managing volatile resources such as a cache should enlist using the <xref:System.Transactions.Transaction.EnlistVolatile%2A> methods.</span></span> <span data-ttu-id="9be36-135">Tyto objekty nemusí být možné získat výsledku transakce nebo obnovit stav všech transakcí, které se účastní v po selhání systému.</span><span class="sxs-lookup"><span data-stu-id="9be36-135">Such objects might not be able to obtain the outcome of a transaction or recover the state of any transaction they participate in after a system failure.</span></span>  
  
 <span data-ttu-id="9be36-136">Jak je uvedeno dříve, správce prostředků by Nestálá zařazení, pokud spravuje v paměti, těkavých zdroj.</span><span class="sxs-lookup"><span data-stu-id="9be36-136">As stated previously, a resource manager would make a volatile enlistment if it manages an in-memory, volatile resource.</span></span> <span data-ttu-id="9be36-137">Jednou z výhod pomocí <xref:System.Transactions.Transaction.EnlistVolatile%2A> je nevede nepotřebné eskalace transakce.</span><span class="sxs-lookup"><span data-stu-id="9be36-137">One of the benefits of using <xref:System.Transactions.Transaction.EnlistVolatile%2A> is that it does not force an unnecessary escalation of the transaction.</span></span> <span data-ttu-id="9be36-138">Další informace o eskalaci transakce, najdete v části [transakce správu eskalace](../../../../docs/framework/data/transactions/transaction-management-escalation.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="9be36-138">For more information on transaction escalation, see [Transaction Management Escalation](../../../../docs/framework/data/transactions/transaction-management-escalation.md) topic.</span></span> <span data-ttu-id="9be36-139">Uvedení volatilely zahrnuje i rozdíl v zpracování zařazení správcem transakcí, stejně jako očekávané ze Správce prostředků správcem transakcí.</span><span class="sxs-lookup"><span data-stu-id="9be36-139">Enlisting volatilely implies both a difference in how the enlistment is handled by the transaction manager, as well as what is expected of the resource manager by the transaction manager.</span></span> <span data-ttu-id="9be36-140">Toto je vzhledem k tomu, že správce prostředků těkavých neprovádí obnovení.</span><span class="sxs-lookup"><span data-stu-id="9be36-140">This is because a volatile resource manager does not perform recovery.</span></span> <span data-ttu-id="9be36-141"><xref:System.Transactions.Transaction.EnlistVolatile%2A> Metody nepřebírají <xref:System.Guid> parametr, vzhledem k tomu, že správce prostředků těkavých neprovádí obnovení a by volat <xref:System.Transactions.TransactionManager.Reenlist%2A> metodu, kterou je <xref:System.Guid>.</span><span class="sxs-lookup"><span data-stu-id="9be36-141">The <xref:System.Transactions.Transaction.EnlistVolatile%2A> methods do not take a <xref:System.Guid> parameter, because a volatile resource manager does not perform recovery and would not call the <xref:System.Transactions.TransactionManager.Reenlist%2A> method which needs a <xref:System.Guid>.</span></span>  
  
 <span data-ttu-id="9be36-142">Stejně jako u trvalý zařazení označuje podle toho, která přetížení metody, které použijete k zařazení do správce transakcí zda váš správce prostředků podporuje optimalizaci jedné fáze potvrzení.</span><span class="sxs-lookup"><span data-stu-id="9be36-142">As with durable enlistments, whichever overload method you use to enlist denotes to the transaction manager whether your resource manager supports the Single Phase Commit optimization.</span></span> <span data-ttu-id="9be36-143">Vzhledem k tomu, že správce prostředků těkavých nelze provést obnovení, žádné informace o obnovení pro těkavých zařazení během fáze Prepare není zapsán.</span><span class="sxs-lookup"><span data-stu-id="9be36-143">Since a volatile resource manager cannot perform recovery, no recovery information is written for a volatile enlistment during the Prepare phase.</span></span> <span data-ttu-id="9be36-144">Proto volání <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> metodu vede <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="9be36-144">Therefore, calling the <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> method results in an <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="9be36-145">Následující příklad ukazuje, jak takový objekt jako účastník v transakci pomocí zařazení do seznamu <xref:System.Transactions.Transaction.EnlistVolatile%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="9be36-145">The following example shows how to enlist such an object as a participant in a transaction using the <xref:System.Transactions.Transaction.EnlistVolatile%2A> method.</span></span>  
  
 [!code-csharp[Tx_Enlist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#1)]
 [!code-vb[Tx_Enlist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#1)]  
  
### <a name="optimizing-performance"></a><span data-ttu-id="9be36-146">Optimalizace výkonu</span><span class="sxs-lookup"><span data-stu-id="9be36-146">Optimizing Performance</span></span>  
 <span data-ttu-id="9be36-147"><xref:System.Transactions.Transaction> Třída rovněž poskytuje <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> metodu k zařazení možné zařazení pro jedné fáze (PSPE).</span><span class="sxs-lookup"><span data-stu-id="9be36-147">The <xref:System.Transactions.Transaction> class also provides the <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> method to enlist a Promotable Single Phase Enlistment (PSPE).</span></span> <span data-ttu-id="9be36-148">To umožňuje trvalý prostředku manager (SV) pro hostování a "vlastní" transakce, který lze později eskalován jej lze spravovat pomocí příkaz MSDTC v případě potřeby.</span><span class="sxs-lookup"><span data-stu-id="9be36-148">This allows a durable resource manager (RM) to host and "own" a transaction that can later be escalated to be managed by the MSDTC if necessary.</span></span> <span data-ttu-id="9be36-149">Další informace najdete v tématu [optimalizace pomocí jednoho potvrdit fáze a možné zvýšit jeden oznámení fáze](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="9be36-149">For more information on this, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be36-150">Viz také</span><span class="sxs-lookup"><span data-stu-id="9be36-150">See Also</span></span>  
 [<span data-ttu-id="9be36-151">Optimalizace pomocí jednoho potvrdit fáze a možné zvýšit jedné fáze oznámení</span><span class="sxs-lookup"><span data-stu-id="9be36-151">Optimization using Single Phase Commit and Promotable Single Phase Notification</span></span>](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)  
 [<span data-ttu-id="9be36-152">Potvrzení transakce v jednofázové a více fáze</span><span class="sxs-lookup"><span data-stu-id="9be36-152">Committing a Transaction in Single-Phase and Multi-Phase</span></span>](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md)