---
title: "Přehled pracovního postupu systému Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc44adbe-1412-49ae-81af-0298be44aae6
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f60d5a7fb0bcc1f38fda470e5f44938fc0fa011f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="windows-workflow-overview"></a><span data-ttu-id="3c017-102">Přehled pracovního postupu systému Windows</span><span class="sxs-lookup"><span data-stu-id="3c017-102">Windows Workflow Overview</span></span>
<span data-ttu-id="3c017-103">Pracovní postup je sada elementární jednotek nazývaných *aktivity* , jsou uloženy jako model, který popisuje reálného procesu.</span><span class="sxs-lookup"><span data-stu-id="3c017-103">A workflow is a set of elemental units called *activities* that are stored as a model that describes a real-world process.</span></span> <span data-ttu-id="3c017-104">Pracovní postupy zadejte označení pořadí provádění a závislé vztahy mezi částí krátké nebo dlouhotrvající práce.</span><span class="sxs-lookup"><span data-stu-id="3c017-104">Workflows provide a way of describing the order of execution and dependent relationships between pieces of short- or long-running work.</span></span> <span data-ttu-id="3c017-105">Tento pracovní projdou modelu od začátku do konce a aktivity mohou být prováděny, uživatelé nebo funkce systému.</span><span class="sxs-lookup"><span data-stu-id="3c017-105">This work passes through the model from start to finish, and activities might be executed by people or by system functions.</span></span>  
  
## <a name="workflow-run-time-engine"></a><span data-ttu-id="3c017-106">Modul runtime pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="3c017-106">Workflow Run-time Engine</span></span>  
 <span data-ttu-id="3c017-107">Všechny spuštěné instance pracovního postupu je vytvářené a udržované pomocí modul runtime v procesu, musí hostitelský proces komunikuje prostřednictvím jednoho z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="3c017-107">Every running workflow instance is created and maintained by an in-process run-time engine that the host process interacts with through one of the following:</span></span>  
  
-   <span data-ttu-id="3c017-108">A <xref:System.Activities.WorkflowInvoker>, který volá pracovní postup jako metodu.</span><span class="sxs-lookup"><span data-stu-id="3c017-108">A <xref:System.Activities.WorkflowInvoker>, which invokes the workflow like a method.</span></span>  
  
-   <span data-ttu-id="3c017-109">A <xref:System.Activities.WorkflowApplication> explicitní kontrolu nad spuštění instance jednoho pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="3c017-109">A <xref:System.Activities.WorkflowApplication> for explicit control over the execution of a single workflow instance.</span></span>  
  
-   <span data-ttu-id="3c017-110">A <xref:System.ServiceModel.WorkflowServiceHost> pro interakce na základě zpráv ve scénářích s více instancemi.</span><span class="sxs-lookup"><span data-stu-id="3c017-110">A <xref:System.ServiceModel.WorkflowServiceHost> for message-based interactions in multi-instance scenarios.</span></span>  
  
 <span data-ttu-id="3c017-111">Každá z těchto tříd zabalí na core runtime aktivity vyjádřené <xref:System.Activities.ActivityInstance> zodpovědná za spuštění aktivity.</span><span class="sxs-lookup"><span data-stu-id="3c017-111">Each of these classes wraps the core activity runtime represented as a <xref:System.Activities.ActivityInstance> responsible for activity execution.</span></span> <span data-ttu-id="3c017-112">Může být několik <xref:System.Activities.ActivityInstance> objektů v rámci současné spuštění domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="3c017-112">There can be several <xref:System.Activities.ActivityInstance> objects within an application domain running concurrently.</span></span>  
  
 <span data-ttu-id="3c017-113">Každý z předchozí interakce objektů tři hostitele je vytvořen ze stromu aktivit, které jsou označovány jako program pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="3c017-113">Each of the preceding three host interaction objects is created from a tree of activities referred to as a workflow program.</span></span> <span data-ttu-id="3c017-114">Pomocí těchto typů nebo vlastní hostitele, který zabalí <xref:System.Activities.ActivityInstance>, pracovní postupy můžete spustit v rámci libovolného procesu systému Windows včetně konzolové aplikace založené na formulářích aplikace služby systému Windows, [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] weby, a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]služby.</span><span class="sxs-lookup"><span data-stu-id="3c017-114">Using these types or a custom host that wraps <xref:System.Activities.ActivityInstance>, workflows can be executed inside any Windows process including console applications, forms-based applications, Windows Services, [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web sites, and [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]services.</span></span>  
  
 <span data-ttu-id="3c017-115">![Součásti pracovního postupu v procesu hostitele](../../../docs/framework/windows-workflow-foundation/media/44c79d1d-178b-4487-87ed-3e33015a3842.gif "44c79d1d-178b-4487-87ed-3e33015a3842")</span><span class="sxs-lookup"><span data-stu-id="3c017-115">![Workflow components in the host process](../../../docs/framework/windows-workflow-foundation/media/44c79d1d-178b-4487-87ed-3e33015a3842.gif "44c79d1d-178b-4487-87ed-3e33015a3842")</span></span>  
<span data-ttu-id="3c017-116">Součásti pracovního postupu v procesu hostitele</span><span class="sxs-lookup"><span data-stu-id="3c017-116">Workflow components in the host process</span></span>  
  
## <a name="interaction-between-workflow-components"></a><span data-ttu-id="3c017-117">Interakce mezi součástmi pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="3c017-117">Interaction between Workflow Components</span></span>  
 <span data-ttu-id="3c017-118">Následující diagram ukazuje, jak součásti pracovního postupu vzájemné interakce.</span><span class="sxs-lookup"><span data-stu-id="3c017-118">The following diagram demonstrates how workflow components interact with one another.</span></span>  
  
 <span data-ttu-id="3c017-119">![Pracovní postup interakce](../../../docs/framework/windows-workflow-foundation/media/workflowinteraction.gif "WorkflowInteraction")</span><span class="sxs-lookup"><span data-stu-id="3c017-119">![Workflow interaction](../../../docs/framework/windows-workflow-foundation/media/workflowinteraction.gif "WorkflowInteraction")</span></span>  
  
 <span data-ttu-id="3c017-120">Na předchozím obrázku <xref:System.Activities.WorkflowInvoker.Invoke%2A> metodu <xref:System.Activities.WorkflowInvoker> třída se používá k vyvolání několik instancí pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="3c017-120">In the preceding diagram, the <xref:System.Activities.WorkflowInvoker.Invoke%2A> method of the <xref:System.Activities.WorkflowInvoker> class is used to invoke several workflow instances.</span></span> <span data-ttu-id="3c017-121"><xref:System.Activities.WorkflowInvoker>slouží pro prosté pracovní postupy, které nepotřebují správy z hostitele; pracovní postupy, které je třeba Správa z hostitele (například <xref:System.Activities.Bookmark> obnovení) je třeba spustit pomocí <xref:System.Activities.WorkflowApplication.Run%2A> místo.</span><span class="sxs-lookup"><span data-stu-id="3c017-121"><xref:System.Activities.WorkflowInvoker> is used for lightweight workflows that do not need management from the host; workflows that need management from the host (such as <xref:System.Activities.Bookmark> resumption) must be executed using <xref:System.Activities.WorkflowApplication.Run%2A> instead.</span></span> <span data-ttu-id="3c017-122">Není potřeba čekat na jednu instanci pracovního postupu k dokončení před vyvoláním modul runtime podporuje současně spuštěno více instancí pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="3c017-122">It isn’t required to wait for one workflow instance to complete before invoking another; the runtime engine supports running multiple workflow instances simultaneously.</span></span>  <span data-ttu-id="3c017-123">Vyvolá pracovní postupy jsou následující:</span><span class="sxs-lookup"><span data-stu-id="3c017-123">The workflows invoked are as follows:</span></span>  
  
-   <span data-ttu-id="3c017-124">A <xref:System.Activities.Statements.Sequence> aktivity, která obsahuje <xref:System.Activities.Statements.WriteLine> podřízené aktivity.</span><span class="sxs-lookup"><span data-stu-id="3c017-124">A <xref:System.Activities.Statements.Sequence> activity that contains a <xref:System.Activities.Statements.WriteLine> child activity.</span></span> <span data-ttu-id="3c017-125">A <xref:System.Activities.Variable> nadřazené aktivity je vázána na <xref:System.Activities.InArgument> podřízené aktivity.</span><span class="sxs-lookup"><span data-stu-id="3c017-125">A <xref:System.Activities.Variable> of the parent activity is bound to an <xref:System.Activities.InArgument> of the child activity.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="3c017-126">na proměnné, argumentů a vazbu, najdete v části [proměnné a argumenty](../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="3c017-126"> on variables, arguments, and binding, see [Variables and Arguments](../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
-   <span data-ttu-id="3c017-127">Vlastní aktivity volá `ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="3c017-127">A custom activity called `ReadLine`.</span></span> <span data-ttu-id="3c017-128"><xref:System.Activities.OutArgument> z `ReadLine` aktivity se vrátí do volající <xref:System.Activities.WorkflowInvoker.Invoke%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="3c017-128">An <xref:System.Activities.OutArgument> of the `ReadLine` activity is returned to the calling <xref:System.Activities.WorkflowInvoker.Invoke%2A> method.</span></span>  
  
-   <span data-ttu-id="3c017-129">Vlastní aktivity, která je odvozena z <xref:System.Activities.CodeActivity> abstraktní třídy.</span><span class="sxs-lookup"><span data-stu-id="3c017-129">A custom activity that derives from the <xref:System.Activities.CodeActivity> abstract class.</span></span> <span data-ttu-id="3c017-130"><xref:System.Activities.CodeActivity> Můžete přístup k funkcím runtime (například sledování a vlastnosti) pomocí <xref:System.Activities.CodeActivityContext> která je k dispozici jako parametr funkce <xref:System.Activities.CodeActivity.Execute%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="3c017-130">The <xref:System.Activities.CodeActivity> can access run-time features (such as tracking and properties) using the <xref:System.Activities.CodeActivityContext> that is available as a parameter of the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="3c017-131">Tyto funkce běhové najdete [pracovního postupu pro sledování a trasování](../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) a [vlastnosti spuštění pracovního postupu](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3c017-131"> these run-time features, see [Workflow Tracking and Tracing](../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Workflow Execution Properties](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c017-132">Viz také</span><span class="sxs-lookup"><span data-stu-id="3c017-132">See Also</span></span>  
 [<span data-ttu-id="3c017-133">BizTalk Server 2006 nebo WF? Volba správného pracovního postupu nástroje pro svůj projekt</span><span class="sxs-lookup"><span data-stu-id="3c017-133">BizTalk Server 2006 or WF? Choosing the Right Workflow Tool for Your Project</span></span>](http://go.microsoft.com/fwlink/?LinkId=154901)