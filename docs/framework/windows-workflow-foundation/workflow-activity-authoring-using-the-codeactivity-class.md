---
title: "Používání třídy CodeActivity vytváření aktivit pracovního postupu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f9894926ba93461d332eaac248c71d20ea4e7d30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a><span data-ttu-id="6634b-102">Používání třídy CodeActivity vytváření aktivit pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="6634b-102">Workflow Activity Authoring Using the CodeActivity Class</span></span>
<span data-ttu-id="6634b-103">Aktivity vytvořené pomocí dědění z <xref:System.Activities.CodeActivity> můžete implementovat základní imperativní chování přepsáním <xref:System.Activities.CodeActivity.Execute%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="6634b-103">Activities created by inheriting from <xref:System.Activities.CodeActivity> can implement basic imperative behavior by overriding the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>  
  
## <a name="using-codeactivitycontext"></a><span data-ttu-id="6634b-104">Pomocí CodeActivityContext</span><span class="sxs-lookup"><span data-stu-id="6634b-104">Using CodeActivityContext</span></span>  
 <span data-ttu-id="6634b-105">Funkce modulu runtime pracovního postupu je přístupná prostřednictvím <xref:System.Activities.CodeActivity.Execute%2A> metoda pomocí členy `context` parametr typu <xref:System.Activities.CodeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="6634b-105">Features of the workflow runtime can be accessed from within the <xref:System.Activities.CodeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="6634b-106">Funkcí dostupných prostřednictvím <xref:System.Activities.CodeActivityContext> patří:</span><span class="sxs-lookup"><span data-stu-id="6634b-106">The features available through <xref:System.Activities.CodeActivityContext> include the following:</span></span>  
  
-   <span data-ttu-id="6634b-107">Získání a nastavení hodnoty proměnné a argumenty.</span><span class="sxs-lookup"><span data-stu-id="6634b-107">Getting and setting the values of variables and arguments.</span></span>  
  
-   <span data-ttu-id="6634b-108">Vlastní sledování funkce pomocí <xref:System.Activities.CodeActivityContext.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="6634b-108">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>  
  
-   <span data-ttu-id="6634b-109">Přístup k vlastnostem provádění aktivity pomocí <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="6634b-109">Access to the activity’s execution properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span></span>  
  
#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a><span data-ttu-id="6634b-110">Chcete-li vytvořit vlastní aktivitu, která dědí z CodeActivity</span><span class="sxs-lookup"><span data-stu-id="6634b-110">To create a custom activity that inherits from CodeActivity</span></span>  
  
1.  <span data-ttu-id="6634b-111">Otevřete[!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6634b-111">Open[!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="6634b-112">Vyberte **soubor**, **nové**a potom **projektu**.</span><span class="sxs-lookup"><span data-stu-id="6634b-112">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="6634b-113">Vyberte **Workflow 4.0** pod **Visual C#** v **typy projektů** a vyberte **v2010** uzlu.</span><span class="sxs-lookup"><span data-stu-id="6634b-113">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="6634b-114">Vyberte **knihovna aktivit** v **šablony** okno.</span><span class="sxs-lookup"><span data-stu-id="6634b-114">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="6634b-115">Název nového projektu HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="6634b-115">Name the new project HelloActivity.</span></span>  
  
3.  <span data-ttu-id="6634b-116">Klikněte pravým tlačítkem na Activity1.xaml v HelloActivity projektu a vyberte **odstranit**.</span><span class="sxs-lookup"><span data-stu-id="6634b-116">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="6634b-117">Klikněte pravým tlačítkem na projekt HelloActivity a vyberte **přidat** a potom **třída**.</span><span class="sxs-lookup"><span data-stu-id="6634b-117">Right-click the HelloActivity project and select **Add** , and then **Class**.</span></span> <span data-ttu-id="6634b-118">Pojmenujte novou třídu HelloActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="6634b-118">Name the new class HelloActivity.cs.</span></span>  
  
5.  <span data-ttu-id="6634b-119">V souboru HelloActivity.cs, přidejte následující `using` direktivy.</span><span class="sxs-lookup"><span data-stu-id="6634b-119">In the HelloActivity.cs file, add the following `using` directives.</span></span>  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  <span data-ttu-id="6634b-120">Ujistěte se, nové třídy dědí <xref:System.Activities.CodeActivity> přidáním základní třídu pro deklaraci třídy.</span><span class="sxs-lookup"><span data-stu-id="6634b-120">Make the new class inherit from <xref:System.Activities.CodeActivity> by adding a base class to the class declaration.</span></span>  
  
    ```csharp  
    class HelloActivity : CodeActivity  
    ```  
  
7.  <span data-ttu-id="6634b-121">Přidání funkce do třídy přidáním <xref:System.Activities.CodeActivity.Execute%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="6634b-121">Add functionality to the class by adding an <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  <span data-ttu-id="6634b-122">Použití <xref:System.Activities.CodeActivityContext> vytvoření záznamu sledování.</span><span class="sxs-lookup"><span data-stu-id="6634b-122">Use the <xref:System.Activities.CodeActivityContext> to create a tracking record.</span></span>  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");  
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));  
        context.Track(record);  
    }  
    ```