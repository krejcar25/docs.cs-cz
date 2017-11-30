---
title: "Načítání a upravovat Data v technologii ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 35de20b1cb35fdcd87a653f1ac202c01d345c317
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="deb0e-102">Načítání a upravovat Data v technologii ADO.NET</span><span class="sxs-lookup"><span data-stu-id="deb0e-102">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="deb0e-103">Primární funkce jakékoli aplikace, databáze je připojení ke zdroji dat a načítání dat, který ji obsahuje.</span><span class="sxs-lookup"><span data-stu-id="deb0e-103">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="deb0e-104">Zprostředkovatele dat .NET Framework technologie ADO.NET sloužit jako most mezi aplikace a zdroj dat, což umožňuje provést příkazy také o načtení dat pomocí **DataReader –** nebo **DataAdapter** .</span><span class="sxs-lookup"><span data-stu-id="deb0e-104">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="deb0e-105">Klíčové funkce jakékoli aplikace, databáze, je schopnost aktualizovat data, která je uložená v databázi.</span><span class="sxs-lookup"><span data-stu-id="deb0e-105">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="deb0e-106">V technologii ADO.NET, aktualizace dat zahrnuje použití **DataAdapter** a <xref:System.Data.DataSet>, a **příkaz** objekty; a může zahrnovat také pomocí transakce.</span><span class="sxs-lookup"><span data-stu-id="deb0e-106">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="deb0e-107">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="deb0e-107">In This Section</span></span>  
 [<span data-ttu-id="deb0e-108">Připojení ke zdroji dat</span><span class="sxs-lookup"><span data-stu-id="deb0e-108">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 <span data-ttu-id="deb0e-109">Popisuje, jak vytvořit připojení ke zdroji dat a jak pracovat s události připojení.</span><span class="sxs-lookup"><span data-stu-id="deb0e-109">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="deb0e-110">Připojovací řetězce</span><span class="sxs-lookup"><span data-stu-id="deb0e-110">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 <span data-ttu-id="deb0e-111">Obsahuje témata s popisem různé aspekty použití řetězců připojení, včetně klíčová slova řetězec připojení, bezpečnostní údaje a ukládání a načítání je.</span><span class="sxs-lookup"><span data-stu-id="deb0e-111">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="deb0e-112">Sdružování připojení</span><span class="sxs-lookup"><span data-stu-id="deb0e-112">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 <span data-ttu-id="deb0e-113">Popisuje sdružování připojení pro poskytovatele dat .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="deb0e-113">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="deb0e-114">Příkazy a parametry</span><span class="sxs-lookup"><span data-stu-id="deb0e-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 <span data-ttu-id="deb0e-115">Obsahuje témata s popisem vytváření příkazů a příkaz počítačů, nakonfigurujte parametry a postup provedení příkazu k načtení a upravovat data.</span><span class="sxs-lookup"><span data-stu-id="deb0e-115">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="deb0e-116">DataAdapters a DataReaders</span><span class="sxs-lookup"><span data-stu-id="deb0e-116">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 <span data-ttu-id="deb0e-117">Obsahuje témata s popisem DataReaders, DataAdapters, parametry, zpracování událostí DataAdapter a provádění dávkových operací.</span><span class="sxs-lookup"><span data-stu-id="deb0e-117">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="deb0e-118">Transakce a souběžnost</span><span class="sxs-lookup"><span data-stu-id="deb0e-118">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 <span data-ttu-id="deb0e-119">Obsahuje témata popisující, jak provádět místní transakce, distribuovaných transakcí a pracovat s optimistickou metodu souběžného.</span><span class="sxs-lookup"><span data-stu-id="deb0e-119">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="deb0e-120">Načítání Identity nebo hodnoty automatické číslování</span><span class="sxs-lookup"><span data-stu-id="deb0e-120">Retrieving Identity or Autonumber Values</span></span>](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="deb0e-121">Poskytuje příklad mapování hodnoty vygenerované **identity** sloupec v [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] tabulky, nebo **automatické číslování** pole v tabulce Microsoft Access ke sloupci vloženého řádku v tabulce.</span><span class="sxs-lookup"><span data-stu-id="deb0e-121">Provides an example of mapping the values generated for an **identity** column in a [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="deb0e-122">Popisuje slučovat hodnoty identity v `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="deb0e-122">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="deb0e-123">Načítání binární Data</span><span class="sxs-lookup"><span data-stu-id="deb0e-123">Retrieving Binary Data</span></span>](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 <span data-ttu-id="deb0e-124">Popisuje, jak získat binární data nebo velkého množství dat struktur pomocí `CommandBehavior`.`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="deb0e-124">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="deb0e-125">Chcete-li změnit výchozí chování `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="deb0e-125">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="deb0e-126">Úprava dat pomocí uložené procedury</span><span class="sxs-lookup"><span data-stu-id="deb0e-126">Modifying Data with Stored Procedures</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="deb0e-127">Popisuje způsob používání vstupních parametrů uložené procedury a výstupní parametry vložit řádek v databázi, vrátí novou hodnotu identity.</span><span class="sxs-lookup"><span data-stu-id="deb0e-127">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="deb0e-128">Načítání informací o schématu databáze</span><span class="sxs-lookup"><span data-stu-id="deb0e-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 <span data-ttu-id="deb0e-129">Popisuje, jak získat dostupné databáze nebo katalogů, tabulky a zobrazení v databázi, omezení, která platí pro tabulky a další informace o schématu ze zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="deb0e-129">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="deb0e-130">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="deb0e-130">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="deb0e-131">Popisuje model objektu pro vytváření zprostředkovatele a ukazuje, jak používat základní třídy v `System.Data.Common` oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="deb0e-131">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="deb0e-132">Data trasování v technologii ADO.NET</span><span class="sxs-lookup"><span data-stu-id="deb0e-132">Data Tracing in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-tracing.md)  
 <span data-ttu-id="deb0e-133">Popisuje, jak technologie ADO.NET poskytuje funkce integrované data trasování.</span><span class="sxs-lookup"><span data-stu-id="deb0e-133">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="deb0e-134">Čítače výkonu</span><span class="sxs-lookup"><span data-stu-id="deb0e-134">Performance Counters</span></span>](../../../../docs/framework/data/adonet/performance-counters.md)  
 <span data-ttu-id="deb0e-135">Popisuje čítače výkonu, které jsou k dispozici pro `SqlClient` a `OracleClient`.</span><span class="sxs-lookup"><span data-stu-id="deb0e-135">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="deb0e-136">Asynchronní programování</span><span class="sxs-lookup"><span data-stu-id="deb0e-136">Asynchronous Programming</span></span>](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 <span data-ttu-id="deb0e-137">Popisuje [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] podporu pro asynchronní programování.</span><span class="sxs-lookup"><span data-stu-id="deb0e-137">Describes [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="deb0e-138">Podpora streamování SqlClient</span><span class="sxs-lookup"><span data-stu-id="deb0e-138">SqlClient Streaming Support</span></span>](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 <span data-ttu-id="deb0e-139">Popisuje, jak psát aplikace, které data z datového proudu [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] bez nutnosti, je plně načten do paměti.</span><span class="sxs-lookup"><span data-stu-id="deb0e-139">Discusses how to write applications that stream data from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb0e-140">Viz také</span><span class="sxs-lookup"><span data-stu-id="deb0e-140">See Also</span></span>  
 [<span data-ttu-id="deb0e-141">Mapování datového typu v technologii ADO.NET</span><span class="sxs-lookup"><span data-stu-id="deb0e-141">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="deb0e-142">Datové sady, DataTables a DataView</span><span class="sxs-lookup"><span data-stu-id="deb0e-142">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="deb0e-143">Zabezpečení aplikací ADO.NET</span><span class="sxs-lookup"><span data-stu-id="deb0e-143">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="deb0e-144">SQL Server a ADO.NET</span><span class="sxs-lookup"><span data-stu-id="deb0e-144">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="deb0e-145">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="deb0e-145">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)