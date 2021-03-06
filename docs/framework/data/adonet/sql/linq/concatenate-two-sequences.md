---
title: "Řetězení dvě pořadí"
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
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a73ace484c3ca519f250069063a9222b75ef6c17
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/17/2018
---
# <a name="concatenate-two-sequences"></a>Řetězení dvě pořadí
Použití <xref:System.Linq.Queryable.Concat%2A> operátor ke zřetězení dvě pořadí.  
  
 <xref:System.Linq.Queryable.Concat%2A> Operátor je definována pro seřazené multisets kde objednávky příjemce a argument jsou stejné.  
  
 Řazení v systému SQL je v posledním kroku, před vytváří výsledky. Z tohoto důvodu <xref:System.Linq.Queryable.Concat%2A> operátor je implementována pomocí `UNION ALL` a nezachovává pořadí argumentů. Ujistěte se, že řazení je správný ve výsledcích, zajistěte, aby explicitně řazení výsledků.  
  
## <a name="example"></a>Příklad  
 Tento příklad používá <xref:System.Linq.Queryable.Concat%2A> vrátit pořadí všech `Customer` a `Employee` číslo telefonu a faxu.  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a>Příklad  
 Tento příklad používá <xref:System.Linq.Queryable.Concat%2A> vrátit pořadí všech `Customer` a `Employee` název a telefonní číslo mapování.  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a>Viz také  
 [Příklady dotazů](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Převod standardních operátorů dotazů](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
