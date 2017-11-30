---
title: "Obnovit WorkflowHostingEndpoint záložek"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc3c92245a641b42b0357f9c6dd536dccacd6496
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="4a2d4-102">Obnovit WorkflowHostingEndpoint záložek</span><span class="sxs-lookup"><span data-stu-id="4a2d4-102">WorkflowHostingEndpoint Resume Bookmark</span></span>
<span data-ttu-id="4a2d4-103">Tento příklad ukazuje, jak <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> lze použít s <xref:System.ServiceModel.Activities.WorkflowServiceHost> k vytvoření instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4a2d4-104">Demonstruje</span><span class="sxs-lookup"><span data-stu-id="4a2d4-104">Demonstrates</span></span>  
 <span data-ttu-id="4a2d4-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="4a2d4-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="4a2d4-106">Diskusní</span><span class="sxs-lookup"><span data-stu-id="4a2d4-106">Discussion</span></span>  
 <span data-ttu-id="4a2d4-107">V tomto příkladu <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> k vytvoření instance pracovního postupu hostované pomocí <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="4a2d4-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>je bod rozšiřitelnosti pro <xref:System.ServiceModel.Activities.WorkflowServiceHost> které lze použít v následujících scénářích:</span><span class="sxs-lookup"><span data-stu-id="4a2d4-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="4a2d4-109">Vytvoření nové instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-109">Creating new workflow instances.</span></span>  
  
-   <span data-ttu-id="4a2d4-110">Záložky na instanci pracovního postupu obnovení hostované v <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-110">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="4a2d4-111">Ukázka koncového bodu, který je součástí zpřístupní kontrakt, který obsahuje operace vytvoření pracovního postupu a vrátíte se ID instance nebo pro vytvoření instance s konkrétním ID.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="4a2d4-112">Vytvoří ukázkovou aplikaci konzoly <xref:System.ServiceModel.Activities.WorkflowServiceHost> instanci s definicí základní pracovní postup a přidá `CreationEndpoint` na hostitele.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="4a2d4-113">Potom zavolá `Create` operace na koncový bod pro vytvoření nové instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4a2d4-114">Pokud chcete nastavit, sestavit a spustit ukázku</span><span class="sxs-lookup"><span data-stu-id="4a2d4-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4a2d4-115">Sestavte řešení.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-115">Build the solution.</span></span>  
  
2.  <span data-ttu-id="4a2d4-116">Spusťte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-116">Run the application.</span></span> <span data-ttu-id="4a2d4-117">`CreationEndpoint` Konzola zobrazí zprávu, která zahrnuje instance ID při vytvoření instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="4a2d4-118">Zpráva "Hello, World!"</span><span class="sxs-lookup"><span data-stu-id="4a2d4-118">The message "Hello World!"</span></span> <span data-ttu-id="4a2d4-119">je vytištěna v tomto pracovním postupu na úspěšné obnovení záložky.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-119">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4a2d4-120">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4a2d4-121">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="4a2d4-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4a2d4-122">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4a2d4-123">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="4a2d4-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`