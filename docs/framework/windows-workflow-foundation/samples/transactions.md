---
title: Transactions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c7611ce26c1a3b9150a60ced7b4931cc1282eecd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="transactions"></a><span data-ttu-id="7f976-102">Transakce</span><span class="sxs-lookup"><span data-stu-id="7f976-102">Transactions</span></span>
<span data-ttu-id="7f976-103">Tato část obsahuje ukázky, která ukazují pracovní postup transakce v [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f976-103">This section contains samples that demonstrate workflow transactions in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f976-104">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="7f976-104">In This Section</span></span>  
 [<span data-ttu-id="7f976-105">Základní TransactionScope</span><span class="sxs-lookup"><span data-stu-id="7f976-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="7f976-106">Se skládá ze čtyř scénáře, které ukazují, jak lze vnořit <xref:System.Activities.Statements.TransactionScope> instance.</span><span class="sxs-lookup"><span data-stu-id="7f976-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="7f976-107">Použití TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="7f976-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="7f976-108">Ukazuje, jak toku transakce z klienta na server pomocí <xref:System.Activities.Statements.TransactionScope> vytvořit novou transakci na straně klienta a <xref:System.ServiceModel.Activities.TransactedReceiveScope> přijmout zprávu s sdružení transakcí a obor životnost transakce na serveru.</span><span class="sxs-lookup"><span data-stu-id="7f976-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="7f976-109">Vnoření TransactionScope v rámci služby</span><span class="sxs-lookup"><span data-stu-id="7f976-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="7f976-110">Se skládá z těchto dvou scénářů, které ukazují, jak zpracovat <xref:System.Activities.Statements.TransactionScope> instance aktivit v rámci služby.</span><span class="sxs-lookup"><span data-stu-id="7f976-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>