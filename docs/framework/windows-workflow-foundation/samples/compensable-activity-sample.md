---
title: "Ukázka compensable aktivity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b8d7fb5650a8927016e0deebc07a68a8145496db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="compensable-activity-sample"></a><span data-ttu-id="034f9-102">Ukázka compensable aktivity</span><span class="sxs-lookup"><span data-stu-id="034f9-102">Compensable Activity Sample</span></span>
<span data-ttu-id="034f9-103">Tento příklad znázorňuje způsob použití `CompensableActivity` aktivity k definování práce, kterou je třeba udělat pro danou akci během normálního spouštění a práci, kterou je potřeba provést odpovídajícím způsobem této akce v případě potřeby později.</span><span class="sxs-lookup"><span data-stu-id="034f9-103">This sample demonstrates how to use the `CompensableActivity` activity to define the work to be done for a given action during normal execution and the work that is necessary to be done to compensate that action, if necessary at a later time.</span></span>  <span data-ttu-id="034f9-104">První část vzorku ukazuje, jak lze definovat compensable pracovní jednotky v [!INCLUDE[wf](../../../../includes/wf-md.md)] pomocí `CompensableActivity` aktivity a jak jsou spouštěny v spuštění úspěšné.</span><span class="sxs-lookup"><span data-stu-id="034f9-104">The first part of the sample shows how units of compensable work can be defined in [!INCLUDE[wf](../../../../includes/wf-md.md)] using a `CompensableActivity` activity and how they are executed in a successful run.</span></span>  <span data-ttu-id="034f9-105">Druhá část vzorku ukazuje, jak funkce stejné compensable pracovních jednotek automaticky postará o kompenzaci když je dosaženo neočekávané události a zrušení instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="034f9-105">The second part of the sample shows how the same units of compensable work automatically take care of compensation when an unexpected event is hit and the workflow instance is canceled.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="034f9-106">Pokud chcete nastavit, sestavit a spustit ukázku</span><span class="sxs-lookup"><span data-stu-id="034f9-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="034f9-107">Pomocí sady Visual Studio 2010, otevřete CompensableActivity.sln.</span><span class="sxs-lookup"><span data-stu-id="034f9-107">Using Visual Studio 2010, open the CompensableActivity.sln.</span></span>  
  
2.  <span data-ttu-id="034f9-108">Sestavte řešení stisknutím kombinace kláves CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="034f9-108">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="034f9-109">Spusťte aplikaci stisknutím klávesy F5.</span><span class="sxs-lookup"><span data-stu-id="034f9-109">Run the application by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="034f9-110">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="034f9-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="034f9-111">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="034f9-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="034f9-112">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="034f9-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="034f9-113">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="034f9-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`  
  
## <a name="see-also"></a><span data-ttu-id="034f9-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="034f9-114">See Also</span></span>