---
title: "N-vrstvá a vzdálené aplikace s dotazy LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f44b6da8ecc8d036a9550856f71b2981770e9478
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a><span data-ttu-id="ac32b-102">N-vrstvá a vzdálené aplikace s dotazy LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ac32b-102">N-Tier and Remote Applications with LINQ to SQL</span></span>
<span data-ttu-id="ac32b-103">Můžete vytvořit n vrstvá nebo vícevrstvé aplikace, které používají [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac32b-103">You can create n-tier or multitier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="ac32b-104">Obvykle [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] kontextu dat, tříd entit a konstrukce logiku dotazu se nacházejí ve střední vrstvě jako vrstva přístupu k datům (DAL).</span><span class="sxs-lookup"><span data-stu-id="ac32b-104">Typically, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] data context, entity classes, and query construction logic are located on the middle tier as the data access layer (DAL).</span></span> <span data-ttu-id="ac32b-105">Obchodní logika a žádná dočasnou data můžou se implementovat zcela v částečné třídy a metody entity a kontext dat, nebo se dá implementovat v samostatné třídy.</span><span class="sxs-lookup"><span data-stu-id="ac32b-105">Business logic and any non-persistent data can be implemented completely in partial classes and methods of entities and the data context, or it can be implemented in separate classes.</span></span>  
  
 <span data-ttu-id="ac32b-106">Klient nebo prezentační vrstva volá metody na střední vrstvě pro vzdálené rozhraní a v této vrstvě DAL, budou spuštěny dotazy nebo uložené procedury, které jsou mapované na <xref:System.Data.Linq.DataContext> metody.</span><span class="sxs-lookup"><span data-stu-id="ac32b-106">The client or presentation layer calls methods on the middle-tier's remote interface, and the DAL on that tier will execute queries or stored procedures that are mapped to <xref:System.Data.Linq.DataContext> methods.</span></span> <span data-ttu-id="ac32b-107">Střední vrstva vrátí data o klientům obvykle jako reprezentace XML entity nebo objekty proxy.</span><span class="sxs-lookup"><span data-stu-id="ac32b-107">The middle tier returns the data to clients typically as XML representations of entities or proxy objects.</span></span>  
  
 <span data-ttu-id="ac32b-108">Ve střední vrstvě jsou entity vytvořené pomocí kontextu dat, která sleduje jejich stavu a spravuje odložené načítání z a odeslání změn do databáze.</span><span class="sxs-lookup"><span data-stu-id="ac32b-108">On the middle tier, entities are created by the data context, which tracks their state, and manages deferred loading from and submission of changes to the database.</span></span> <span data-ttu-id="ac32b-109">Tyto entity jsou "připojené" k `DataContext`.</span><span class="sxs-lookup"><span data-stu-id="ac32b-109">These entities are "attached" to the `DataContext`.</span></span> <span data-ttu-id="ac32b-110">Ale po entity, které se odesílají na jinou vrstvu prostřednictvím serializace, budou odpojit, což znamená, že `DataContext` už ke sledování stavu.</span><span class="sxs-lookup"><span data-stu-id="ac32b-110">However, after the entities are sent to another tier through serialization, they become detached, which means the `DataContext` is no longer tracking their state.</span></span> <span data-ttu-id="ac32b-111">Entit, které klient odešle zpět aktualizací musí být znovu připojit ke kontextu dat před [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] můžete odeslat provedené změny do databáze.</span><span class="sxs-lookup"><span data-stu-id="ac32b-111">Entities that the client sends back for updates must be reattached to the data context before [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can submit the changes to the database.</span></span> <span data-ttu-id="ac32b-112">Klient zodpovídá za poskytování původní hodnoty nebo časová razítka zpět střední vrstvy, pokud těch, které jsou požadovány pro optimistickou metodu souběžného kontroly.</span><span class="sxs-lookup"><span data-stu-id="ac32b-112">The client is responsible for providing original values and/or timestamps back to the middle tier if those are required for optimistic concurrency checks.</span></span>  
  
 <span data-ttu-id="ac32b-113">V aplikacích ASP.NET <xref:System.Web.UI.WebControls.LinqDataSource> spravuje většinu této složitost.</span><span class="sxs-lookup"><span data-stu-id="ac32b-113">In ASP.NET applications, the <xref:System.Web.UI.WebControls.LinqDataSource> manages most of this complexity.</span></span> <span data-ttu-id="ac32b-114">Další informace najdete v tématu [NIB: Přehled ovládacího prvku webového serveru LinqDataSource](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).</span><span class="sxs-lookup"><span data-stu-id="ac32b-114">For more information, see [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="ac32b-115">Další prostředky</span><span class="sxs-lookup"><span data-stu-id="ac32b-115">Additional Resources</span></span>  
 <span data-ttu-id="ac32b-116">Další informace o tom, jak implementovat vícevrstvé aplikace, které používají [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], najdete v následujících tématech:</span><span class="sxs-lookup"><span data-stu-id="ac32b-116">For more information about how to implement n-tier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], see the following topics:</span></span>  
  
-   [<span data-ttu-id="ac32b-117">Technologie LINQ to SQL N-vrstvá s technologií ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ac32b-117">LINQ to SQL N-Tier with ASP.NET</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [<span data-ttu-id="ac32b-118">Technologie LINQ to SQL N-vrstvá s webovými službami</span><span class="sxs-lookup"><span data-stu-id="ac32b-118">LINQ to SQL N-Tier with Web Services</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [<span data-ttu-id="ac32b-119">Technologie LINQ to SQL s aplikacemi úzce párované Klient Server</span><span class="sxs-lookup"><span data-stu-id="ac32b-119">LINQ to SQL with Tightly-Coupled Client-Server Applications</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [<span data-ttu-id="ac32b-120">Implementace vícevrstvé obchodní logiky</span><span class="sxs-lookup"><span data-stu-id="ac32b-120">Implementing N-Tier Business Logic</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [<span data-ttu-id="ac32b-121">Operace vytvoření ve víceúrovňových aplikacích (technologie LINQ to SQL) a načtení dat</span><span class="sxs-lookup"><span data-stu-id="ac32b-121">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 <span data-ttu-id="ac32b-122">Další informace o vícevrstvé aplikace, které používají datové ADO.NET naleznete v tématu [pracovat s datovými sadami ve vícevrstvých aplikacích](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span><span class="sxs-lookup"><span data-stu-id="ac32b-122">For more information about n-tier applications that use ADO.NET DataSets, see [Work with datasets in n-tier applications](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac32b-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="ac32b-123">See Also</span></span>  
 [<span data-ttu-id="ac32b-124">Základní informace</span><span class="sxs-lookup"><span data-stu-id="ac32b-124">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)