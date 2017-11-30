---
title: "Zásady aktivity v rozhraní .NET Framework 4.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1374bc086923b9ffef288a7fa90427710bdd91b4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="policy-activity-in-net-framework-45"></a><span data-ttu-id="02f87-102">Zásady aktivity v rozhraní .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="02f87-102">Policy Activity in .NET Framework 4.5</span></span>
<span data-ttu-id="02f87-103">Umožňuje aktivity Policy4 [!INCLUDE[wf2](../../../../includes/wf2-md.md)] v [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objekty, které chcete použít v [!INCLUDE[wf2](../../../../includes/wf2-md.md)] v [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) přímo pomocí pravidla modulem, který se dodává v WF 3.5.</span><span class="sxs-lookup"><span data-stu-id="02f87-103">The Policy4 activity allows [!INCLUDE[wf2](../../../../includes/wf2-md.md)] in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects to be used in [!INCLUDE[wf2](../../../../includes/wf2-md.md)] in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span> <span data-ttu-id="02f87-104">Pomocí této aktivity může vytvářet a spouštět WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>.</span><span class="sxs-lookup"><span data-stu-id="02f87-104">By using this activity, you can create and execute a WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="02f87-105">WF 3.5 stroj pravidel, které jsou součástí Windows Workflow Foundation, přečtěte si úvod k modulu Windows Workflow Foundation pravidla.</span><span class="sxs-lookup"><span data-stu-id="02f87-105"> WF 3.5 Rules Engine included as part of Windows Workflow Foundation, please read Introduction to the Windows Workflow Foundation Rules Engine.</span></span> <span data-ttu-id="02f87-106">Další informace o migraci pravidla, která WF v [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], přečtěte si prosím [migrace pokyny](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="02f87-106">For more information about migrating rules to WF in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], please read [Migration Guidance](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="02f87-107">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="02f87-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="02f87-108">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="02f87-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="02f87-109">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="02f87-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="02f87-110">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="02f87-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## <a name="projects-in-this-sample"></a><span data-ttu-id="02f87-111">Projekty v této ukázce</span><span class="sxs-lookup"><span data-stu-id="02f87-111">Projects in this Sample</span></span>  
  
|<span data-ttu-id="02f87-112">Název projektu</span><span class="sxs-lookup"><span data-stu-id="02f87-112">Project Name</span></span>|<span data-ttu-id="02f87-113">Popis</span><span class="sxs-lookup"><span data-stu-id="02f87-113">Description</span></span>|<span data-ttu-id="02f87-114">Hlavní soubory</span><span class="sxs-lookup"><span data-stu-id="02f87-114">Main Files</span></span>|  
|------------------|-----------------|----------------|  
|<span data-ttu-id="02f87-115">Policy4</span><span class="sxs-lookup"><span data-stu-id="02f87-115">Policy4</span></span>|<span data-ttu-id="02f87-116">Obsahuje aktivitu Policy4 a jeho [!INCLUDE[wf1](../../../../includes/wf1-md.md)] designer.</span><span class="sxs-lookup"><span data-stu-id="02f87-116">Contains the Policy4 activity and its [!INCLUDE[wf1](../../../../includes/wf1-md.md)] designer.</span></span>|<span data-ttu-id="02f87-117">**Policy4.cs**: Policy4 definici aktivity.</span><span class="sxs-lookup"><span data-stu-id="02f87-117">**Policy4.cs**: Policy4 activity definition.</span></span><br /><br /> <span data-ttu-id="02f87-118">**PolicyDesigner.xaml**: vlastní Návrhář aktivity Policy4.</span><span class="sxs-lookup"><span data-stu-id="02f87-118">**PolicyDesigner.xaml**: Custom designer for Policy4 activity.</span></span> <span data-ttu-id="02f87-119">Použije pravidla editor ([RuleSetDialog třída](http://go.microsoft.com/fwlink/?LinkId=150378)) z [!INCLUDE[wf1](../../../../includes/wf1-md.md)] stroj pravidel.</span><span class="sxs-lookup"><span data-stu-id="02f87-119">It uses the rules editor ([RuleSetDialog Class](http://go.microsoft.com/fwlink/?LinkId=150378)) from [!INCLUDE[wf1](../../../../includes/wf1-md.md)] rules engine.</span></span>|  
|<span data-ttu-id="02f87-120">ImperativeCodeClientSample</span><span class="sxs-lookup"><span data-stu-id="02f87-120">ImperativeCodeClientSample</span></span>|<span data-ttu-id="02f87-121">Ukázková aplikace klienta, která slouží ke konfiguraci a spustí pracovní postup pomocí Policy4 aplikace pomocí imperativní kód C# (žádné [!INCLUDE[wf1](../../../../includes/wf1-md.md)] návrháře použít).</span><span class="sxs-lookup"><span data-stu-id="02f87-121">Sample client application that configures and runs a workflow using a Policy4 application using imperative C# code (no [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Designer used).</span></span>|<span data-ttu-id="02f87-122">**ApplyDiscount.rules**: soubor s [!INCLUDE[wf1](../../../../includes/wf1-md.md)] definice pravidla.</span><span class="sxs-lookup"><span data-stu-id="02f87-122">**ApplyDiscount.rules**: File with [!INCLUDE[wf1](../../../../includes/wf1-md.md)] rule definitions.</span></span><br /><br /> <span data-ttu-id="02f87-123">**Order.cs**: typ, který reprezentuje pořadí od zákazníků.</span><span class="sxs-lookup"><span data-stu-id="02f87-123">**Order.cs**: Type that represents a customer order.</span></span> <span data-ttu-id="02f87-124">Pravidla objekty tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="02f87-124">Rules are applied to objects of this type.</span></span><br /><br /> <span data-ttu-id="02f87-125">**Program.cs**: konfiguruje a spouští pracovní postup, který má aktivita Policy4 použít pravidla definovaná v ApplyDiscount.rules k instancím objektů pořadí.</span><span class="sxs-lookup"><span data-stu-id="02f87-125">**Program.cs**: Configures and runs a workflow that has a Policy4 activity to apply rules defined in ApplyDiscount.rules to instances of Order objects.</span></span><br /><br /> <span data-ttu-id="02f87-126">**App.config**: konfigurační soubor s cestu k souboru pravidla.</span><span class="sxs-lookup"><span data-stu-id="02f87-126">**App.config**: Configuration file with the path of the rules file.</span></span>|  
|<span data-ttu-id="02f87-127">DesignerClientSample</span><span class="sxs-lookup"><span data-stu-id="02f87-127">DesignerClientSample</span></span>|<span data-ttu-id="02f87-128">Ukázková aplikace klienta, která slouží ke konfiguraci a spustí pracovní postup pomocí aplikace Policy4 v [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="02f87-128">Sample client application that configures and runs a workflow using a Policy4 application in the [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Designer.</span></span>|<span data-ttu-id="02f87-129">**Sequence1.XAML**: sekvenční pracovní postup, který používá aktivitu Policy4 k provedení pravidlo hodnocení.</span><span class="sxs-lookup"><span data-stu-id="02f87-129">**Sequence1.xaml**: Sequential workflow that uses a Policy4 activity to perform rule evaluations.</span></span><br /><br /> <span data-ttu-id="02f87-130">`Program.cs`: Běží instance pracovního postupu definované v Sequence1.xaml.</span><span class="sxs-lookup"><span data-stu-id="02f87-130">`Program.cs`: Runs an instance of the workflow defined in Sequence1.xaml.</span></span>|  
  
## <a name="the-policy4-activity"></a><span data-ttu-id="02f87-131">Policy4 aktivity</span><span class="sxs-lookup"><span data-stu-id="02f87-131">The Policy4 Activity</span></span>  
 <span data-ttu-id="02f87-132">Aktivita Policy4 je třída, která je odvozena z <xref:System.Activities.NativeActivity%601> pracovní postupy pro spuštění, který umožňuje [!INCLUDE[wf1](../../../../includes/wf1-md.md)] sady pravidel.</span><span class="sxs-lookup"><span data-stu-id="02f87-132">The Policy4 activity is a class that derives from <xref:System.Activities.NativeActivity%601> that allows workflows to execute [!INCLUDE[wf1](../../../../includes/wf1-md.md)] RuleSets.</span></span> <span data-ttu-id="02f87-133">Následující příklad kódu je zjednodušená definice veřejné OM aktivity.</span><span class="sxs-lookup"><span data-stu-id="02f87-133">The following code example is a simplified definition of the public OM of the activity.</span></span>  
  
```csharp  
public class Policy4Activity<TResult>: NativeActivity<TResult>  
{  
    public RuleSet RuleSet  
  
    [IsRequired]  
    public InArgument Input  
  
    public OutArgument<ValidationErrorCollection> ValidationErrors  
}  
```  
  
|<span data-ttu-id="02f87-134">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="02f87-134">Property</span></span>|<span data-ttu-id="02f87-135">Popis</span><span class="sxs-lookup"><span data-stu-id="02f87-135">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="02f87-136">Sada pravidel pro</span><span class="sxs-lookup"><span data-stu-id="02f87-136">RuleSet</span></span>|<span data-ttu-id="02f87-137">WF [RuleSet třída](http://go.microsoft.com/fwlink/?LinkId=150379) pro rozhraní .NET Framework 3.5, který se má vyhodnotit při provedení aktivity.</span><span class="sxs-lookup"><span data-stu-id="02f87-137">The WF [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379) for .NET Framework 3.5 to be evaluated when the activity is executed.</span></span>|  
|<span data-ttu-id="02f87-138">TargetObject</span><span class="sxs-lookup"><span data-stu-id="02f87-138">TargetObject</span></span>|<span data-ttu-id="02f87-139">Objekt, pro kterou pravidla v [RuleSet třída](http://go.microsoft.com/fwlink/?LinkId=150379) vyhodnocují.</span><span class="sxs-lookup"><span data-stu-id="02f87-139">The object against which the Rules in the [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379) are evaluated.</span></span>|  
|<span data-ttu-id="02f87-140">ValidationError</span><span class="sxs-lookup"><span data-stu-id="02f87-140">ValidationError</span></span>|<span data-ttu-id="02f87-141">Seznam chyb ověření vrácené [!INCLUDE[wf1](../../../../includes/wf1-md.md)] stroj pravidel pro rozhraní .NET Framework 3.5 při ověření [RuleSet třída](http://go.microsoft.com/fwlink/?LinkId=150379) proti cílový objekt před spuštěním.</span><span class="sxs-lookup"><span data-stu-id="02f87-141">The list of validation errors returned by the [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Rule Engine for .NET Framework 3.5 when validating the [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379) against the target object before execution.</span></span>|  
  
## <a name="policy4-activity-designer"></a><span data-ttu-id="02f87-142">Návrhář aktivity Policy4</span><span class="sxs-lookup"><span data-stu-id="02f87-142">Policy4 Activity Designer</span></span>  
 <span data-ttu-id="02f87-143">Návrhář Policy4 přidá možnosti konfigurace aktivity Policy4 bez nutnosti psaní kódu.</span><span class="sxs-lookup"><span data-stu-id="02f87-143">The Policy4 designer adds the capability to configure a Policy4 activity without the need to write code.</span></span> <span data-ttu-id="02f87-144">Po sestavení řešení, se nachází v panelu nástrojů v části **Microsoft.Samples.Activities.Rules**.</span><span class="sxs-lookup"><span data-stu-id="02f87-144">After building the solution, it can be found in the toolbox in the section **Microsoft.Samples.Activities.Rules**.</span></span>  
  
 <span data-ttu-id="02f87-145">Návrhář WF můžete konfigurovat cílový objekt a sada pravidel pro.</span><span class="sxs-lookup"><span data-stu-id="02f87-145">The WF Designer allows you to configure a target object and a RuleSet.</span></span> <span data-ttu-id="02f87-146">Když **upravit RuleSet** po kliknutí na tlačítko, WF [RuleSetDialog třída](http://go.microsoft.com/fwlink/?LinkId=150378) pro [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] se zobrazí.</span><span class="sxs-lookup"><span data-stu-id="02f87-146">When the **Edit RuleSet** button is clicked, the WF [RuleSetDialog Class](http://go.microsoft.com/fwlink/?LinkId=150378) for [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] is displayed.</span></span> <span data-ttu-id="02f87-147">Toto dialogové okno je znovu hostované [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] editoru pravidel.</span><span class="sxs-lookup"><span data-stu-id="02f87-147">This dialog is the re-hosted [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] Rules Editor.</span></span> <span data-ttu-id="02f87-148">Pomocí editoru vytvořte a upravte pravidla, která provede Policy4 aktivity.</span><span class="sxs-lookup"><span data-stu-id="02f87-148">Use the editor to create and edit the rules that the Policy4 activity executes.</span></span>  
  
## <a name="using-this-sample"></a><span data-ttu-id="02f87-149">Pomocí této ukázky</span><span class="sxs-lookup"><span data-stu-id="02f87-149">Using this Sample</span></span>  
 <span data-ttu-id="02f87-150">Ke spuštění této ukázce je vyžadováno žádné speciální nastavení.</span><span class="sxs-lookup"><span data-stu-id="02f87-150">No special set up is required to run this sample.</span></span> <span data-ttu-id="02f87-151">Stačí otevřít řešení v sadě Visual Studio a stisknutím klávesy F5 spusťte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="02f87-151">Just open the solution in Visual Studio, and press F5 to run the application.</span></span>  
  
 <span data-ttu-id="02f87-152">Tato ukázka obsahuje dva klientské aplikace: ImperativeCodeClientSample a DesignerClientSample.</span><span class="sxs-lookup"><span data-stu-id="02f87-152">This sample contains two client applications: ImperativeCodeClientSample and DesignerClientSample.</span></span> <span data-ttu-id="02f87-153">Klient ImperativeCodeClientSample ukazuje, jak nakonfigurovat a spustit aktivitu Policy40 pomocí imperativní kód C#.</span><span class="sxs-lookup"><span data-stu-id="02f87-153">The ImperativeCodeClientSample client shows how to configure and run the Policy40 activity using C# imperative code.</span></span> <span data-ttu-id="02f87-154">DesignerClientSample ukazuje, jak nakonfigurovat a spustit aktivitu Policy4 pomocí návrháře.</span><span class="sxs-lookup"><span data-stu-id="02f87-154">The DesignerClientSample shows how to configure and run the Policy4 activity using the designer.</span></span>  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a><span data-ttu-id="02f87-155">Ke spuštění klienta aplikace ImperativeCodeClientSample</span><span class="sxs-lookup"><span data-stu-id="02f87-155">To run the ImperativeCodeClientSample client application</span></span>  
  
1.  <span data-ttu-id="02f87-156">Pomocí [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], otevřete soubor řešení Policy4Sample.sln.</span><span class="sxs-lookup"><span data-stu-id="02f87-156">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Policy4Sample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="02f87-157">V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **ImperativeCodeClientSample** projektu a potom vyberte **nastavit jako spouštěný projekt**.</span><span class="sxs-lookup"><span data-stu-id="02f87-157">In **Solution Explorer**, right-click the **ImperativeCodeClientSample** project and then select **Set as startup project**.</span></span>  
  
3.  <span data-ttu-id="02f87-158">Chcete-li spustit projekt, stiskněte CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="02f87-158">To run the project, press CTRL+F5.</span></span>  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a><span data-ttu-id="02f87-159">Ke spuštění klienta aplikace ImperativeCodeClientSample</span><span class="sxs-lookup"><span data-stu-id="02f87-159">To run the ImperativeCodeClientSample client application</span></span>  
  
1.  <span data-ttu-id="02f87-160">Pomocí [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], otevřete soubor řešení Policy4Sample.sln.</span><span class="sxs-lookup"><span data-stu-id="02f87-160">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Policy4Sample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="02f87-161">V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DesignerClientSample** projektu.</span><span class="sxs-lookup"><span data-stu-id="02f87-161">In **Solution Explorer**, right-click the **DesignerClientSample** project.</span></span>  
  
    -   <span data-ttu-id="02f87-162">Vyberte **nastavit jako spouštěný projekt**.</span><span class="sxs-lookup"><span data-stu-id="02f87-162">Select **Set as startup project**.</span></span>  
  
3.  <span data-ttu-id="02f87-163">Kompilace projektu, stiskněte CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="02f87-163">To compile the project, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="02f87-164">Chcete-li spustit projekt, stiskněte CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="02f87-164">To run the project, press CTRL+F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02f87-165">Viz také</span><span class="sxs-lookup"><span data-stu-id="02f87-165">See Also</span></span>