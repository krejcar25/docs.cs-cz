---
title: Sada (entita SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1378295cfa8e2563e56843c2e1dec89846bbf494
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/17/2018
---
# <a name="set-entity-sql"></a>Sada (entita SQL)
Výraz sady se používá k získávání novou kolekci s všechny elementy s duplicitním odebrat převést na kolekci objektů do sady.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Jakýkoli platný dotaz výraz, která vrátí kolekci.  
  
## <a name="remarks"></a>Poznámky  
 Výraz sady `SET(c)` logicky odpovídá následující příkaz select:  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET`patří mezi [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nastavit operátory. Všechny [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operátory set vyhodnocovány zleva doprava. V tématu [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) přednost informace pro [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nastavit operátory.  
  
## <a name="example"></a>Příklad  
 Následující dotaz Entity SQL používá pro převod na kolekci objektů do sady výraz sady. Dotaz je založen na modelu prodej AdventureWorks. Pro zkompilování a spuštění tohoto dotazu, postupujte takto:  
  
1.  Postupujte podle pokynů v [postup: provedení dotazu tohoto vrátí výsledky PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Předat jako argument pro následující dotaz `ExecutePrimitiveTypeQuery` metoda:  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a>Viz také  
 [Reference k Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
