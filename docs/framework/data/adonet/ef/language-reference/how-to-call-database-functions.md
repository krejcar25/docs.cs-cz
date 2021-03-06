---
title: "Postupy: volání funkce databáze"
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
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4395128abc3a8f604eee762479bc1a26bed7f95b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-call-database-functions"></a>Postupy: volání funkce databáze
<xref:System.Data.Objects.SqlClient.SqlFunctions> Třída obsahuje metody, které zveřejňují funkce SQL Server pomocí v technologii LINQ dotazů entity. Při použití <xref:System.Data.Objects.SqlClient.SqlFunctions> metody v technologii LINQ dotazů entity, odpovídající funkce databáze jsou spouštěny v databázi.  
  
> [!NOTE]
>  Funkce databáze, které provádět výpočet sadu hodnot a vrátí jednu hodnotu (také označované jako databáze agregační funkce) můžete přímo vyvolat. Další kanonické funkce lze volat pouze jako součást dotazu LINQ to Entities. Chcete-li volat přímo agregační funkci, musíte zadat <xref:System.Data.Objects.ObjectQuery%601> funkce. Další informace najdete v druhém níže uvedeném příkladu.  
  
> [!NOTE]
>  Metody v <xref:System.Data.Objects.SqlClient.SqlFunctions> třídy jsou specifické pro funkce systému SQL Server. Podobně jako třídy, které zveřejňují funkce databáze může být k dispozici prostřednictvím dalších zprostředkovatelů.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá [Model prodeje společnosti AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). V příkladu provede dotazu LINQ to Entities používající <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> metody, která vrátí všechny kontakty, jejichž příjmení začíná "Ma":  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a>Příklad  
 Následující příklad používá [Model prodeje společnosti AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). V příkladu volá agregace <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> metoda přímo. Všimněte si, že <xref:System.Data.Objects.ObjectQuery%601> předaný funkci, která umožňuje volá se, aniž by byly součástí dotazu LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Viz také  
 [Volání funkcí v dotazech LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Dotazy v technologii LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
