---
title: "Obvyklé kroky pro používání technologie LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3aedef610d8ad3f743b346a46059b15d917cf7ca
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/17/2018
---
# <a name="typical-steps-for-using-linq-to-sql"></a>Obvyklé kroky pro používání technologie LINQ to SQL
K implementaci [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aplikace, můžete podle kroků popsaných později v tomto tématu. Všimněte si, že mnoho kroků jsou volitelné. Je velmi možné, že můžete použít objektový model ve svém výchozím stavu.  
  
 Opravdu rychlý start a použít [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] vytvoření objektový model a psaní své dotazy.  
  
## <a name="creating-the-object-model"></a>Vytváření objektový Model  
 Prvním krokem je vytvoření objektový model z metadat stávající relační databáze. Objektový model představuje databázi podle programovacího jazyka od vývojářů. Další informace najdete v tématu [technologii LINQ to SQL objektový Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
### <a name="1-select-a-tool-to-create-the-model"></a>1. Vyberte nástroj k vytváření modelu.  
 Tři nástroje jsou k dispozici pro vytvoření modelu.  
  
-   Na[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]  
  
     Tento návrhář poskytuje bohaté uživatelské rozhraní pro vytvoření objektu modelu z existující databáze. Tento nástroj je součástí [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] IDE a je nejvhodnější pro malé a střední databáze.  
  
-   Nástroj pro generování kódu SQLMetal  
  
     Tento nástroj příkazového řádku poskytuje sadu možností z mírně liší [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]. Modelování velké databáze se nejlépe provádí pomocí tohoto nástroje. Další informace najdete v tématu [SqlMetal.exe (nástroj pro vytváření kódu)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
-   Editor kódu  
  
     Můžete napsat vlastní kód pomocí [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] editor kódu nebo jiný editor. Nedoporučujeme tento přístup, což může být náchylná k chybám, pokud máte existující databázi a můžete použít buď [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] nebo na SQLMetal nástroj. Editor kódu však může být vhodné upřesnění nebo úprava kód, který jste již vygenerovali pomocí jiných nástrojů. Další informace najdete v tématu [postupy: přizpůsobení tříd entit pomocí editoru kódu](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md).  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a>2. Vyberte typ kód, který chcete vygenerovat.  
  
-   C# nebo [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] souboru zdrojového kódu pro mapování na základě atributů.  
  
     Pak zahrňte tento soubor kódu vaší [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] projektu. Další informace najdete v tématu [na základě atributů mapování](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
-   Soubor XML pro externí mapování.  
  
     Když použijete tuto metodu, můžete zachovat metadata mapování z kódu aplikace. Další informace najdete v tématu [externí mapování](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
    > [!NOTE]
    >  [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] Nepodporuje generování externí mapování souborů. Musíte použít nástroj SQLMetal k implementací této funkce.  
  
-   Souboru DBML, které lze upravit před vygenerováním souboru konečné kódu.  
  
     Toto je pokročilá funkce.  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a>3. Upřesněte souboru kódu tak, aby odrážela potřebám vaší aplikace.  
 Pro tento účel můžete použít buď [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] nebo editoru kódu.  
  
## <a name="using-the-object-model"></a>Pomocí objektu modelu  
 Následující obrázek znázorňuje vztahy mezi na vývojáře a data ve scénáři dvouvrstvá. Další scénáře, najdete v části [N-vrstvá a vzdálené aplikace s dotazy LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md).  
  
 ![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")  
  
 Teď, když máte objektový model, popisují informace žádosti a pracovat s daty v rámci tohoto modelu. Domníváte, že z hlediska objektů a vlastností v objektu modelu a není z hlediska řádků a sloupců databáze. Není pracují přímo s databází.  
  
 Pokud dáte pokyn [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] buď spustit dotaz, který je popsán nebo volání `SubmitChanges()` na data, která můžete mít s nimi manipulovat, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] komunikuje s databází v jazyce databáze.  
  
 Následující představuje obvyklé kroky pro použití v objektovém modelu, který jste vytvořili.  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a>1. Vytváření dotazů k načtení informací z databáze.  
 Další informace najdete v tématu [dotazu koncepty](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md) a [příklady dotazu](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md).  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a>2. Přepsat výchozí chování pro příkaz Insert, Update a odstranit.  
 Tento krok je volitelný. Další informace najdete v tématu [přizpůsobení vložit, aktualizovat a odstranit operace](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a>3. Nastavte požadované možnosti pro zjišťování a sestavy konfliktů souběžnosti.  
 Můžete nechat modelu s jeho výchozí hodnoty pro zpracování konfliktů souběžnosti, nebo můžete změnit tak, aby odpovídal vaše záměry. Další informace najdete v tématu [postup: Určete který členové jsou testovány souběžnosti konflikty](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) a [postup: zadejte při souběžnosti jsou výjimky vyvolány](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
### <a name="4-establish-an-inheritance-hierarchy"></a>4. Vytvoření hierarchie dědičnosti.  
 Tento krok je volitelný. Další informace najdete v tématu [dědičnosti podporu](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
### <a name="5-provide-an-appropriate-user-interface"></a>5. Zadejte odpovídající uživatelské rozhraní.  
 Tento krok je volitelný a závisí na tom, jak bude vaše aplikace používána.  
  
### <a name="6-debug-and-test-your-application"></a>6. Ladění a testování vaší aplikace.  
 Další informace najdete v tématu [podpora ladění](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).  
  
## <a name="see-also"></a>Viz také  
 [Začínáme](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 [Vytvoření objektového modelu](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [Uložené procedury](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
