---
title: "Práce s Data Definition Language"
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
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d65fb17796339f38be59b64e550d7ec77336083d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="f0b4b-102">Práce s Data Definition Language</span><span class="sxs-lookup"><span data-stu-id="f0b4b-102">Working with Data Definition Language</span></span>
<span data-ttu-id="f0b4b-103">Od verze [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] verze 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] podporuje jazyk definice dat (DDL).</span><span class="sxs-lookup"><span data-stu-id="f0b4b-103">Starting with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="f0b4b-104">To vám umožňuje vytvořit nebo odstranit instanci databáze na základě připojovací řetězec a metadata modelu úložiště (SSDL).</span><span class="sxs-lookup"><span data-stu-id="f0b4b-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="f0b4b-105">Následující metody na <xref:System.Data.Objects.ObjectContext> pomůže provést následující připojovací řetězec a obsah SSDL: vytvoření nebo odstranění databáze, zkontrolujte, zda databáze existuje a zobrazit generovaného skriptu DDL:</span><span class="sxs-lookup"><span data-stu-id="f0b4b-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="f0b4b-106">Provádění příkazů DDL předpokládá dostatečná oprávnění.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="f0b4b-107">Metody dříve uvedených delegovat většinu práce na základní zprostředkovatel dat ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="f0b4b-108">Je zodpovědností poskytovatele pro zajištění souladu s konvencemi použitými pro dotazování na zásady vytváření názvů sloužící ke generování databázové objekty a aktualizace.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="f0b4b-109">Následující příklad ukazuje, jak vygenerovat databázi založenou na stávající modelu.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="f0b4b-110">Také přidá nový objekt entity do kontextu objektu a pak ji uloží je do databáze.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f0b4b-111">Procedury</span><span class="sxs-lookup"><span data-stu-id="f0b4b-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="f0b4b-112">Chcete-li definovat databázi založenou na stávající modelu</span><span class="sxs-lookup"><span data-stu-id="f0b4b-112">To define a database based on the existing model</span></span>  
  
1.  <span data-ttu-id="f0b4b-113">Vytvořte konzolovou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-113">Create a console application.</span></span>  
  
2.  <span data-ttu-id="f0b4b-114">Přidání existujícího modelu do aplikace.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-114">Add an existing model to your application.</span></span>  
  
    1.  <span data-ttu-id="f0b4b-115">Přidat prázdný model s názvem `SchoolModel`.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="f0b4b-116">Pokud chcete vytvořit prázdný model, přečtěte si téma [postup: vytvoření nové .edmx souboru](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2) tématu.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-116">To create an empty model, see the [How to: Create a New .edmx File](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2) topic.</span></span>  
  
     <span data-ttu-id="f0b4b-117">Soubor SchoolModel.edmx je přidán do projektu.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1.  <span data-ttu-id="f0b4b-118">Zkopírujte koncepční, úložiště a mapování obsahu pro model školní ze [školní modelu](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) tématu.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) topic.</span></span>  
  
    2.  <span data-ttu-id="f0b4b-119">Otevřete soubor SchoolModel.edmx a vložte obsah v rámci `edmx:Runtime` značky.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3.  <span data-ttu-id="f0b4b-120">Přidejte následující kód do hlavní funkce.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-120">Add the following code to your main function.</span></span> <span data-ttu-id="f0b4b-121">Kód inicializuje připojovací řetězec k databázovému serveru, zobrazení skriptu DDL vytvoří databázi, přidá novou entitu do kontextu a uloží změny do databáze.</span><span class="sxs-lookup"><span data-stu-id="f0b4b-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]