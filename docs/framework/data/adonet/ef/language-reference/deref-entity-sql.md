---
title: DEREF (entita SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 49ae645baccf877a8e9c0f80ac8827823b9d6c34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="deref-entity-sql"></a><span data-ttu-id="c2138-102">DEREF (entita SQL)</span><span class="sxs-lookup"><span data-stu-id="c2138-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="c2138-103">Dereferences hodnota odkazu a vytváří výsledek této dereference.</span><span class="sxs-lookup"><span data-stu-id="c2138-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2138-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c2138-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2138-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="c2138-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c2138-106">Jakýkoli platný dotaz výraz, která vrátí kolekci.</span><span class="sxs-lookup"><span data-stu-id="c2138-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2138-107">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="c2138-107">Return Value</span></span>  
 <span data-ttu-id="c2138-108">Hodnota entity, který se odkazuje.</span><span class="sxs-lookup"><span data-stu-id="c2138-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2138-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c2138-109">Remarks</span></span>  
 <span data-ttu-id="c2138-110">Operátor DEREF dereferences hodnota odkazu a vytváří výsledek této dereference.</span><span class="sxs-lookup"><span data-stu-id="c2138-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="c2138-111">Například pokud `r` odkaz typu ref\<T >, `Deref``(r)` je výraz typu `T` , vypočítá entita odkazuje `r`.</span><span class="sxs-lookup"><span data-stu-id="c2138-111">For example, if `r` is a reference of type ref\<T>, `Deref``(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="c2138-112">Pokud hodnota odkaz má hodnotu null nebo je nepropojená (který je cílem odkazu neexistuje), výsledkem operátoru DEREF má hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="c2138-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2138-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="c2138-113">Example</span></span>  
 <span data-ttu-id="c2138-114">Následující [!INCLUDE[esql](../../../../../../includes/esql-md.md)] dotazu pomocí operátoru DEREF dereference produktu dereference výsledek a hodnota odkazu.</span><span class="sxs-lookup"><span data-stu-id="c2138-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="c2138-115">Dotaz je založen na modelu prodej AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c2138-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c2138-116">Pro zkompilování a spuštění tohoto dotazu, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="c2138-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c2138-117">Postupujte podle pokynů v [postup: provedení dotazu tohoto vrátí výsledky PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c2138-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="c2138-118">Následující dotaz předejte jako argument metodu ExecutePrimitiveTypeQuery:</span><span class="sxs-lookup"><span data-stu-id="c2138-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="c2138-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="c2138-119">See Also</span></span>  
 [<span data-ttu-id="c2138-120">Odkaz na entitu SQL</span><span class="sxs-lookup"><span data-stu-id="c2138-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="c2138-121">REF</span><span class="sxs-lookup"><span data-stu-id="c2138-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [<span data-ttu-id="c2138-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="c2138-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="c2138-123">KLÍČ</span><span class="sxs-lookup"><span data-stu-id="c2138-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="c2138-124">Strukturované typy s možnou hodnotou Null</span><span class="sxs-lookup"><span data-stu-id="c2138-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)