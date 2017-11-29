---
title: "PŘEJDĚTE (entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c82149fb5d76ac7b95198ce2b29550eade54b48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="e26c7-102">PŘEJDĚTE (entita SQL)</span><span class="sxs-lookup"><span data-stu-id="e26c7-102">NAVIGATE (Entity SQL)</span></span>
<span data-ttu-id="e26c7-103">Přejde přes vztahu mezi entity.</span><span class="sxs-lookup"><span data-stu-id="e26c7-103">Navigates over the relationship established between entities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e26c7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e26c7-104">Syntax</span></span>  
  
```  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## <a name="arguments"></a><span data-ttu-id="e26c7-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="e26c7-105">Arguments</span></span>  
 `instance-expresssion`  
 <span data-ttu-id="e26c7-106">Instance entity.</span><span class="sxs-lookup"><span data-stu-id="e26c7-106">An instance of an entity.</span></span>  
  
 `relationship-type`  
 <span data-ttu-id="e26c7-107">Název typu vztahu z soubor konceptuálního schématu definition language (CSDL).</span><span class="sxs-lookup"><span data-stu-id="e26c7-107">The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="e26c7-108">`relationship-type` Je kvalifikovaný jako \<obor názvů >.\< Název typu vztahu >.</span><span class="sxs-lookup"><span data-stu-id="e26c7-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>  
  
 `to`  
 <span data-ttu-id="e26c7-109">Konec relace.</span><span class="sxs-lookup"><span data-stu-id="e26c7-109">The end of the relationship.</span></span>  
  
 `from`  
 <span data-ttu-id="e26c7-110">Začátek relace.</span><span class="sxs-lookup"><span data-stu-id="e26c7-110">The beginning of the relationship.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e26c7-111">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="e26c7-111">Return Value</span></span>  
 <span data-ttu-id="e26c7-112">Pokud na kardinalitu pro ukončení je 1, bude vrácenou hodnotu `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="e26c7-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="e26c7-113">Pokud na kardinalitu na konec n, bude vrácenou hodnotu `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="e26c7-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e26c7-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e26c7-114">Remarks</span></span>  
 <span data-ttu-id="e26c7-115">První třídy konstrukce v se vztahy [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span><span class="sxs-lookup"><span data-stu-id="e26c7-115">Relationships are first-class constructs in the [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span></span> <span data-ttu-id="e26c7-116">Vztahy lze navázat mezi dva nebo více typy entit a uživatelé mohou přejít přes vztah z jednoho elementu end (entita) do jiné.</span><span class="sxs-lookup"><span data-stu-id="e26c7-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="e26c7-117">`from`a `to` jsou podmíněně volitelné při překladu názvů v rámci relace nedochází k nejednoznačnosti.</span><span class="sxs-lookup"><span data-stu-id="e26c7-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>  
  
 <span data-ttu-id="e26c7-118">NAVIGOVAT je platná v prostoru O a C.</span><span class="sxs-lookup"><span data-stu-id="e26c7-118">NAVIGATE is valid in O and C space.</span></span>  
  
 <span data-ttu-id="e26c7-119">Obecná forma konstrukce navigace je následující:</span><span class="sxs-lookup"><span data-stu-id="e26c7-119">The general form of a navigation construct is the following:</span></span>  
  
 <span data-ttu-id="e26c7-120">přejděte (`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ]])</span><span class="sxs-lookup"><span data-stu-id="e26c7-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>  
  
 <span data-ttu-id="e26c7-121">Příklad:</span><span class="sxs-lookup"><span data-stu-id="e26c7-121">For example:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="e26c7-122">Kde je OrderCustomer `relationship`, a jsou zákazníka a pořadí `to-end` (zákazníka) a `from-end` (pořadí elementů) vztahu.</span><span class="sxs-lookup"><span data-stu-id="e26c7-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="e26c7-123">Jestliže byl OrderCustomer relaci n: 1, bude výsledný typ výrazu přejděte Ref\<zákazníka >.</span><span class="sxs-lookup"><span data-stu-id="e26c7-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>  
  
 <span data-ttu-id="e26c7-124">Jednodušší formu výrazu je následující:</span><span class="sxs-lookup"><span data-stu-id="e26c7-124">The simpler form of this expression is the following:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="e26c7-125">Podobně v dotazu má následující formu, přejděte výraz byste mohli vytvořit kolekci < Ref\<pořadí >>.</span><span class="sxs-lookup"><span data-stu-id="e26c7-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 <span data-ttu-id="e26c7-126">Instance výraz musí být typu entity nebo ref.</span><span class="sxs-lookup"><span data-stu-id="e26c7-126">The instance-expression must be an entity/ref type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e26c7-127">Příklad</span><span class="sxs-lookup"><span data-stu-id="e26c7-127">Example</span></span>  
 <span data-ttu-id="e26c7-128">Následující dotaz Entity SQL pomocí operátoru přejděte přejděte přes vztahu mezi adresu a SalesOrderHeader typy entit.</span><span class="sxs-lookup"><span data-stu-id="e26c7-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="e26c7-129">Dotaz je založen na modelu prodej AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e26c7-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e26c7-130">Pro zkompilování a spuštění tohoto dotazu, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="e26c7-130">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e26c7-131">Postupujte podle pokynů v [postup: provedení dotazu tohoto vrátí výsledky StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e26c7-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e26c7-132">Předat jako argument pro následující dotaz `ExecuteStructuralTypeQuery` metoda:</span><span class="sxs-lookup"><span data-stu-id="e26c7-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## <a name="see-also"></a><span data-ttu-id="e26c7-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="e26c7-133">See Also</span></span>  
 [<span data-ttu-id="e26c7-134">Odkaz na entitu SQL</span><span class="sxs-lookup"><span data-stu-id="e26c7-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="e26c7-135">Postupy: přejděte relace se přejděte – operátor</span><span class="sxs-lookup"><span data-stu-id="e26c7-135">How to: Navigate Relationships with Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)