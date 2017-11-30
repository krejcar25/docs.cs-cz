---
title: "Začínáme Tutorial2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9947833a11fa0b7227a11e65f3b42a91d8fe91d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="066c2-102">Kurz Začínáme</span><span class="sxs-lookup"><span data-stu-id="066c2-102">Getting Started Tutorial</span></span>
<span data-ttu-id="066c2-103">Tato část obsahuje sadu návod témata, které vám představí programování [!INCLUDE[wf](../../../includes/wf-md.md)] aplikací.</span><span class="sxs-lookup"><span data-stu-id="066c2-103">This section contains a set of walkthrough topics that introduce you to programming [!INCLUDE[wf](../../../includes/wf-md.md)] applications.</span></span> <span data-ttu-id="066c2-104">Pomocí následujících postupů v těchto tématech, vytvoříte aplikaci, která je číslo hádání hra.</span><span class="sxs-lookup"><span data-stu-id="066c2-104">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="066c2-105">První téma v tomto kurzu vás provede kroky k vytvoření vlastních aktivit, které jsou potřebné pro pracovní postup.</span><span class="sxs-lookup"><span data-stu-id="066c2-105">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="066c2-106">V druhé tématu jsou tyto aktivity několik společně s integrovanou pracovního postupu aktivit do vývojový diagram pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="066c2-106">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="066c2-107">V sekci třetí aplikace hostitele je nakonfigurována pro spuštění pracovního postupu a v posledním tématu uvádíme trvalost.</span><span class="sxs-lookup"><span data-stu-id="066c2-107">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="066c2-108">Každý krok v tomto procesu závisí na předchozí kroky, proto doporučujeme, můžete dokončit v pořadí.</span><span class="sxs-lookup"><span data-stu-id="066c2-108">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="066c2-109">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="066c2-109">In This Section</span></span>  
 [<span data-ttu-id="066c2-110">Postupy: vytvoření aktivity</span><span class="sxs-lookup"><span data-stu-id="066c2-110">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 <span data-ttu-id="066c2-111">Popisuje, jak vytvořit vlastní aktivitu, která je odvozena z <xref:System.Activities.NativeActivity%601>a jak vytvořit tuto aktivitu společně s aktivitou integrované do složených aktivit pomocí návrháře aktivit.</span><span class="sxs-lookup"><span data-stu-id="066c2-111">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="066c2-112">Postupy: vytvoření pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="066c2-112">How to: Create a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 <span data-ttu-id="066c2-113">Popisuje, jak vytvořit vývojový diagram sekvenční a pracovních postupů stav počítače pomocí předdefinované a vlastní aktivity z předchozí kurzu.</span><span class="sxs-lookup"><span data-stu-id="066c2-113">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="066c2-114">Postupy: spuštění pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="066c2-114">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)  
 <span data-ttu-id="066c2-115">Popisuje, jak vyvolat pracovní postup z prostředí hostitele, předávání dat do a z pracovního postupu a jak obnovit záložky.</span><span class="sxs-lookup"><span data-stu-id="066c2-115">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="066c2-116">Postupy: vytvoření a spuštění s dlouhým spuštěný pracovní postup</span><span class="sxs-lookup"><span data-stu-id="066c2-116">How to: Create and Run a Long Running Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="066c2-117">Popisuje postup přidání trvalost do aplikace pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="066c2-117">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="066c2-118">Postupy: vytvoření vlastní sledování účastník</span><span class="sxs-lookup"><span data-stu-id="066c2-118">How to: Create a Custom Tracking Participant</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="066c2-119">Popisuje, jak vytvořit vlastní sledování účastník a sledování profilu.</span><span class="sxs-lookup"><span data-stu-id="066c2-119">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="066c2-120">Postupy: hostování více verzí pracovní postup-souběžného</span><span class="sxs-lookup"><span data-stu-id="066c2-120">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="066c2-121">Popisuje způsob použití `WorkflowIdentity` k hostování více verzí pracovní postup-souběžného.</span><span class="sxs-lookup"><span data-stu-id="066c2-121">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="066c2-122">Postupy: aktualizovat definici spuštěná instance pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="066c2-122">How to: Update the Definition of a Running Workflow Instance</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="066c2-123">Popisuje způsob použití dynamické aktualizace k úpravě spuštěné instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="066c2-123">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="066c2-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="066c2-124">See Also</span></span>  
 [<span data-ttu-id="066c2-125">Windows Workflow Foundation programování</span><span class="sxs-lookup"><span data-stu-id="066c2-125">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)