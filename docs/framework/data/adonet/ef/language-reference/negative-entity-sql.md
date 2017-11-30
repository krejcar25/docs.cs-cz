---
title: "- (Záporné hodnoty) (Entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0cc2ca457fe8666bddd6f4ab40d2823d9d44c591
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="2c012-102">-(Záporné) (entita SQL)</span><span class="sxs-lookup"><span data-stu-id="2c012-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="2c012-103">Vrátí záporná hodnota číselného výrazu.</span><span class="sxs-lookup"><span data-stu-id="2c012-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c012-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2c012-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2c012-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="2c012-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2c012-106">Jakýkoli platný výraz některého číselné datové typy.</span><span class="sxs-lookup"><span data-stu-id="2c012-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2c012-107">Typy výsledků</span><span class="sxs-lookup"><span data-stu-id="2c012-107">Result Types</span></span>  
 <span data-ttu-id="2c012-108">Datový typ `expression`.</span><span class="sxs-lookup"><span data-stu-id="2c012-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c012-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2c012-109">Remarks</span></span>  
 <span data-ttu-id="2c012-110">Pokud `expression` je typ nepodepsané výsledný typ bude typ se znaménkem nejvíce má vztah typu `expression`.</span><span class="sxs-lookup"><span data-stu-id="2c012-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="2c012-111">Například pokud `expression` je typu bajtů, se hodnota typu Int16 bude vrácen.</span><span class="sxs-lookup"><span data-stu-id="2c012-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c012-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="2c012-112">Example</span></span>  
 <span data-ttu-id="2c012-113">Pomocí následujícího dotazu Entity SQL-aritmetického operátoru vrátit záporná hodnota číselného výrazu.</span><span class="sxs-lookup"><span data-stu-id="2c012-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="2c012-114">Dotaz je založen na modelu prodej AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2c012-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2c012-115">Pro zkompilování a spuštění tohoto dotazu, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="2c012-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2c012-116">Postupujte podle pokynů v [postup: provedení dotazu tohoto vrátí výsledky StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2c012-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="2c012-117">Předat jako argument pro následující dotaz `ExecuteStructuralTypeQuery` metoda:</span><span class="sxs-lookup"><span data-stu-id="2c012-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="2c012-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="2c012-118">See Also</span></span>  
 [<span data-ttu-id="2c012-119">Odkaz na entitu SQL</span><span class="sxs-lookup"><span data-stu-id="2c012-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)