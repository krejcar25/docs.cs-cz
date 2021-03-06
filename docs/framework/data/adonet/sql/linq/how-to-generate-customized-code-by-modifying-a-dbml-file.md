---
title: "Postupy: generování přizpůsobených kódu úpravou souboru DBML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c9a2b382c84548d3226fe68531961e0f53033e7d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Postupy: generování přizpůsobených kódu úpravou souboru DBML
Můžete vygenerovat [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] nebo zdrojového kódu C# ze souboru metadat databáze markup language (dbml). Tento přístup poskytuje možnost přizpůsobit výchozí soubor DBML před generováním mapování kódu aplikace. Toto je pokročilá funkce.  
  
 Takto vypadají kroky v tomto procesu:  
  
1.  Generování souboru DBML.  
  
2.  K úpravě souboru DBML použijte editor. Všimněte si, že soubor DBML musíte ověřit proti souboru schématu definice (XSD) pro [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soubory dbml. Další informace najdete v tématu [generování kódu v technologii LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
3.  Vygenerovat [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] nebo zdrojového kódu C#.  
  
 Následující příklady pomocí nástroje příkazového řádku na SQLMetal. Další informace najdete v tématu [SqlMetal.exe (nástroj pro vytváření kódu)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Příklad  
 Následující kód vytvoří soubor DBML z ukázková databáze Northwind. Jako zdroj pro metadata databáze můžete použít název databáze nebo název souboru MDF.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Příklad  
 Následující kód vytvoří [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] nebo C# souboru zdrojového kódu ze souboru DBML.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>Viz také  
 [Generování kódu v LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [SqlMetal.exe (nástroj pro vytváření kódu)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [Vytvoření objektového modelu](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
