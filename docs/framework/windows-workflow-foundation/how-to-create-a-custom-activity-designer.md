---
title: "Postupy: vytvoření vlastního návrháře aktivit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
caps.latest.revision: "25"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cdf64dd7aca82fb0d0b3111832aca863a327270b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-activity-designer"></a><span data-ttu-id="0d26d-102">Postupy: vytvoření vlastního návrháře aktivit</span><span class="sxs-lookup"><span data-stu-id="0d26d-102">How to: Create a Custom Activity Designer</span></span>
<span data-ttu-id="0d26d-103">Návrháři vlastních aktivit jsou obvykle implementovány tak, aby jejich aktivity související s ostatními aktivitami, jejichž Designer může být přetažen na návrhovou plochu, která s nimi bez možnosti složení.</span><span class="sxs-lookup"><span data-stu-id="0d26d-103">Custom activity designers are typically implemented so that their associated activities are composable with other activities whose designers can be dropped on to the design surface with them.</span></span> <span data-ttu-id="0d26d-104">Tato funkce vyžaduje, aby zadali Návrhář vlastní aktivity "rozevírací zónu" umístění libovolné aktivity a také způsob, jak spravovat výsledné kolekci elementů na návrhovou plochu.</span><span class="sxs-lookup"><span data-stu-id="0d26d-104">This functionality requires that a custom activity designer provide a "drop zone" where an arbitrary activity can be placed and also the means to manage the resulting collection of elements on the design surface.</span></span> <span data-ttu-id="0d26d-105">Toto téma popisuje, jak vytvořit vlastní aktivity návrháře obsahující rozevírací zóny a jak vytvořit Návrhář vlastní aktivity, který zajišťuje, že úpravy funkce potřebné ke správě kolekci elementů návrháře.</span><span class="sxs-lookup"><span data-stu-id="0d26d-105">This topic describes how to create a custom activity designer that contains such a drop zone and how to create a custom activity designer that provides that editing functionality needed to manage the collection of designer elements.</span></span>  
  
 <span data-ttu-id="0d26d-106">Návrháři vlastních aktivit obvykle dědí <xref:System.Activities.Presentation.ActivityDesigner> což je výchozí základní aktivitě návrháře typ pro všechny aktivity bez konkrétní návrháře.</span><span class="sxs-lookup"><span data-stu-id="0d26d-106">Custom activity designers typically inherit from <xref:System.Activities.Presentation.ActivityDesigner> which is the default base activity designer type for any activities without a specific designer.</span></span> <span data-ttu-id="0d26d-107">Tento typ poskytuje prostředí návrhu interakci s mřížku vlastností a konfigurace základní aspekty například správu barvy a ikony.</span><span class="sxs-lookup"><span data-stu-id="0d26d-107">This type provides the design-time experience of interacting with the property grid and configuring basic aspects such as managing colors and icons.</span></span>  
  
 <span data-ttu-id="0d26d-108"><xref:System.Activities.Presentation.ActivityDesigner>pomocí dvou ovládacích prvků pomocné rutiny, <xref:System.Activities.Presentation.WorkflowItemPresenter> a <xref:System.Activities.Presentation.WorkflowItemsPresenter> aby bylo snazší vývoj Návrháře vlastních aktivit.</span><span class="sxs-lookup"><span data-stu-id="0d26d-108"><xref:System.Activities.Presentation.ActivityDesigner> uses two helper controls, <xref:System.Activities.Presentation.WorkflowItemPresenter> and <xref:System.Activities.Presentation.WorkflowItemsPresenter> to make it easier to develop custom activity designers.</span></span> <span data-ttu-id="0d26d-109">Běžné funkce jako přetahování podřízené elementy, odstranění, výběru a přidání těchto podřízených elementů, které zpracovávají.</span><span class="sxs-lookup"><span data-stu-id="0d26d-109">They handle common functionality like dragging and dropping of child elements, deletion, selection, and addition of those child elements.</span></span> <span data-ttu-id="0d26d-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> Umožňuje jeden podřízený element uživatelského rozhraní uvnitř, zajištění "rozevírací zóně", je při <xref:System.Activities.Presentation.WorkflowItemsPresenter> může poskytnout podporu více prvky uživatelského rozhraní, včetně další funkce, jako je řazení, přesunutí, odstranění a přidání podřízených elementů.</span><span class="sxs-lookup"><span data-stu-id="0d26d-110">The <xref:System.Activities.Presentation.WorkflowItemPresenter> allows a single child UI element inside, providing the "drop zone", it while the <xref:System.Activities.Presentation.WorkflowItemsPresenter> can provide support multiple UI elements, including additional functionality like the ordering, moving, deleting, and adding of child elements.</span></span>  
  
 <span data-ttu-id="0d26d-111">Další část klíče scénáře, který potřebuje zvýraznění implementace Návrhář vlastní aktivity se týká způsob, ve kterém jsou visual úpravy svázán pomocí [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] datové vazby k instanci uložené v paměti co jsme jsou úpravy v návrháři.</span><span class="sxs-lookup"><span data-stu-id="0d26d-111">The other key part of the story that needs highlighting in the implementation of a custom activity designer concerns the way in which the visual edits are bound using [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] data binding to the instance stored in memory of what we are editing in the designer.</span></span> <span data-ttu-id="0d26d-112">To lze provést stromu položku modelu, který zodpovídá taky pro povolení oznámení o změně a sledování událostí jako změny ve stavu.</span><span class="sxs-lookup"><span data-stu-id="0d26d-112">This is accomplished by the Model Item tree, which is also responsible for enabling change notification and the tracking of events like changes in states.</span></span>  
  
 <span data-ttu-id="0d26d-113">Toto téma popisuje dva postupy.</span><span class="sxs-lookup"><span data-stu-id="0d26d-113">This topic outlines two procedures.</span></span>  
  
1.  <span data-ttu-id="0d26d-114">První postup popisuje, jak vytvořit vlastní aktivity designer s <xref:System.Activities.Presentation.WorkflowItemPresenter> rozevírací zóny, která obdrží ostatní aktivity, která poskytuje.</span><span class="sxs-lookup"><span data-stu-id="0d26d-114">The first procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter> that provides the drop zone that receives other activities.</span></span> <span data-ttu-id="0d26d-115">Tento postup je založen na [vlastní složený Designer - přednášejícího položky pracovního postupu](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) ukázka.</span><span class="sxs-lookup"><span data-stu-id="0d26d-115">This procedure is based on the [Custom Composite Designers - Workflow Item Presenter](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) sample.</span></span>  
  
2.  <span data-ttu-id="0d26d-116">Druhý postup popisuje, jak vytvořit vlastní aktivity designer s <xref:System.Activities.Presentation.WorkflowItemsPresenter> poskytující funkce potřebná pro úpravu kolekce elementech, které obsahují.</span><span class="sxs-lookup"><span data-stu-id="0d26d-116">The second procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter> that provides the functionality needed to edit of a collection of contained elements.</span></span> <span data-ttu-id="0d26d-117">Tento postup je založen na [vlastní složený Designer - přednášejícího položky pracovního postupu](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) ukázka.</span><span class="sxs-lookup"><span data-stu-id="0d26d-117">This procedure is based on the [Custom Composite Designers - Workflow Items Presenter](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) sample.</span></span>  
  
### <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a><span data-ttu-id="0d26d-118">Vytvoření vlastního návrháře aktivit s rozevírací zóny pomocí WorkflowItemPresenter</span><span class="sxs-lookup"><span data-stu-id="0d26d-118">To create a custom activity designer with a drop zone using WorkflowItemPresenter</span></span>  
  
1.  <span data-ttu-id="0d26d-119">Spustit [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d26d-119">Start [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="0d26d-120">Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu...** .</span><span class="sxs-lookup"><span data-stu-id="0d26d-120">On the **File** menu, point to **New**, and then select **Project…**.</span></span>  
  
     <span data-ttu-id="0d26d-121">**Nový projekt** otevře se dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="0d26d-121">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="0d26d-122">V **nainstalovaných šablonách** podokně, vyberte **Windows** z vaší upřednostňovaný jazyk kategorie.</span><span class="sxs-lookup"><span data-stu-id="0d26d-122">In the **Installed Templates** pane, select **Windows** from your preferred language category.</span></span>  
  
4.  <span data-ttu-id="0d26d-123">V **šablony** podokně, vyberte **aplikaci WPF**.</span><span class="sxs-lookup"><span data-stu-id="0d26d-123">In the **Templates** pane, select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="0d26d-124">V **název** zadejte `UsingWorkflowItemPresenter`.</span><span class="sxs-lookup"><span data-stu-id="0d26d-124">In the **Name** box, enter `UsingWorkflowItemPresenter`.</span></span>  
  
6.  <span data-ttu-id="0d26d-125">V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.</span><span class="sxs-lookup"><span data-stu-id="0d26d-125">In the **Location** box, enter the directory in which you want to save your project, or click **Browse** to navigate to it.</span></span>  
  
7.  <span data-ttu-id="0d26d-126">V **řešení** pole, přijměte výchozí hodnotu.</span><span class="sxs-lookup"><span data-stu-id="0d26d-126">In the **Solution** box, accept the default value.</span></span>  
  
8.  <span data-ttu-id="0d26d-127">Click **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d26d-127">Click **OK**.</span></span>  
  
9. <span data-ttu-id="0d26d-128">Klikněte pravým tlačítkem na soubor MainWindows.xaml v **Průzkumníku řešení**, vyberte **odstranit** a potvrďte **OK** v **Microsoft Visual Studio**dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="0d26d-128">Right-click the MainWindows.xaml file in the **Solution Explorer**, select **Delete** and confirm **OK** in the **Microsoft Visual Studio** dialogue box.</span></span>  
  
10. <span data-ttu-id="0d26d-129">Klikněte pravým tlačítkem na projekt UsingWorkflowItemPresenter **Průzkumníku řešení**, vyberte **přidat**, pak **novou položku...**</span><span class="sxs-lookup"><span data-stu-id="0d26d-129">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="0d26d-130">se zprovoznit **přidat novou položku** dialogový a vyberte **WPF** kategorie z **nainstalovaných šablonách** na levé straně.</span><span class="sxs-lookup"><span data-stu-id="0d26d-130">to bring up the **Add New Item** dialogue and select the **WPF** category from the **Installed Templates** section on the left.</span></span>  
  
11. <span data-ttu-id="0d26d-131">Vyberte **okno (WPF)** šablony, pojmenujte ji `RehostingWFDesigner`a klikněte na tlačítko **přidat**.</span><span class="sxs-lookup"><span data-stu-id="0d26d-131">Select the  **Window (WPF)** template, name it `RehostingWFDesigner`, and click **Add**.</span></span>  
  
12. <span data-ttu-id="0d26d-132">Otevřete soubor RehostingWFDesigner.xaml a vložte následující kód do ní k zadání uživatelského rozhraní pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="0d26d-132">Open the RehostingWFDesigner.xaml file and paste the following code into it to define the UI for the application.</span></span>  
  
    ```xml  
    <Window x:Class=" UsingWorkflowItemPresenter.RehostingWFDesigner"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"  
            xmlns:sys="clr-namespace:System;assembly=mscorlib"  
            Title="Window1" Height="600" Width="900">  
        <Window.Resources>  
            <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>  
        </Window.Resources>  
        <Grid>  
            <Grid.ColumnDefinitions>  
                <ColumnDefinition Width="2*"/>  
                <ColumnDefinition Width="7*"/>  
                <ColumnDefinition Width="3*"/>  
            </Grid.ColumnDefinitions>  
            <Border Grid.Column="0">  
                <sapt:ToolboxControl Name="Toolbox">  
                    <sapt:ToolboxCategory CategoryName="Basic">  
                        <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.Sequence  
                            </sapt:ToolboxItemWrapper.ToolName>  
                           </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.WriteLine  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.If  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.While  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                    </sapt:ToolboxCategory>  
                </sapt:ToolboxControl>  
            </Border>  
            <Border Grid.Column="1" Name="DesignerBorder"/>  
            <Border Grid.Column="2" Name="PropertyBorder"/>  
        </Grid>  
    </Window>  
    ```  
  
13. <span data-ttu-id="0d26d-133">Pokud chcete přidružit Návrhář aktivity typu aktivity, je nutné zaregistrovat tento Návrhář aktivity s úložištěm metadat.</span><span class="sxs-lookup"><span data-stu-id="0d26d-133">To associate an activity designer with an activity type, you must register that activity designer with the metadata store.</span></span> <span data-ttu-id="0d26d-134">Chcete-li to provést, přidejte `RegisterMetadata` metodu `RehostingWFDesigner` – třída.</span><span class="sxs-lookup"><span data-stu-id="0d26d-134">To do this, add the `RegisterMetadata` method to the `RehostingWFDesigner` class.</span></span> <span data-ttu-id="0d26d-135">V rámci oboru `RegisterMetadata` metody vytvoření <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> objekt a volání <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> metoda pro přidání atributů do ní.</span><span class="sxs-lookup"><span data-stu-id="0d26d-135">Within the scope of the  `RegisterMetadata` method, create an <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> object and call the <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> method to add the attributes to it.</span></span> <span data-ttu-id="0d26d-136">Volání <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> metody přidat <xref:System.Activities.Presentation.Metadata.AttributeTable> k úložišti metadat.</span><span class="sxs-lookup"><span data-stu-id="0d26d-136">Call the <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> method to add the <xref:System.Activities.Presentation.Metadata.AttributeTable> to the metadata store.</span></span> <span data-ttu-id="0d26d-137">Následující kód obsahuje rehosting logiku pro návrháře.</span><span class="sxs-lookup"><span data-stu-id="0d26d-137">The following code contains the rehosting logic for the designer.</span></span> <span data-ttu-id="0d26d-138">Ho zaregistruje metadata, umístí `SimpleNativeActivity` do sady nástrojů a vytvoří pracovní postup.</span><span class="sxs-lookup"><span data-stu-id="0d26d-138">It registers the metadata, puts the `SimpleNativeActivity` into the toolbox, and creates the workflow.</span></span> <span data-ttu-id="0d26d-139">Tento kód vložte do souboru RehostingWFDesigner.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="0d26d-139">Put this code into the RehostingWFDesigner.xaml.cs file.</span></span>  
  
    ```  
    using System;  
    using System.Activities.Core.Presentation;  
    using System.Activities.Presentation;  
    using System.Activities.Presentation.Metadata;  
    using System.Activities.Presentation.Toolbox;  
    using System.Activities.Statements;  
    using System.ComponentModel;  
    using System.Windows;  
  
    namespace UsingWorkflowItemPresenter  
    {  
        // Interaction logic for RehostingWFDesigner.xaml  
        public partial class RehostingWFDesigner  
        {  
            public RehostingWFDesigner()  
            {  
                InitializeComponent();  
            }  
  
            protected override void OnInitialized(EventArgs e)  
            {  
                base.OnInitialized(e);  
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
                // add custom activity to toolbox  
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));  
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
    ```  
  
14. <span data-ttu-id="0d26d-140">V adresáři odkazy v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **přidat odkaz na...**</span><span class="sxs-lookup"><span data-stu-id="0d26d-140">Right-click the References directory in Solution Explorer and select **Add Reference …**</span></span> <span data-ttu-id="0d26d-141">Chcete-li zprovoznit **přidat odkaz na** dialogu.</span><span class="sxs-lookup"><span data-stu-id="0d26d-141">to bring up the **Add Reference** dialogue.</span></span>  
  
15. <span data-ttu-id="0d26d-142">Klikněte **.NET** najděte sestavení s názvem **System.Activities.Core.Presentation**, vyberte ho a klikněte na tlačítko **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d26d-142">Click the **.NET** tab, locate the assembly named **System.Activities.Core.Presentation**, select it and click **OK**.</span></span>  
  
16. <span data-ttu-id="0d26d-143">Pomocí stejného postupu, přidejte odkazy na následující:</span><span class="sxs-lookup"><span data-stu-id="0d26d-143">Using the same procedure, add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="0d26d-144">System.Data.DataSetExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="0d26d-144">System.Data.DataSetExtensions.dll</span></span>  
  
    2.  <span data-ttu-id="0d26d-145">System.Activities.Presentation.dll</span><span class="sxs-lookup"><span data-stu-id="0d26d-145">System.Activities.Presentation.dll</span></span>  
  
    3.  <span data-ttu-id="0d26d-146">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="0d26d-146">System.ServiceModel.Activities.dll</span></span>  
  
17. <span data-ttu-id="0d26d-147">Otevřete soubor App.xaml a změňte hodnotu StartUpUri na "RehostingWFDesigner.xaml".</span><span class="sxs-lookup"><span data-stu-id="0d26d-147">Open the App.xaml file and change the value of the StartUpUri to "RehostingWFDesigner.xaml".</span></span>  
  
18. <span data-ttu-id="0d26d-148">Klikněte pravým tlačítkem na projekt UsingWorkflowItemPresenter **Průzkumníku řešení**, vyberte **přidat**, pak **novou položku...**</span><span class="sxs-lookup"><span data-stu-id="0d26d-148">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="0d26d-149">se zprovoznit **přidat novou položku** dialogový a vyberte **pracovního postupu** kategorie formuláře **nainstalovaných šablonách** na levé straně.</span><span class="sxs-lookup"><span data-stu-id="0d26d-149">to bring up the **Add New Item** dialogue and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>  
  
19. <span data-ttu-id="0d26d-150">Vyberte **Návrhář aktivity** šablony, pojmenujte ji `SimpleNativeDesigner`a klikněte na tlačítko **přidat**.</span><span class="sxs-lookup"><span data-stu-id="0d26d-150">Select the **Activity Designer** template, name it `SimpleNativeDesigner`, and click **Add**.</span></span>  
  
20. <span data-ttu-id="0d26d-151">Otevřete soubor SimpleNativeDesigner.xaml a vložte následující kód do ní.</span><span class="sxs-lookup"><span data-stu-id="0d26d-151">Open the SimpleNativeDesigner.xaml file and paste the following code into it.</span></span> <span data-ttu-id="0d26d-152">Poznámka: Tento kód používá <xref:System.Activities.Presentation.ActivityDesigner> jako kořenový element a ukazuje, jak vazby slouží k integraci <xref:System.Activities.Presentation.WorkflowItemPresenter> do vašeho návrháře tak podřízený typ zobrazený ve vaší Návrhář složené aktivity.</span><span class="sxs-lookup"><span data-stu-id="0d26d-152">Note this code uses <xref:System.Activities.Presentation.ActivityDesigner> as your root element and shows how binding is used to integrate <xref:System.Activities.Presentation.WorkflowItemPresenter> into your designer so a child type can be displayed in your composite activity designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d26d-153">Schéma pro <xref:System.Activities.Presentation.ActivityDesigner> lze přidat pouze jeden podřízený element pro návrháře definici vlastní aktivity; však může být tento prvek `StackPanel`, `Grid`, nebo některých jiných složený prvek uživatelského rozhraní.</span><span class="sxs-lookup"><span data-stu-id="0d26d-153">The schema for <xref:System.Activities.Presentation.ActivityDesigner> allows the addition of only one child element to your custom activity designer definition; however, this element could be a `StackPanel`, `Grid`, or some other composite UI element.</span></span>  
  
    ```xml  
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemPresenter.SimpleNativeDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
        <sap:ActivityDesigner.Resources>  
            <DataTemplate x:Key="Collapsed">  
                <StackPanel>  
                    <TextBlock>This is the collapsed view</TextBlock>  
                </StackPanel>  
            </DataTemplate>  
            <DataTemplate x:Key="Expanded">  
                <StackPanel>  
                    <TextBlock>Custom Text</TextBlock>  
                    <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
                                            HintText="Please drop an activity here" />  
                </StackPanel>  
            </DataTemplate>  
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
                <Style.Triggers>  
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                    </DataTrigger>  
                </Style.Triggers>  
            </Style>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />  
        </Grid>  
    </sap:ActivityDesigner>  
    ```  
  
21. <span data-ttu-id="0d26d-154">Klikněte pravým tlačítkem na projekt UsingWorkflowItemPresenter **Průzkumníku řešení**, vyberte **přidat**, pak **novou položku...**</span><span class="sxs-lookup"><span data-stu-id="0d26d-154">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="0d26d-155">se zprovoznit **přidat novou položku** dialogový a vyberte **pracovního postupu** kategorie formuláře **nainstalovaných šablonách** na levé straně.</span><span class="sxs-lookup"><span data-stu-id="0d26d-155">to bring up the **Add New Item** dialogue and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>  
  
22. <span data-ttu-id="0d26d-156">Vyberte **kód aktivity** šablony, pojmenujte ji `SimpleNativeActivity`a klikněte na tlačítko **přidat**.</span><span class="sxs-lookup"><span data-stu-id="0d26d-156">Select the  **Code Activity** template, name it `SimpleNativeActivity`, and click **Add**.</span></span>  
  
23. <span data-ttu-id="0d26d-157">Implementace `SimpleNativeActivity` třídy tak, že zadáte následující kód do souboru SimpleNativeActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="0d26d-157">Implement the `SimpleNativeActivity` class by entering the following code into the SimpleNativeActivity.cs file.</span></span>  
  
    ```  
    using System.Activities;  
  
    namespace UsingWorkflowItemPresenter  
    {  
        public sealed class SimpleNativeActivity : NativeActivity  
        {  
            // this property contains an activity that will be scheduled in the execute method  
    // the WorkflowItemPresenter in the designer is bound to this to enable editing  
    // of the value  
            public Activity Body { get; set; }  
  
            protected override void CacheMetadata(NativeActivityMetadata metadata)  
            {  
               metadata.AddChild(Body);  
               base.CacheMetadata(metadata);  
  
            }  
  
            protected override void Execute(NativeActivityContext context)  
            {  
                context.ScheduleActivity(Body);  
            }  
        }  
    }  
    ```  
  
24. <span data-ttu-id="0d26d-158">Vyberte **sestavit řešení** z **sestavení** nabídky.</span><span class="sxs-lookup"><span data-stu-id="0d26d-158">Select **Build Solution** from the **Build** menu.</span></span>  
  
25. <span data-ttu-id="0d26d-159">Vyberte **spustit bez ladění** z **ladění** chcete otevřít okno opětovné hostování nástroje vlastní návrh v nabídce.</span><span class="sxs-lookup"><span data-stu-id="0d26d-159">Select **Start Without Debugging** from the **Debug** menu to open the rehosted custom design window.</span></span>  
  
### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a><span data-ttu-id="0d26d-160">Chcete-li vytvořit vlastní aktivity návrháře pomocí WorkflowItemsPresenter</span><span class="sxs-lookup"><span data-stu-id="0d26d-160">To create a custom activity designer using WorkflowItemsPresenter</span></span>  
  
1.  <span data-ttu-id="0d26d-161">Postup pro druhý Návrhář vlastní aktivity se parallels první s několik změn, z nichž první je název aplikace druhý `UsingWorkflowItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="0d26d-161">The procedure for the second custom activity designer is the parallels the first with a few modifications, the first of which is to name the second application `UsingWorkflowItemsPresenter`.</span></span> <span data-ttu-id="0d26d-162">Tato aplikace také nedefinuje nové vlastní aktivity.</span><span class="sxs-lookup"><span data-stu-id="0d26d-162">Also this application does not define a new custom activity.</span></span>  
  
2.  <span data-ttu-id="0d26d-163">Hlavní rozdíly jsou obsažené v souborech CustomParallelDesigner.xaml a RehostingWFDesigner.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="0d26d-163">Key differences are contained in the CustomParallelDesigner.xaml and RehostingWFDesigner.xaml.cs files.</span></span> <span data-ttu-id="0d26d-164">Tady je kód od CustomParallelDesigne.xaml souboru, který definuje uživatelské rozhraní.</span><span class="sxs-lookup"><span data-stu-id="0d26d-164">Here is the code from the CustomParallelDesigne.xaml file that defines the UI.</span></span>  
  
    ```xml  
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemsPresenter.CustomParallelDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
        <sap:ActivityDesigner.Resources>  
            <DataTemplate x:Key="Collapsed">  
                <TextBlock>This is the Collapsed View</TextBlock>  
            </DataTemplate>  
            <DataTemplate x:Key="Expanded">  
                <StackPanel>  
                    <TextBlock HorizontalAlignment="Center">This is the</TextBlock>  
                    <TextBlock HorizontalAlignment="Center">extended view</TextBlock>  
                    <sap:WorkflowItemsPresenter HintText="Drop Activities Here"  
                                        Items="{Binding Path=ModelItem.Branches}">  
                        <sap:WorkflowItemsPresenter.SpacerTemplate>  
                            <DataTemplate>  
                                <Ellipse Width="10" Height="10" Fill="Black"/>  
                            </DataTemplate>  
                        </sap:WorkflowItemsPresenter.SpacerTemplate>  
                        <sap:WorkflowItemsPresenter.ItemsPanel>  
                            <ItemsPanelTemplate>  
                                <StackPanel Orientation="Horizontal"/>  
                            </ItemsPanelTemplate>  
                        </sap:WorkflowItemsPresenter.ItemsPanel>  
                    </sap:WorkflowItemsPresenter>  
                </StackPanel>  
            </DataTemplate>  
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
                <Style.Triggers>  
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                    </DataTrigger>  
                </Style.Triggers>  
            </Style>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>  
        </Grid>  
    </sap:ActivityDesigner>  
    ```  
  
3.  <span data-ttu-id="0d26d-165">Tady je kód od RehostingWFDesigner.xaml.cs souboru, který poskytuje rehosting logiku.</span><span class="sxs-lookup"><span data-stu-id="0d26d-165">Here is the code from the RehostingWFDesigner.xaml.cs file that provides the rehosting logic.</span></span>  
  
    ```  
    using System;  
    using System.Activities.Core.Presentation;  
    using System.Activities.Presentation;  
    using System.Activities.Presentation.Metadata;  
    using System.Activities.Statements;  
    using System.ComponentModel;  
    using System.Windows;  
  
    namespaceUsingWorkflowItemsPresenter  
    {  
        public partial class RehostingWfDesigner : Window  
        {  
            public RehostingWfDesigner()  
            {  
                InitializeComponent();  
            }  
  
            protected override void OnInitialized(EventArgs e)  
            {  
                base.OnInitialized(e);  
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0d26d-166">Viz také</span><span class="sxs-lookup"><span data-stu-id="0d26d-166">See Also</span></span>  
 <xref:System.Activities.Presentation.ActivityDesigner>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>  
 <xref:System.Activities.Presentation.WorkflowViewElement>  
 <xref:System.Activities.Presentation.Model.ModelItem>  
 [<span data-ttu-id="0d26d-167">Přizpůsobení prostředí návrhu pracovních postupů</span><span class="sxs-lookup"><span data-stu-id="0d26d-167">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)