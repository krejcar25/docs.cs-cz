---
title: "PŘEKRYTÍ (entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b3544eac58fe168c5f2e6a355e8cf97b4598bb76
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="f8938-102">PŘEKRYTÍ (entita SQL)</span><span class="sxs-lookup"><span data-stu-id="f8938-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="f8938-103">Určuje, zda mají dvě kolekce společné prvky.</span><span class="sxs-lookup"><span data-stu-id="f8938-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8938-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f8938-104">Syntax</span></span>  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f8938-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="f8938-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="f8938-106">Libovolný platný dotaz výraz, který vrátí kolekce k porovnání s kolekcí vrácená z jiného výrazu dotazu.</span><span class="sxs-lookup"><span data-stu-id="f8938-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="f8938-107">Všechny výrazy musí být stejného typu nebo typu běžné základní nebo odvozené jako `expression`.</span><span class="sxs-lookup"><span data-stu-id="f8938-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8938-108">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="f8938-108">Return Value</span></span>  
 <span data-ttu-id="f8938-109">`true`Pokud máte dvě kolekce společné prvky; v opačném `false`.</span><span class="sxs-lookup"><span data-stu-id="f8938-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8938-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f8938-110">Remarks</span></span>  
 <span data-ttu-id="f8938-111">PŘEKRYTÍ nabízí funkčně ekvivalentní takto:</span><span class="sxs-lookup"><span data-stu-id="f8938-111">OVERLAPS provides functionally equivalent tothe following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="f8938-112">PŘEKRYTÍ je jedním z [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nastavit operátory.</span><span class="sxs-lookup"><span data-stu-id="f8938-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="f8938-113">Všechny [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operátory set vyhodnocovány zleva doprava.</span><span class="sxs-lookup"><span data-stu-id="f8938-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="f8938-114">Priorita informace pro [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nastavení operátory najdete [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f8938-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8938-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="f8938-115">Example</span></span>  
 <span data-ttu-id="f8938-116">Následující dotaz Entity SQL pomocí operátoru PŘEKRYTÍ Určuje, zda dvě kolekce mají společnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="f8938-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="f8938-117">Dotaz je založen na modelu prodej AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f8938-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f8938-118">Pro zkompilování a spuštění to, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="f8938-118">To compile and run this, follow these steps:</span></span>  
  
1.  <span data-ttu-id="f8938-119">Postupujte podle pokynů v [postup: provedení dotazu tohoto vrátí výsledky StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f8938-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="f8938-120">Předat jako argument pro následující dotaz `ExecuteStructuralTypeQuery` metoda:</span><span class="sxs-lookup"><span data-stu-id="f8938-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="f8938-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="f8938-121">See Also</span></span>  
 [<span data-ttu-id="f8938-122">Odkaz na entitu SQL</span><span class="sxs-lookup"><span data-stu-id="f8938-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)