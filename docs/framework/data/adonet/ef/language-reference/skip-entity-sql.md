---
title: "Přeskočit (entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0dd0754158000642dd078f00033c9ddc2f78686d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="skip-entity-sql"></a>Přeskočit (entita SQL)
Fyzické stránkování můžete provést pomocí dílčí klauzuli SKIP v klauzuli ORDER by. SKIP nelze použít samostatně z klauzule ORDER by.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a>Arguments  
 `n`  
 Počet položek tak, aby přeskočil.  
  
## <a name="remarks"></a>Poznámky  
 Pokud se nachází dílčí klauzuli SKIP výrazu v klauzuli ORDER BY, výsledky budou seřazeny podle specifikace řazení a sadu výsledků dotazu zahrne řádky začínající z na další řádek hned po výrazu SKIP. Například bude 5 PŘESKOČENÍ přeskočte prvních pět řádky a vrátí z šesté řádek dál.  
  
> [!NOTE]
>  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Dotaz je neplatný, pokud modifikátor TOP a dílčí klauzuli SKIP se nacházejí ve stejném výrazu dotazu. Dotaz by měl být přepsána změnou výraz TOP na výrazu omezení.  
  
> [!NOTE]
>  V [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], pomocí přeskočit s klauzulí ORDER BY v neklíčových sloupců může vrátit nesprávné výsledky. Více než zadaný počet řádků může přeskočen. Pokud neklíčový sloupec obsahuje duplicitní data v ní. Je to z důvodu jak SKIP je přeložená pro [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]. Například v následujícím kódu více než pět řádků může být přeskočeno `E.NonKeyColumn` obsahuje duplicitní hodnoty:  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Dotazu v [to](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) příklad používá operátor ORDER BY s PŘESKOČENÍM k určení pořadí řazení použít u objektů, vrátí se v příkazu SELECT.  
  
## <a name="see-also"></a>Viz také  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [Postupy: výsledky stránky prostřednictvím dotazu](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [Stránkování](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
