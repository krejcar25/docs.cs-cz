---
title: "Kanonické funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1f676c88691f0ba80ca682d720adf649ab612cfb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/17/2018
---
# <a name="canonical-functions"></a>Kanonické funkce
Tato část popisuje kanonické funkce, které jsou podporovány všechny zprostředkovateli dat a mohou být využívána všechny dotazování technologie. Kanonické funkce nelze rozšířit pomocí zprostředkovatele.  
  
 Tyto kanonické funkce bude možné přeložit funkci odpovídající zdroj dat pro zprostředkovatele. To umožňuje volání funkce vyjádřené v běžné formuláře napříč datové zdroje.  
  
 Protože tyto kanonické funkce jsou nezávislé na zdroje dat, jsou definovány argument a návratové typy kanonické funkce z hlediska typy v konceptuálním modelu. Některé zdroje dat však nemusí podporovat všechny typy v konceptuálním modelu.  
  
 Při použití kanonické funkce v [!INCLUDE[esql](../../../../../../includes/esql-md.md)] dotaz, příslušnou funkci bude volána ve zdroji dat.  
  
 Všechny kanonické funkce mít hodnotu null vstup chování a chybové stavy explicitně určena. Poskytovatelé úložiště, by měly splňovat chování, ale [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] nevynucuje toto chování.  
  
 Pro scénáře LINQ dotazy proti [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] zahrnují mapování metod modulu CLR do metod v podkladovém zdroji dat. Mapa metody CLR na kanonické funkce tak, aby konkrétní nastavena metod bude správně mapovat, bez ohledu na zdroj dat.  
  
## <a name="canonical-functions-namespace"></a>Namespace kanonické funkce  
 Obor názvů pro kanonické funkce je <xref:System.Data.Metadata.Edm>. <xref:System.Data.Metadata.Edm> Obor názvů je automaticky součástí všechny dotazy. Ale pokud je importované jiný obor názvů, který obsahuje funkce se stejným názvem jako kanonické funkce (v <xref:System.Data.Metadata.Edm> oboru názvů), je nutné zadat obor názvů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Agregační kanonické funkce](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 Popisuje agregace [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonické funkce.  
  
 [Matematické kanonické funkce](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 Popisuje matematické [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonické funkce.  
  
 [Řetězcové kanonické funkce](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 Popisuje řetězec [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonické funkce.  
  
 [Kanonické funkce pro datum a čas](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 Popisuje data a času [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonické funkce.  
  
 [Bitové kanonické funkce](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 Popisuje bitový [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonické funkce.  
  
 [Prostorové funkce](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 Popisuje Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonické funkce.  
  
 [Jiné kanonické funkce](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 Popisuje funkce není klasifikovaný bitové, datum a čas, řetězec, matematické nebo agregace.  
  
## <a name="see-also"></a>Viz také  
 [Přehled Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Reference k Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Konceptuální model v kanonickém formátu pro mapování funkcí SQL Serveru](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)  
 [Uživatelem definované funkce](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
