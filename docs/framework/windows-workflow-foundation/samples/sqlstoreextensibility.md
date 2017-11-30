---
title: SQLStoreExtensibility
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 111e7aa4164d9fc811ebe3f5efb196df77d1ded0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="sqlstoreextensibility"></a><span data-ttu-id="73f92-102">SQLStoreExtensibility</span><span class="sxs-lookup"><span data-stu-id="73f92-102">SQLStoreExtensibility</span></span>
<span data-ttu-id="73f92-103">Tento příklad znázorňuje použití a konfiguraci propagovaných vlastností v úložišti instance SQL pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="73f92-103">This sample demonstrates the use and configuration of promoted properties in the SQL workflow instance store.</span></span> <span data-ttu-id="73f92-104">Ukládání instance pracovního postupu SQL je na základě SQL implementace instance úložiště.</span><span class="sxs-lookup"><span data-stu-id="73f92-104">The SQL workflow instance store is a SQL-based implementation of an instance store.</span></span> <span data-ttu-id="73f92-105">Umožňuje instanci pro uložení stavu a načtení stavu do a z databáze systému SQL Server nebo SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="73f92-105">It allows an instance to save its state and load its state to and from a SQL Server or SQL Server Express database.</span></span> <span data-ttu-id="73f92-106">Funkce rozšiřitelnost úložiště umožňuje uživateli definovat vlastnosti, které jsou uložené v úložišti instance.</span><span class="sxs-lookup"><span data-stu-id="73f92-106">The store extensibility feature allows the user to define properties that are stored in the instance store.</span></span> <span data-ttu-id="73f92-107">Tyto vlastnosti jsou zobrazeny v zobrazení propagovaných vlastnosti, která umožňuje uživatelům dotazu pro ně.</span><span class="sxs-lookup"><span data-stu-id="73f92-107">These properties are displayed in a promoted properties view that allows the user to query for them.</span></span>  
  
 <span data-ttu-id="73f92-108">Tato ukázka se skládá z pracovního postupu, který implementuje počítání služby.</span><span class="sxs-lookup"><span data-stu-id="73f92-108">This sample consists of a workflow that implements a counting service.</span></span> <span data-ttu-id="73f92-109">Po zavolání metody spuštění služby, služby počty od 0 do 29.</span><span class="sxs-lookup"><span data-stu-id="73f92-109">Once the service's start method is invoked, the service counts from 0 to 29.</span></span> <span data-ttu-id="73f92-110">Hodnota čítače se zvýší každé 2 sekundy.</span><span class="sxs-lookup"><span data-stu-id="73f92-110">The counter is incremented once every 2 seconds.</span></span> <span data-ttu-id="73f92-111">Po každé počet pracovního postupu trvá.</span><span class="sxs-lookup"><span data-stu-id="73f92-111">After each count, the workflow persists.</span></span> <span data-ttu-id="73f92-112">Aktuální hodnota čítače je uložen v úložišti instance jako propagovaných vlastnost.</span><span class="sxs-lookup"><span data-stu-id="73f92-112">The current counter value is stored in the instance store as a promoted property.</span></span>  
  
 <span data-ttu-id="73f92-113">Počítání pracovního postupu je samoobslužně hostovaná hostitel služby pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="73f92-113">The Counting Workflow is self-hosted by a Workflow Service Host.</span></span> <span data-ttu-id="73f92-114">Program `Main` metoda provede následující akce:</span><span class="sxs-lookup"><span data-stu-id="73f92-114">The program's `Main` method performs the following actions:</span></span>  
  
-   <span data-ttu-id="73f92-115">Vytvoří instanci hostitele služby pracovního postupu, který je hostitelem počítání pracovního postupu a definuje koncové body, za kterých bude možné spojit počítání pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="73f92-115">Creates an instance of the Workflow Service Host that hosts the Counting Workflow and defines the endpoints under which the Counting Workflow can be reached.</span></span>  
  
-   <span data-ttu-id="73f92-116">Definuje SQL pracovního postupu instance úložiště chování, které slouží ke konfiguraci úložiště instance SQL pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="73f92-116">Defines a SQL workflow instance store behavior, which is used to configure the SQL workflow instance store.</span></span> <span data-ttu-id="73f92-117">Windows store je odeslán pokyn přistupovat ke `CountStatus` jako propagovaných vlastnost.</span><span class="sxs-lookup"><span data-stu-id="73f92-117">The store is instructed to treat `CountStatus` as a promoted property.</span></span>  
  
-   <span data-ttu-id="73f92-118">Vytvoří klienta, který volá metodu start počítání pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="73f92-118">Creates a client that calls the start method of the counting workflow.</span></span>  
  
 <span data-ttu-id="73f92-119">Po spuštění programu, čítač, automaticky spustí, počítání.</span><span class="sxs-lookup"><span data-stu-id="73f92-119">Once the program is started, the counter automatically starts counting.</span></span> <span data-ttu-id="73f92-120">Všimněte si, že může trvat několik sekund, načítání instance a konfiguraci úložiště instance pracovního postupu SQL.</span><span class="sxs-lookup"><span data-stu-id="73f92-120">Note that it might take a few seconds to load the instance and configure the SQL workflow instance store.</span></span>  
  
 <span data-ttu-id="73f92-121">Ke zvýšení úrovně hodnota čítače jako vlastní vlastnost, musí být přijata následující kroky:</span><span class="sxs-lookup"><span data-stu-id="73f92-121">To promote the counter value as a custom property, the following steps must be taken:</span></span>  
  
1.  <span data-ttu-id="73f92-122">Třída `CounterStatus` definuje rozšíření instance typu <xref:System.Activities.Persistence.PersistenceParticipant>, který je využíván jiným aktivity k poskytování proměnné stavu.</span><span class="sxs-lookup"><span data-stu-id="73f92-122">The class `CounterStatus` defines an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span> <span data-ttu-id="73f92-123">`Count`je definován jako hodnotu pouze pro zápis.</span><span class="sxs-lookup"><span data-stu-id="73f92-123">`Count` is defined as a write-only value.</span></span> <span data-ttu-id="73f92-124">Instance pracovního postupu vycházejí trvalost bodu, uloží rozšíření instance `Count` vlastnost do kolekce dat trvalost.</span><span class="sxs-lookup"><span data-stu-id="73f92-124">When a workflow instance comes to a persistence point, the instance extension saves the `Count` property into the persistence data collection.</span></span>  
  
2.  <span data-ttu-id="73f92-125">Při vytváření úložiště instance, novou vlastnost `CountStatus`, je definována pomocí `store.Promote()` metoda.</span><span class="sxs-lookup"><span data-stu-id="73f92-125">When creating the instance store, a new property, `CountStatus`, is defined through the `store.Promote()` method.</span></span>  
  
3.  <span data-ttu-id="73f92-126">Pracovního postupu `SaveCounter` aktivity přiřadí aktuální hodnota čítače `Count` pole stavu.</span><span class="sxs-lookup"><span data-stu-id="73f92-126">The workflow's `SaveCounter` activity assigns the current counter value to the `Count` status field.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="73f92-127">Pro fungování této ukázky</span><span class="sxs-lookup"><span data-stu-id="73f92-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="73f92-128">Vytvoření instance úložiště databáze.</span><span class="sxs-lookup"><span data-stu-id="73f92-128">Create the instance store database.</span></span>  
  
    1.  <span data-ttu-id="73f92-129">Otevřete [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="73f92-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="73f92-130">Přejděte do adresáře ukázkové (\WF\Basic\Persistence\SqlStoreExtensibility\CS) a spusťte CreateInstanceStore.cmd [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="73f92-130">Navigate to the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility\CS) and run CreateInstanceStore.cmd in the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
        > [!WARNING]
        >  <span data-ttu-id="73f92-131">Skript CreateInstanceStore.cmd se pokusí vytvořit databázi na výchozí instanci systému SQL Server 2008 Express.</span><span class="sxs-lookup"><span data-stu-id="73f92-131">The CreateInstanceStore.cmd script attempts to create the database on the default instance of SQL Server 2008 Express.</span></span> <span data-ttu-id="73f92-132">Pokud chcete pro instalaci databáze na jinou instanci, upravte skript tak, aby tak.</span><span class="sxs-lookup"><span data-stu-id="73f92-132">If you want to install the database on a different instance, modify the script to do so.</span></span>  
  
2.  <span data-ttu-id="73f92-133">Otevřete [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] načíst SqlStoreExtensibility.sln řešení a sestavení stisknutím kombinace kláves CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="73f92-133">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and load the SqlStoreExtensibility.sln solution and build it by pressing CTRL+SHIFT+B.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="73f92-134">Pokud jste nainstalovali databázi na jiné než výchozí instanci systému SQL Server, aktualizujte připojovací řetězec v kódu než začnete vytvářet řešení.</span><span class="sxs-lookup"><span data-stu-id="73f92-134">If you installed the database on a non-default instance of SQL Server, update the connection string in the code prior to building the solution.</span></span>  
  
3.  <span data-ttu-id="73f92-135">Spustit ukázku s oprávněními správce tak, že přejdete do adresáře bin projektu (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) v [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], pravým tlačítkem myši na SqlStoreExtensibility.exe a výběr **spustit jako Správce**.</span><span class="sxs-lookup"><span data-stu-id="73f92-135">Run the sample with administrator privileges by navigating to the project’s bin directory (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], right-clicking SqlStoreExtensibility.exe and selecting **Run as Administrator**.</span></span>  
  
### <a name="to-verify-the-sample-is-working-correctly"></a><span data-ttu-id="73f92-136">Ověření ukázku pracuje správně.</span><span class="sxs-lookup"><span data-stu-id="73f92-136">To verify the sample is working correctly</span></span>  
  
1.  <span data-ttu-id="73f92-137">Použít SQL Server Management Studio k zobrazení obsahu tabulky instance výběrem **databáze**, **InstanceStore**a potom  **System.ServiceModel.Activities.DurableInstancing.InstanceTable** v Průzkumníku objektů, klikněte pravým tlačítkem na **System.ServiceModel.Activities.DurableInstancing.InstanceTable** a vyberte  **Vybrat prvních 1 000 řádků**.</span><span class="sxs-lookup"><span data-stu-id="73f92-137">Use SQL Server Management Studio to view the contents of the instance table by selecting **Databases**, **InstanceStore**, and then **System.ServiceModel.Activities.DurableInstancing.InstanceTable** in the Object Explorer, right-click **System.ServiceModel.Activities.DurableInstancing.InstanceTable** and select **Select Top 1000 Rows**.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="73f92-138">SQL Server Management Studio, najdete v části [představení SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645)</span><span class="sxs-lookup"><span data-stu-id="73f92-138"> SQL Server Management Studio, see [Introducing SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645)</span></span>  
  
2.  <span data-ttu-id="73f92-139">Sledujte instancí pracovních postupů, které jsou uvedené.</span><span class="sxs-lookup"><span data-stu-id="73f92-139">Observe the workflow instances listed.</span></span>  
  
3.  <span data-ttu-id="73f92-140">V [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] příkazového řádku, spusťte skript QueryInstanceStore.cmd umístěný v adresáři ukázkové (\WF\Basic\Persistence\SqlStoreExtensibility).</span><span class="sxs-lookup"><span data-stu-id="73f92-140">In a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run the QueryInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
4.  <span data-ttu-id="73f92-141">Sledovat hodnota čítače se zobrazí v části **CountStatus**.</span><span class="sxs-lookup"><span data-stu-id="73f92-141">Observe the counter value displayed under **CountStatus**.</span></span>  
  
5.  <span data-ttu-id="73f92-142">Spusťte skript několikrát zobrazíte **CountStats** hodnotu změnit.</span><span class="sxs-lookup"><span data-stu-id="73f92-142">Run the script a few times to see the **CountStats** value change.</span></span>  
  
6.  <span data-ttu-id="73f92-143">Stisknutím klávesy ENTER ukončení aplikace pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="73f92-143">Press ENTER to terminate the workflow application.</span></span>  
  
### <a name="to-uninstall-the-sample"></a><span data-ttu-id="73f92-144">Chcete-li odinstalovat vzorku</span><span class="sxs-lookup"><span data-stu-id="73f92-144">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="73f92-145">Odeberte databázi úložiště instance spuštěním skriptu RemoveInstanceStore.cmd umístěný v adresáři ukázkové (\WF\Basic\Persistence\SqlStoreExtensibility).</span><span class="sxs-lookup"><span data-stu-id="73f92-145">Remove the instance store database by running the RemoveInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73f92-146">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="73f92-146">The samples may already be installed on your machine.</span></span> <span data-ttu-id="73f92-147">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="73f92-147">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="73f92-148">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="73f92-148">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="73f92-149">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="73f92-149">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a><span data-ttu-id="73f92-150">Viz také</span><span class="sxs-lookup"><span data-stu-id="73f92-150">See Also</span></span>  
 [<span data-ttu-id="73f92-151">Trvalost pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="73f92-151">Workflow Persistence</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [<span data-ttu-id="73f92-152">Služby pracovních postupů</span><span class="sxs-lookup"><span data-stu-id="73f92-152">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="73f92-153">Ukázky trvalosti a hostování AppFabric</span><span class="sxs-lookup"><span data-stu-id="73f92-153">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)