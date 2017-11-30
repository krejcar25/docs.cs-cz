---
title: "Postupy: zpřístupnění modelu a soubory mapování vložené prostředky"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 98fb3ada369279a34ed08110644aabcbbe72a501
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="a6acd-102">Postupy: zpřístupnění modelu a soubory mapování vložené prostředky</span><span class="sxs-lookup"><span data-stu-id="a6acd-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="a6acd-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Umožňuje nasadit model a mapování soubory jako vložené prostředky aplikace.</span><span class="sxs-lookup"><span data-stu-id="a6acd-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="a6acd-104">Toto sestavení s vložený model a mapování soubory musí být ve stejné doméně aplikace jako připojení entity načíst.</span><span class="sxs-lookup"><span data-stu-id="a6acd-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="a6acd-105">Další informace najdete v tématu [připojovací řetězce](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="a6acd-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="a6acd-106">Ve výchozím nastavení [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] nástroje pro vložení modelu a mapování souborů.</span><span class="sxs-lookup"><span data-stu-id="a6acd-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="a6acd-107">Když definujete ručně modelu a mapování souborů, pomocí tohoto postupu zkontrolujte, že soubory jsou nasazeny jako vložené prostředky společně s [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="a6acd-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6acd-108">Pokud chcete zachovat vložené prostředky, musíte tento postup zopakovat vždy, když jsou upraveny modelu a mapování souborů.</span><span class="sxs-lookup"><span data-stu-id="a6acd-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="a6acd-109">Chcete-li vložit soubory mapování a modelu</span><span class="sxs-lookup"><span data-stu-id="a6acd-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="a6acd-110">V **Průzkumníku**, vyberte soubor koncepční (.csdl).</span><span class="sxs-lookup"><span data-stu-id="a6acd-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="a6acd-111">V **vlastnosti** podokně nastavit **akce sestavení** k **vložený prostředek**.</span><span class="sxs-lookup"><span data-stu-id="a6acd-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="a6acd-112">Opakujte kroky 1 a 2 pro soubor úložiště (ssdl) a souboru mapování (.msl).</span><span class="sxs-lookup"><span data-stu-id="a6acd-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="a6acd-113">V **Průzkumníku řešení**, poklikejte na soubor App.config a potom upravte `Metadata` parametr ve `connectionString` atributů na základě jedné z následujících formátů:</span><span class="sxs-lookup"><span data-stu-id="a6acd-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   <span data-ttu-id="a6acd-114">`Metadata=``res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="a6acd-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    -   <span data-ttu-id="a6acd-115">`Metadata=``res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="a6acd-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="a6acd-116">Další informace najdete v tématu [připojovací řetězce](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="a6acd-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6acd-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="a6acd-117">Example</span></span>  
 <span data-ttu-id="a6acd-118">Následující připojovací řetězec odkazuje vložený model a mapování souborů [Model prodeje společnosti AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="a6acd-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="a6acd-119">Tento připojovací řetězec uložený v souboru App.config projektu.</span><span class="sxs-lookup"><span data-stu-id="a6acd-119">This connection string is stored in the project's App.config file.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="a6acd-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="a6acd-120">See Also</span></span>  
 [<span data-ttu-id="a6acd-121">Mapování a modelování</span><span class="sxs-lookup"><span data-stu-id="a6acd-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="a6acd-122">Postupy: definování připojovací řetězec</span><span class="sxs-lookup"><span data-stu-id="a6acd-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)  
 [<span data-ttu-id="a6acd-123">Postupy: sestavení řetězec připojení EntityConnection</span><span class="sxs-lookup"><span data-stu-id="a6acd-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
 [<span data-ttu-id="a6acd-124">Nástroje modelu ADO.NET Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="a6acd-124">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)