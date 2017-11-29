---
title: "Postupy: vytvoření služby Data pomocí zdroje dat ADO.NET Entity Framework (služby WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d69a3cf60b60806085a9bb7ae292cc88ba99871e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="af4cb-102">Postupy: vytvoření služby Data pomocí zdroje dat ADO.NET Entity Framework (služby WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="af4cb-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="af4cb-103">zpřístupní entity data jako datové služby.</span><span class="sxs-lookup"><span data-stu-id="af4cb-103"> exposes entity data as a data service.</span></span> <span data-ttu-id="af4cb-104">Tato data entity zajišťuje [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Pokud zdroj dat je relační databáze.</span><span class="sxs-lookup"><span data-stu-id="af4cb-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="af4cb-105">Toto téma ukazuje, jak vytvořit [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]– na základě datového modelu v [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] webovou aplikaci, která je založena na existující databázi a použít tento datový model pro vytvoření nové datové služby.</span><span class="sxs-lookup"><span data-stu-id="af4cb-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web application that is based on an existing database and use this data model to create a new data service.</span></span>  
  
 <span data-ttu-id="af4cb-106">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Také poskytuje nástroj pro příkazový řádek, který může vytvořit [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] modelu mimo [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] projektu.</span><span class="sxs-lookup"><span data-stu-id="af4cb-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] project.</span></span> <span data-ttu-id="af4cb-107">Další informace najdete v tématu [postupy: použití EdmGen.exe pro generování modelu a mapování soubory](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="af4cb-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="af4cb-108">Chcete-li přidat model Entity Framework, který je založen na existující databázi a stávající webovou aplikaci</span><span class="sxs-lookup"><span data-stu-id="af4cb-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>  
  
1.  <span data-ttu-id="af4cb-109">Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-109">On the **Project** menu, click **Add new item**.</span></span>  
  
2.  <span data-ttu-id="af4cb-110">V **šablony** podokně klikněte na tlačítko **Data** kategorie a potom vyberte **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="af4cb-111">Zadejte název modelu a potom klikněte na **přidat**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-111">Type the model name and then click **Add**.</span></span>  
  
     <span data-ttu-id="af4cb-112">Na první stránku [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] průvodce se zobrazí.</span><span class="sxs-lookup"><span data-stu-id="af4cb-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>  
  
4.  <span data-ttu-id="af4cb-113">V **zvolte obsah modelu** dialogové okno, vyberte **generování z databáze**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="af4cb-114">Pak klikněte na tlačítko **Další**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-114">Then click **Next**.</span></span>  
  
5.  <span data-ttu-id="af4cb-115">Klikněte **nové připojení** tlačítko.</span><span class="sxs-lookup"><span data-stu-id="af4cb-115">Click the **New Connection** button.</span></span>  
  
6.  <span data-ttu-id="af4cb-116">V **vlastnosti připojení** dialogové okno, zadejte název serveru, vyberte metodu ověřování, zadejte název databáze a pak klikněte na tlačítko **OK**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="af4cb-117">**Vybrat datové připojení**dialogové okno s se aktualizuje se nastavení připojení k databázi.</span><span class="sxs-lookup"><span data-stu-id="af4cb-117">The **Choose Your Data Connection**s dialog box is updated with your database connection settings.</span></span>  
  
7.  <span data-ttu-id="af4cb-118">Ujistěte se, že **uložit nastavení připojení entity v souboru App.Config jako:** je zaškrtnuté políčko.</span><span class="sxs-lookup"><span data-stu-id="af4cb-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="af4cb-119">Pak klikněte na tlačítko **Další**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-119">Then click **Next**.</span></span>  
  
8.  <span data-ttu-id="af4cb-120">V **zvolte si databázové objekty** dialogové okno, vyberte všechny databáze objekty, že chcete vystavit v rámci služby data.</span><span class="sxs-lookup"><span data-stu-id="af4cb-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af4cb-121">Objektů obsažených v datovém modelu se službou data nezobrazí automaticky.</span><span class="sxs-lookup"><span data-stu-id="af4cb-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="af4cb-122">Se musí být explicitně vystavené samotné služby.</span><span class="sxs-lookup"><span data-stu-id="af4cb-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="af4cb-123">Další informace najdete v tématu [konfigurace službu Data](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="af4cb-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
9. <span data-ttu-id="af4cb-124">Klikněte na tlačítko **Dokončit** dokončete průvodce.</span><span class="sxs-lookup"><span data-stu-id="af4cb-124">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="af4cb-125">Tím se vytvoří výchozí datový model založena na konkrétní databázi.</span><span class="sxs-lookup"><span data-stu-id="af4cb-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="af4cb-126">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Umožňuje přizpůsobit datový model.</span><span class="sxs-lookup"><span data-stu-id="af4cb-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="af4cb-127">Další informace najdete v tématu [úlohy](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span><span class="sxs-lookup"><span data-stu-id="af4cb-127">For more information, see [Tasks](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span></span>  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="af4cb-128">Chcete-li vytvořit službu data pomocí nového datového modelu</span><span class="sxs-lookup"><span data-stu-id="af4cb-128">To create the data service by using the new data model</span></span>  
  
1.  <span data-ttu-id="af4cb-129">V [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], otevřete soubor EDMX, který představuje datový model.</span><span class="sxs-lookup"><span data-stu-id="af4cb-129">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the .edmx file that represents the data model.</span></span>  
  
2.  <span data-ttu-id="af4cb-130">V **prohlížeče modelu**, klikněte pravým tlačítkem na model, klikněte na **vlastnosti**a poznamenejte si název kontejneru entit.</span><span class="sxs-lookup"><span data-stu-id="af4cb-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>  
  
3.  <span data-ttu-id="af4cb-131">V **Průzkumníku řešení**, klikněte pravým tlačítkem na název vaší [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] projektu a pak klikněte na **přidat novou položku**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
4.  <span data-ttu-id="af4cb-132">V **přidat novou položku** dialogové okno, vyberte **služby WCF Data Service**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-132">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
5.  <span data-ttu-id="af4cb-133">Zadejte název pro službu a pak klikněte na tlačítko **OK**.</span><span class="sxs-lookup"><span data-stu-id="af4cb-133">Supply a name for the service, and then click **OK**.</span></span>  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="af4cb-134">vytvoří soubory značek a kódu XML pro novou službu.</span><span class="sxs-lookup"><span data-stu-id="af4cb-134"> creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="af4cb-135">Ve výchozím nastavení otevře se okno editoru kódu.</span><span class="sxs-lookup"><span data-stu-id="af4cb-135">By default, the code-editor window opens.</span></span>  
  
6.  <span data-ttu-id="af4cb-136">V kódu pro službu data, nahraďte komentář `/* TODO: put your data source class name here */` v definici třídy, která definuje službu datového typu, který dědí z <xref:System.Data.Objects.ObjectContext> třídy a který je kontejneru entit datového modelu, který byl uvedeným v kroku 2.</span><span class="sxs-lookup"><span data-stu-id="af4cb-136">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>  
  
7.  <span data-ttu-id="af4cb-137">V kódu pro službu data povolte autorizovaným klientům přístup k sad entit, že data služby vystavuje.</span><span class="sxs-lookup"><span data-stu-id="af4cb-137">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="af4cb-138">Další informace najdete v tématu [vytváření službu Data](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="af4cb-138">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
8.  <span data-ttu-id="af4cb-139">Chcete-li otestovat službu Northwind.svc data pomocí webového prohlížeče, postupujte podle pokynů v tématu [přístupu ke službě z webového prohlížeče](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="af4cb-139">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af4cb-140">Viz také</span><span class="sxs-lookup"><span data-stu-id="af4cb-140">See Also</span></span>  
 [<span data-ttu-id="af4cb-141">Definování datových služeb WCF</span><span class="sxs-lookup"><span data-stu-id="af4cb-141">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [<span data-ttu-id="af4cb-142">Zprostředkovatelé dat služby</span><span class="sxs-lookup"><span data-stu-id="af4cb-142">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="af4cb-143">Postupy: vytvoření služby Data pomocí poskytovatele reflexe</span><span class="sxs-lookup"><span data-stu-id="af4cb-143">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [<span data-ttu-id="af4cb-144">Postupy: vytvoření služby dat pomocí LINQ ke zdroji dat SQL</span><span class="sxs-lookup"><span data-stu-id="af4cb-144">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)