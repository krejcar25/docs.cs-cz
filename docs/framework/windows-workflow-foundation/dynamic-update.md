---
title: "Dynamická aktualizace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6ef19b-9691-4b4b-824c-3c651a9db96e
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1d8aff19cc087cf4aea2befb7a39533422aeabd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-update"></a><span data-ttu-id="94ad4-102">Dynamická aktualizace</span><span class="sxs-lookup"><span data-stu-id="94ad4-102">Dynamic Update</span></span>
<span data-ttu-id="94ad4-103">Dynamická aktualizace poskytuje mechanismus pro pracovní postup vývojáři aplikace k aktualizaci definice pracovního postupu instance trvalou pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-103">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="94ad4-104">To může být implementace oprava chyb, nové požadavky, nebo aby bylo možné ošetřit neočekávané změny.</span><span class="sxs-lookup"><span data-stu-id="94ad4-104">This can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="94ad4-105">Toto téma obsahuje přehled funkcí Dynamická aktualizace byla zavedená v [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94ad4-105">This topic provides an overview of the dynamic update functionality introduced in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="dynamic-update"></a><span data-ttu-id="94ad4-106">Dynamická aktualizace</span><span class="sxs-lookup"><span data-stu-id="94ad4-106">Dynamic Update</span></span>  
 <span data-ttu-id="94ad4-107">Na instanci pracovního postupu trvalý, dynamická aktualizace <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> je vytvořen, který obsahuje pokyny pro modul runtime, které popisují, jak upravit k instanci pracovního postupu trvalou tak, aby odrážela požadované změny.</span><span class="sxs-lookup"><span data-stu-id="94ad4-107">To apply dynamic updates to a persisted workflow instance, a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> is created that contains instructions for the runtime that describe how to modify the persisted workflow instance to reflect the desired changes.</span></span> <span data-ttu-id="94ad4-108">Po vytvoření mapy aktualizace, je tato instance požadované trvalou pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-108">Once the update map is created, it is applied to the desired persisted workflow instances.</span></span> <span data-ttu-id="94ad4-109">Po dynamické aktualizace, dá se k instanci pracovního postupu obnovit pomocí nové definice aktualizované pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-109">Once the dynamic update is applied, the workflow instance may be resumed using the new updated workflow definition.</span></span> <span data-ttu-id="94ad4-110">Existují čtyři kroky potřebné k vytvoření a použití mapování aktualizace.</span><span class="sxs-lookup"><span data-stu-id="94ad4-110">There are four steps required to create and apply an update map.</span></span>  
  
1.  [<span data-ttu-id="94ad4-111">Příprava definice pracovního postupu pro dynamické aktualizace</span><span class="sxs-lookup"><span data-stu-id="94ad4-111">Prepare the workflow definition for dynamic update</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Prepare)  
  
2.  [<span data-ttu-id="94ad4-112">Aktualizace definice pracovního postupu tak, aby odrážela požadované změny</span><span class="sxs-lookup"><span data-stu-id="94ad4-112">Update the workflow definition to reflect the desired changes</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Update)  
  
3.  [<span data-ttu-id="94ad4-113">Vytvoření mapy aktualizace</span><span class="sxs-lookup"><span data-stu-id="94ad4-113">Create the update map</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Create)  
  
4.  [<span data-ttu-id="94ad4-114">Použít aktualizace mapy pro instance požadované trvalou pracovních postupů</span><span class="sxs-lookup"><span data-stu-id="94ad4-114">Apply the update map to the desired persisted workflow instances</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Apply)  
  
> [!NOTE]
>  <span data-ttu-id="94ad4-115">Všimněte si, že se dají provést kroky 1 až 3, které zahrnují vytváření mapy aktualizace, nezávisle na instalaci aktualizace.</span><span class="sxs-lookup"><span data-stu-id="94ad4-115">Note that steps 1 through 3, which cover the creation of the update map, may be performed independently of applying the update.</span></span> <span data-ttu-id="94ad4-116">Běžný scénář, že vývojář pracovního postupu vytvoříte aktualizace mapovat do offline režimu a pak správce budou platit aktualizace později.</span><span class="sxs-lookup"><span data-stu-id="94ad4-116">A common scenario that that the workflow developer will create the update map offline, and then an administrator will apply the update at a later time.</span></span>  
  
 <span data-ttu-id="94ad4-117">Toto téma obsahuje přehled procesu dynamické aktualizace pro přidání nové aktivity na trvalou instanci kompilované Xaml pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-117">This topic provides an overview of the dynamic update process of adding a new activity to a persisted instance of a compiled Xaml workflow.</span></span>  
  
###  <span data-ttu-id="94ad4-118"><a name="Prepare"></a>Příprava definice pracovního postupu pro dynamické aktualizace</span><span class="sxs-lookup"><span data-stu-id="94ad4-118"><a name="Prepare"></a> Prepare the workflow definition for dynamic update</span></span>  
 <span data-ttu-id="94ad4-119">Prvním krokem v procesu dynamické aktualizace je příprava definice pracovního postupu požadované pro aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="94ad4-119">The first step in the dynamic update process is to prepare the desired workflow definition for update.</span></span> <span data-ttu-id="94ad4-120">To se provádí volání <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> metoda a předávání definice pracovního postupu, který chcete upravit.</span><span class="sxs-lookup"><span data-stu-id="94ad4-120">This is done by calling the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> method and passing in the workflow definition to modify.</span></span> <span data-ttu-id="94ad4-121">Tato metoda ověří a potom provede stromu pracovního postupu k identifikaci všechny objekty, například veřejné a proměnné, které je třeba označit tak, že se má porovnat později s definice upravené pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-121">This method validates and then walks the workflow tree to identify all of the objects such as public activities and variables that need to be tagged so they can be compared later with the modified workflow definition.</span></span> <span data-ttu-id="94ad4-122">Po jejím dokončení, je stromu pracovního postupu klonovat a připojené k původní definice pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-122">When this is complete, the workflow tree is cloned and attached to the original workflow definition.</span></span> <span data-ttu-id="94ad4-123">Při aktualizaci mapy je aktualizovaná verze definice pracovního postupu se porovná se původní definice pracovního postupu a mapy aktualizace bude vytvořena podle rozdíly.</span><span class="sxs-lookup"><span data-stu-id="94ad4-123">When the update map is created, the updated version of the workflow definition is compared with the original workflow definition and the update map is generated based on the differences.</span></span>  
  
 <span data-ttu-id="94ad4-124">Příprava pracovního postupu Xaml pro dynamické aktualizace může být načten do <xref:System.Activities.ActivityBuilder>a potom <xref:System.Activities.ActivityBuilder> je předána do <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94ad4-124">To prepare a Xaml workflow for dynamic update it may be loaded into an <xref:System.Activities.ActivityBuilder>, and then the <xref:System.Activities.ActivityBuilder> is passed into <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94ad4-125">Další informace o práci s serializovat pracovní postupy a <xref:System.Activities.ActivityBuilder>, najdete v části [serializaci pracovních postupů a aktivit do a z XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="94ad4-125">For more information about working with serialized workflows and <xref:System.Activities.ActivityBuilder>, see [Serializing Workflows and Activities to and from XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>  
  
 <span data-ttu-id="94ad4-126">V následujícím příkladu `MortgageWorkflow` definice (který se skládá z <xref:System.Activities.Statements.Sequence> s několika aktivitami podřízené) je načten do <xref:System.Activities.ActivityBuilder>a pak připravené pro dynamické aktualizace.</span><span class="sxs-lookup"><span data-stu-id="94ad4-126">In the following example, a `MortgageWorkflow` definition (that consists of a <xref:System.Activities.Statements.Sequence> with several child activities) is loaded into an <xref:System.Activities.ActivityBuilder>, and then prepared for dynamic update.</span></span> <span data-ttu-id="94ad4-127">Po metoda vrátí, <xref:System.Activities.ActivityBuilder> obsahuje původní definice pracovního postupu, jakož i kopii.</span><span class="sxs-lookup"><span data-stu-id="94ad4-127">After the method returns, the <xref:System.Activities.ActivityBuilder> contains the original workflow definition as well as a copy.</span></span>  
  
```csharp  
// Load the MortgageWorkflow definition from Xaml into  
// an ActivityBuilder.  
XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()  
{  
    LocalAssembly = Assembly.GetExecutingAssembly()  
};  
  
XamlXmlReader xamlReader = new XamlXmlReader(@"C:\WorkflowDefitinions\MortgageWorkflow.xaml",   
    readerSettings);  
  
ActivityBuilder ab = XamlServices.Load(  
    ActivityXamlServices.CreateBuilderReader(xamlReader)) as ActivityBuilder;  
  
// Prepare the workflow definition for dynamic update.  
DynamicUpdateServices.PrepareForUpdate(ab);  
```  
  
> [!NOTE]
>  <span data-ttu-id="94ad4-128">Chcete-li stáhnout ukázkový kód, který doprovází toto téma, přečtěte si téma [dynamická aktualizace ukázkový kód](http://go.microsoft.com/fwlink/?LinkId=227905).</span><span class="sxs-lookup"><span data-stu-id="94ad4-128">To download the sample code that accompanies this topic, see [Dynamic Update sample code](http://go.microsoft.com/fwlink/?LinkId=227905).</span></span>  
  
###  <span data-ttu-id="94ad4-129"><a name="Update"></a>Aktualizace definice pracovního postupu tak, aby odrážela požadované změny</span><span class="sxs-lookup"><span data-stu-id="94ad4-129"><a name="Update"></a> Update the workflow definition to reflect the desired changes</span></span>  
 <span data-ttu-id="94ad4-130">Jakmile definice pracovního postupu je připravena pro aktualizace, můžete provést požadované změny.</span><span class="sxs-lookup"><span data-stu-id="94ad4-130">Once the workflow definition has been prepared for updating, the desired changes can be made.</span></span> <span data-ttu-id="94ad4-131">Můžete přidat nebo odebrat aktivity, přidat, přesunout nebo odstranit veřejné proměnné, přidat nebo odebrat argumenty a provést změny podpis delegáti aktivity.</span><span class="sxs-lookup"><span data-stu-id="94ad4-131">You can add or remove activities, add, move or delete public variables, add or remove arguments, and make changes to the signature of activity delegates.</span></span> <span data-ttu-id="94ad4-132">Nelze odebrat aktivitu spuštěné ani změnit podpis spuštěné delegáta.</span><span class="sxs-lookup"><span data-stu-id="94ad4-132">You cannot remove a running activity or change the signature of a running delegate.</span></span> <span data-ttu-id="94ad4-133">Tyto změny pomocí kódu, nebo v Návrháři znovu hostovaných pracovních postupů.</span><span class="sxs-lookup"><span data-stu-id="94ad4-133">These changes may be made using code, or in a re-hosted workflow designer.</span></span> <span data-ttu-id="94ad4-134">V následujícím příkladu, vlastní `VerifyAppraisal` aktivity se přidá do pořadí, které tvoří text `MortgageWorkflow` z předchozího příkladu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-134">In the following example, a custom `VerifyAppraisal` activity is added to the Sequence that makes up the body of the `MortgageWorkflow` from the previous example.</span></span>  
  
```csharp  
// Make desired changes to the definition. In this example, we are  
// inserting a new VerifyAppraisal activity as the 3rd child of the root Sequence.  
VerifyAppraisal va = new VerifyAppraisal  
{  
    Result = new VisualBasicReference<bool>("LoanCriteria")  
};  
  
// Get the Sequence that makes up the body of the workflow.  
Sequence s = ab.Implementation as Sequence;  
  
// Insert the new activity into the Sequence.  
s.Activities.Insert(2, va);  
```  
  
###  <span data-ttu-id="94ad4-135"><a name="Create"></a>Vytvoření mapy aktualizace</span><span class="sxs-lookup"><span data-stu-id="94ad4-135"><a name="Create"></a> Create the update map</span></span>  
 <span data-ttu-id="94ad4-136">Jakmile připravené pro aktualizaci definice pracovního postupu byla změněna, lze vytvořit mapy aktualizace.</span><span class="sxs-lookup"><span data-stu-id="94ad4-136">Once the workflow definition that was prepared for update has been modified, the update map can be created.</span></span> <span data-ttu-id="94ad4-137">K vytvoření mapy dynamické aktualizace, <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> metoda je volána.</span><span class="sxs-lookup"><span data-stu-id="94ad4-137">To create a dynamic update map, the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> method is invoked.</span></span> <span data-ttu-id="94ad4-138">Tento příkaz vrátí <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> obsahující informace o modulu runtime je potřeba upravit instanci trvalou pracovního postupu tak, aby může být načtena a pokračuje s novou definici pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-138">This returns a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> that contains the information the runtime needs to modify a persisted workflow instance so that it may be loaded and resumed with the new workflow definition.</span></span> <span data-ttu-id="94ad4-139">V následujícím příkladu se vytvoří dynamické mapy pro upravenou `MortgageWorkflow` definice z předchozího příkladu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-139">In the following example, a dynamic map is created for the modified `MortgageWorkflow` definition from the previous example.</span></span>  
  
```csharp  
// Create the update map.  
DynamicUpdateMap map = DynamicUpdateServices.CreateUpdateMap(ab);  
```  
  
 <span data-ttu-id="94ad4-140">Tato mapa aktualizace okamžitě lze upravit instancí trvalou pracovních postupů, nebo více obvykle lze uložit a aktualizace později.</span><span class="sxs-lookup"><span data-stu-id="94ad4-140">This update map can immediately be used to modify persisted workflow instances, or more typically it can be saved and the updates applied later.</span></span> <span data-ttu-id="94ad4-141">Jeden způsob, jak uložit mapy aktualizace je určená k serializaci do souboru, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-141">One way to save the update map is to serialize it to a file, as shown in the following example.</span></span>  
  
```csharp  
// Serialize the update map to a file.  
DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));  
using (FileStream fs = System.IO.File.Open(@"C:\WorkflowDefitinions\MortgageWorkflow.map", FileMode.Create))  
{  
    serializer.WriteObject(fs, map);  
}  
```  
  
 <span data-ttu-id="94ad4-142">Když <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> vrátí definice klonovaný pracovního postupu a další informace dynamické aktualizace, která byla přidána ve volání <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> je odebrán, a je připravený uložit tak, aby ho lze později při obnovení aktualizaci definice pracovního postupu změny instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-142">When <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> returns, the cloned workflow definition and other dynamic update information that was added in the call to <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> is removed, and the modified workflow definition is ready to be saved so that it can be used later when resuming updated workflow instances.</span></span> <span data-ttu-id="94ad4-143">V následujícím příkladu je uložena definice pracovního postupu změny `MortgageWorkflow_v2.xaml`.</span><span class="sxs-lookup"><span data-stu-id="94ad4-143">In the following example, the modified workflow definition is saved to `MortgageWorkflow_v2.xaml`.</span></span>  
  
```csharp  
// Save the modified workflow definition.  
StreamWriter sw = File.CreateText(@"C:\WorkflowDefitinions\MortgageWorkflow_v1.1.xaml");  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw, ab);  
sw.Close();  
```  
  
###  <span data-ttu-id="94ad4-144"><a name="Apply"></a>Použít aktualizace mapy pro instance požadované trvalou pracovních postupů</span><span class="sxs-lookup"><span data-stu-id="94ad4-144"><a name="Apply"></a> Apply the update map to the desired persisted workflow instances</span></span>  
 <span data-ttu-id="94ad4-145">Použití map aktualizace lze provést kdykoli po jeho vytvoření.</span><span class="sxs-lookup"><span data-stu-id="94ad4-145">Applying the update map can be done at any time after creating it.</span></span> <span data-ttu-id="94ad4-146">Je možné ji provést, hned pomocí <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> instanci, která vrátila <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>, nebo je možné ji provést, později pomocí uložené kopie mapy aktualizace.</span><span class="sxs-lookup"><span data-stu-id="94ad4-146">It can be done right away using the <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> instance that was returned by <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>, or it can be done later using a saved copy of the update map.</span></span> <span data-ttu-id="94ad4-147">Aktualizace instance pracovního postupu, načíst do <xref:System.Activities.WorkflowApplicationInstance> pomocí <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94ad4-147">To update a workflow instance, load it into a <xref:System.Activities.WorkflowApplicationInstance> using <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="94ad4-148">Dále vytvořte <xref:System.Activities.WorkflowApplication> pomocí definice aktualizované pracovního postupu a požadovanou <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="94ad4-148">Next, create a <xref:System.Activities.WorkflowApplication> using the updated workflow definition, and the desired <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="94ad4-149">To <xref:System.Activities.WorkflowIdentity> může být jiný než ten, který byl použitý k zachování původní pracovního postupu a většinou je, aby bylo zřejmé, že trvalou instanci se změnila.</span><span class="sxs-lookup"><span data-stu-id="94ad4-149">This <xref:System.Activities.WorkflowIdentity> may be different than the one that was used to persist the original workflow, and typically is in order to reflect that the persisted instance has been modified.</span></span> <span data-ttu-id="94ad4-150">Jednou <xref:System.Activities.WorkflowApplication> je vytvořen, je načten pomocí přetížení <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType> , která má <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>a potom pomocí volání uvolněna z <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94ad4-150">Once the <xref:System.Activities.WorkflowApplication> is created, it is loaded using the overload of <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType> that takes a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>, and then unloaded with a call to <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="94ad4-151">To platí dynamická aktualizace a přetrvává k instanci pracovního postupu aktualizované.</span><span class="sxs-lookup"><span data-stu-id="94ad4-151">This applies the dynamic update and persists the updated workflow instance.</span></span>  
  
```csharp  
// Load the serialized update map.  
DynamicUpdateMap map;  
using (FileStream fs = File.Open(@"C:\WorkflowDefitinions\MortgageWorkflow.map", FileMode.Open))  
{  
    DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));  
    object updateMap = serializer.ReadObject(fs);  
    if (updateMap == null)  
    {  
        throw new ApplicationException("DynamicUpdateMap is null.");  
    }  
  
    map = (DynamicUpdateMap)updateMap;  
}  
  
// Retrieve a list of workflow instance ids that corresponds to the  
// workflow instances to update. This step is the responsibility of  
// the application developer.  
List<Guid> ids = GetPersistedWorkflowIds();  
foreach (Guid id in ids)  
{  
    // Get a proxy to the persisted workflow instance.  
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);  
    WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(id, store);  
  
    // If desired, you can inspect the WorkflowIdentity of the instance  
    // using the DefinitionIdentity property to determine whether to apply  
    // the update.  
    Console.WriteLine(instance.DefinitionIdentity);  
  
    // Create a workflow application. You must specify the updated workflow definition, and  
    // you may provide an updated WorkflowIdentity if desired to reflect the update.  
    WorkflowIdentity identity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow v1.1",  
        Version = new Version(1, 1, 0, 0)  
    };  
  
    // Load the persisted workflow instance using the updated workflow definition  
    // and with an updated WorkflowIdentity. In this example the MortgageWorkflow class  
    // contains the updated definition.  
    WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);  
  
    // Apply the dynamic update on the loaded instance.                
    wfApp.Load(instance, map);  
  
    // Unload the updated instance.  
    wfApp.Unload();  
}  
```  
  
### <a name="resuming-an-updated-workflow-instance"></a><span data-ttu-id="94ad4-152">Obnovování Instance aktualizované pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="94ad4-152">Resuming an Updated Workflow Instance</span></span>  
 <span data-ttu-id="94ad4-153">Po dynamické aktualizace, může být obnoven k instanci pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-153">Once dynamic update has been applied, the workflow instance may be resumed.</span></span> <span data-ttu-id="94ad4-154">Všimněte si, že nové aktualizované definice a <xref:System.Activities.WorkflowIdentity> se musí použít.</span><span class="sxs-lookup"><span data-stu-id="94ad4-154">Note that the new updated definition and <xref:System.Activities.WorkflowIdentity> must be used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94ad4-155">Další informace o práci s <xref:System.Activities.WorkflowApplication> a <xref:System.Activities.WorkflowIdentity>, najdete v části[pomocí WorkflowIdentity a správa verzí](../../../docs/framework/windows-workflow-foundation/using-workflowidentity-and-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="94ad4-155">For more information about working with <xref:System.Activities.WorkflowApplication> and <xref:System.Activities.WorkflowIdentity>, see[Using WorkflowIdentity and Versioning](../../../docs/framework/windows-workflow-foundation/using-workflowidentity-and-versioning.md).</span></span>  
  
 <span data-ttu-id="94ad4-156">V následujícím příkladu `MortgageWorkflow_v1.1.xaml` pracovní postup z předchozího příkladu je kompilovaná a je načtena a obnovit pomocí definice aktualizované pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="94ad4-156">In the following example, the `MortgageWorkflow_v1.1.xaml` workflow from the previous example has been compiled, and is loaded and resumed using the updated workflow definition.</span></span>  
  
```csharp  
// Load the persisted workflow instance using the updated workflow definition  
// and updated WorkflowIdentity.  
WorkflowIdentity identity = new WorkflowIdentity  
{  
    Name = "MortgageWorkflow v1.1",  
    Version = new Version(1, 1, 0, 0)  
};  
  
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);  
  
// Configure persistence and desired workflow event handlers.  
// (Omitted for brevity.)  
ConfigureWorkflowApplication(wfApp);  
  
// Load the persisted workflow instance.  
wfApp.Load(InstanceId);  
  
// Resume the workflow.  
// wfApp.ResumeBookmark(...);  
```  
  
> [!NOTE]
>  <span data-ttu-id="94ad4-157">Chcete-li stáhnout ukázkový kód, který doprovází toto téma, přečtěte si téma [dynamická aktualizace ukázkový kód](http://go.microsoft.com/fwlink/?LinkId=227905).</span><span class="sxs-lookup"><span data-stu-id="94ad4-157">To download the sample code that accompanies this topic, see [Dynamic Update sample code](http://go.microsoft.com/fwlink/?LinkId=227905).</span></span>