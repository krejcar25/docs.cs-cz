---
title: "Místní transakce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f9b1280f3a05a42a2f713adf993bb439245c95a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="local-transactions"></a><span data-ttu-id="c5917-102">Místní transakce</span><span class="sxs-lookup"><span data-stu-id="c5917-102">Local Transactions</span></span>
<span data-ttu-id="c5917-103">Transakce v [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] se používají, když chcete svázat více úkolů společně, aby se spustit jako na jednu jednotku práce.</span><span class="sxs-lookup"><span data-stu-id="c5917-103">Transactions in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] are used when you want to bind multiple tasks together so that they execute as a single unit of work.</span></span> <span data-ttu-id="c5917-104">Představte si například, že aplikace provede dvě úlohy.</span><span class="sxs-lookup"><span data-stu-id="c5917-104">For example, imagine that an application performs two tasks.</span></span> <span data-ttu-id="c5917-105">Nejprve se informace o objednávce aktualizuje tabulku.</span><span class="sxs-lookup"><span data-stu-id="c5917-105">First, it updates a table with order information.</span></span> <span data-ttu-id="c5917-106">Druhý aktualizuje tabulku, která obsahuje informace o inventáři, připsáním na stranu MD položky seřazené.</span><span class="sxs-lookup"><span data-stu-id="c5917-106">Second, it updates a table that contains inventory information, debiting the items ordered.</span></span> <span data-ttu-id="c5917-107">Pokud selže buď úlohu, pak oba aktualizace jsou vrácena zpět.</span><span class="sxs-lookup"><span data-stu-id="c5917-107">If either task fails, then both updates are rolled back.</span></span>  
  
## <a name="determining-the-transaction-type"></a><span data-ttu-id="c5917-108">Určení typu transakce</span><span class="sxs-lookup"><span data-stu-id="c5917-108">Determining the Transaction Type</span></span>  
 <span data-ttu-id="c5917-109">Transakce se považuje za místní transakce, když je jednofázové transakce a je zpracovává databázi přímo.</span><span class="sxs-lookup"><span data-stu-id="c5917-109">A transaction is considered to be a local transaction when it is a single-phase transaction and is handled by the database directly.</span></span> <span data-ttu-id="c5917-110">Transakce se považuje za distribuovanou transakci, při monitorování transakce koordinuje a používá pohotovostního mechanismy (například dvoufázový zápis) pro rozlišení transakce.</span><span class="sxs-lookup"><span data-stu-id="c5917-110">A transaction is considered to be a distributed transaction when it is coordinated by a transaction monitor and uses fail-safe mechanisms (such as two-phase commit) for transaction resolution.</span></span>  
  
 <span data-ttu-id="c5917-111">Každý z [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] zprostředkovatelé dat má svou vlastní `Transaction` objekt pro provedení místní transakce.</span><span class="sxs-lookup"><span data-stu-id="c5917-111">Each of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers has its own `Transaction` object for performing local transactions.</span></span> <span data-ttu-id="c5917-112">Pokud budete potřebovat transakce, které budou provedeny v databázi systému SQL Server, vyberte <xref:System.Data.SqlClient> transakce.</span><span class="sxs-lookup"><span data-stu-id="c5917-112">If you require a transaction to be performed in a SQL Server database, select a <xref:System.Data.SqlClient> transaction.</span></span> <span data-ttu-id="c5917-113">Pro transakci Oracle, použijte <xref:System.Data.OracleClient> zprostředkovatele.</span><span class="sxs-lookup"><span data-stu-id="c5917-113">For an Oracle transaction, use the <xref:System.Data.OracleClient> provider.</span></span> <span data-ttu-id="c5917-114">Kromě toho je nový <xref:System.Data.Common.DbTransaction> třída, která je k dispozici pro psaní kódu nezávislé na zprostředkovatele, který vyžaduje transakce.</span><span class="sxs-lookup"><span data-stu-id="c5917-114">In addition, there is a new <xref:System.Data.Common.DbTransaction> class that is available for writing provider-independent code that requires transactions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5917-115">Transakce jsou nejúčinnější, když se provádí na serveru.</span><span class="sxs-lookup"><span data-stu-id="c5917-115">Transactions are most efficient when it is performed on the server.</span></span> <span data-ttu-id="c5917-116">Pokud pracujete s databází systému SQL Server, která využívá celou explicitních transakcí, vezměte v úvahu jejich zápis jako uložené procedury pomocí příkazu Transact-SQL BEGIN TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="c5917-116">If you are working with a SQL Server database that makes extensive use of explicit transactions, consider writing them as stored procedures using the Transact-SQL BEGIN TRANSACTION statement.</span></span> <span data-ttu-id="c5917-117">Další informace o provedení transakce na straně serveru najdete v části SQL Server Books Online.</span><span class="sxs-lookup"><span data-stu-id="c5917-117">For more information about performing server-side transactions, see SQL Server Books Online.</span></span>  
  
## <a name="performing-a-transaction-using-a-single-connection"></a><span data-ttu-id="c5917-118">Provádění transakcí pomocí jednoho připojení</span><span class="sxs-lookup"><span data-stu-id="c5917-118">Performing a Transaction Using a Single Connection</span></span>  
 <span data-ttu-id="c5917-119">V [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], řídit transakce s `Connection` objektu.</span><span class="sxs-lookup"><span data-stu-id="c5917-119">In [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], you control transactions with the `Connection` object.</span></span> <span data-ttu-id="c5917-120">Můžete spustit místní transakce s `BeginTransaction` metoda.</span><span class="sxs-lookup"><span data-stu-id="c5917-120">You can initiate a local transaction with the `BeginTransaction` method.</span></span> <span data-ttu-id="c5917-121">Po zahájení transakce, můžete zařazení příkaz v této transakci s `Transaction` vlastnost `Command` objektu.</span><span class="sxs-lookup"><span data-stu-id="c5917-121">Once you have begun a transaction, you can enlist a command in that transaction with the `Transaction` property of a `Command` object.</span></span> <span data-ttu-id="c5917-122">Můžete pak potvrďte, nebo vrátit zpět změny provedené ve zdroji dat na základě úspěch nebo selhání součástí transakce.</span><span class="sxs-lookup"><span data-stu-id="c5917-122">You can then commit or roll back modifications made at the data source based on the success or failure of the components of the transaction.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5917-123">`EnlistDistributedTransaction` – Metoda by nemělo být použito pro místní transakce.</span><span class="sxs-lookup"><span data-stu-id="c5917-123">The `EnlistDistributedTransaction` method should not be used for a local transaction.</span></span>  
  
 <span data-ttu-id="c5917-124">Rozsah transakce je omezený na připojení.</span><span class="sxs-lookup"><span data-stu-id="c5917-124">The scope of the transaction is limited to the connection.</span></span> <span data-ttu-id="c5917-125">Následující příklad provádí explicitní transakce, který se skládá ze dvou samostatných příkazů v `try` bloku.</span><span class="sxs-lookup"><span data-stu-id="c5917-125">The following example performs an explicit transaction that consists of two separate commands in the `try` block.</span></span> <span data-ttu-id="c5917-126">Příkazy spusťte příkazy INSERT s tabulkou Production.ScrapReason v AdventureWorks [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] ukázkové databáze, které jsou potvrzené, pokud jsou vyvolány žádné výjimky.</span><span class="sxs-lookup"><span data-stu-id="c5917-126">The commands execute INSERT statements against the Production.ScrapReason table in the AdventureWorks [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] sample database, which are committed if no exceptions are thrown.</span></span> <span data-ttu-id="c5917-127">Kód `catch` bloku vrátí zpět transakci Pokud je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="c5917-127">The code in the `catch` block rolls back the transaction if an exception is thrown.</span></span> <span data-ttu-id="c5917-128">Pokud transakce byla přerušena, nebo připojení je ukončeno před transakce byla dokončena, je automaticky vrácena zpět.</span><span class="sxs-lookup"><span data-stu-id="c5917-128">If the transaction is aborted or the connection is closed before the transaction has completed, it is automatically rolled back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5917-129">Příklad</span><span class="sxs-lookup"><span data-stu-id="c5917-129">Example</span></span>  
 <span data-ttu-id="c5917-130">Postupujte podle těchto kroků k provedení transakce.</span><span class="sxs-lookup"><span data-stu-id="c5917-130">Follow these steps to perform a transaction.</span></span>  
  
1.  <span data-ttu-id="c5917-131">Volání <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> metodu <xref:System.Data.SqlClient.SqlConnection> objekt, který chcete označit zahájení transakce.</span><span class="sxs-lookup"><span data-stu-id="c5917-131">Call the <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to mark the start of the transaction.</span></span> <span data-ttu-id="c5917-132"><xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> Metoda vrátí odkaz na transakci.</span><span class="sxs-lookup"><span data-stu-id="c5917-132">The <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> method returns a reference to the transaction.</span></span> <span data-ttu-id="c5917-133">Tento odkaz je přiřazena k <xref:System.Data.SqlClient.SqlCommand> objekty, které jsou zařazeny v transakci.</span><span class="sxs-lookup"><span data-stu-id="c5917-133">This reference is assigned to the <xref:System.Data.SqlClient.SqlCommand> objects that are enlisted in the transaction.</span></span>  
  
2.  <span data-ttu-id="c5917-134">Přiřazení `Transaction` do objektu <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> vlastnost <xref:System.Data.SqlClient.SqlCommand> spouštění.</span><span class="sxs-lookup"><span data-stu-id="c5917-134">Assign the `Transaction` object to the <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> property of the <xref:System.Data.SqlClient.SqlCommand> to be executed.</span></span> <span data-ttu-id="c5917-135">Pokud příkaz proveden u připojení s aktivní transakce a `Transaction` objekt nebyly přiřazeny do `Transaction` vlastnost `Command` objekt, je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="c5917-135">If a command is executed on a connection with an active transaction, and the `Transaction` object has not been assigned to the `Transaction` property of the `Command` object, an exception is thrown.</span></span>  
  
3.  <span data-ttu-id="c5917-136">Spusťte požadované příkazy.</span><span class="sxs-lookup"><span data-stu-id="c5917-136">Execute the required commands.</span></span>  
  
4.  <span data-ttu-id="c5917-137">Volání <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> metodu <xref:System.Data.SqlClient.SqlTransaction> objekt, který chcete dokončit transakce, nebo volejte <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> metoda k ukončení transakce.</span><span class="sxs-lookup"><span data-stu-id="c5917-137">Call the <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> method of the <xref:System.Data.SqlClient.SqlTransaction> object to complete the transaction, or call the <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> method to end the transaction.</span></span> <span data-ttu-id="c5917-138">Pokud je připojení ukončeno nebo zlikvidován před buď <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> nebo <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> metody byly provedeny, transakce je vrácena zpět.</span><span class="sxs-lookup"><span data-stu-id="c5917-138">If the connection is closed or disposed before either the <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> or <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> methods have been executed, the transaction is rolled back.</span></span>  
  
 <span data-ttu-id="c5917-139">Následující příklad kódu ukazuje, jak pomocí transakční logiku [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] s Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5917-139">The following code example demonstrates transactional logic using [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] with Microsoft SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c5917-140">Viz také</span><span class="sxs-lookup"><span data-stu-id="c5917-140">See Also</span></span>  
 [<span data-ttu-id="c5917-141">Transakce a souběžnost</span><span class="sxs-lookup"><span data-stu-id="c5917-141">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="c5917-142">Distribuované transakce</span><span class="sxs-lookup"><span data-stu-id="c5917-142">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 [<span data-ttu-id="c5917-143">System.Transactions – integrace s SQL serverem</span><span class="sxs-lookup"><span data-stu-id="c5917-143">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 [<span data-ttu-id="c5917-144">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="c5917-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)