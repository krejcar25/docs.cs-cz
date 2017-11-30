---
title: "Postupy: Přidání instalačních programů do aplikace služby"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 8137e41f92335849916dfc9e9ce72afeb186e73c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-installers-to-your-service-application"></a><span data-ttu-id="14b81-102">Postupy: Přidání instalačních programů do aplikace služby</span><span class="sxs-lookup"><span data-stu-id="14b81-102">How to: Add Installers to Your Service Application</span></span>
<span data-ttu-id="14b81-103">Visual Studio se dodává instalace součásti, které můžete nainstalovat prostředky přidružené k vaší aplikace služby.</span><span class="sxs-lookup"><span data-stu-id="14b81-103">Visual Studio ships installation components that can install resources associated with your service applications.</span></span> <span data-ttu-id="14b81-104">Součásti instalace registraci jednotlivých služeb v systému, ke které se instaluje a umožní správci řízení služeb vědět, že služba existuje.</span><span class="sxs-lookup"><span data-stu-id="14b81-104">Installation components register an individual service on the system to which it is being installed and let the Services Control Manager know that the service exists.</span></span> <span data-ttu-id="14b81-105">Pokud pracujete s aplikací služby, můžete vybrat odkaz v okně vlastností a automaticky tak přidejte příslušné instalační programy do projektu.</span><span class="sxs-lookup"><span data-stu-id="14b81-105">When you work with a service application, you can select a link in the Properties window to automatically add the appropriate installers to your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14b81-106">Hodnoty vlastností pro vaši službu jsou kopírovány z třídu služby k třídě Instalační služby.</span><span class="sxs-lookup"><span data-stu-id="14b81-106">Property values for your service are copied from the service class to the installer class.</span></span> <span data-ttu-id="14b81-107">Pokud aktualizujete hodnoty vlastností v třídě služby, nejsou automaticky aktualizovány v instalačním programu.</span><span class="sxs-lookup"><span data-stu-id="14b81-107">If you update the property values on the service class, they are not automatically updated in the installer.</span></span>  
  
 <span data-ttu-id="14b81-108">Když přidáte do projektu novou třídu instalační program (který ve výchozím názvem `ProjectInstaller`) je vytvořen v projektu a instancí odpovídající instalace součásti jsou vytvořené v něm.</span><span class="sxs-lookup"><span data-stu-id="14b81-108">When you add an installer to your project, a new class (which, by default, is named `ProjectInstaller`) is created in the project, and instances of the appropriate installation components are created within it.</span></span> <span data-ttu-id="14b81-109">Tato třída slouží jako centrální bod pro všechny součásti instalace je třeba projekt.</span><span class="sxs-lookup"><span data-stu-id="14b81-109">This class acts as a central point for all of the installation components your project needs.</span></span> <span data-ttu-id="14b81-110">Například pokud přidat druhý službu do vaší aplikace a klikněte na odkaz přidat instalační program, druhý instalační program třída není vytvořena; Místo toho je nezbytné další instalace součásti pro službu druhý přidat do existující třídy.</span><span class="sxs-lookup"><span data-stu-id="14b81-110">For example, if you add a second service to your application and click the Add Installer link, a second installer class is not created; instead, the necessary additional installation component for the second service is added to the existing class.</span></span>  
  
 <span data-ttu-id="14b81-111">Nemusíte dělat žádné zvláštní kódování v rámci instalační programy, aby vaše služby správně nainstalovány.</span><span class="sxs-lookup"><span data-stu-id="14b81-111">You do not need to do any special coding within the installers to make your services install correctly.</span></span> <span data-ttu-id="14b81-112">Však může občas potřebujete upravit obsah instalační programy, pokud je nutné přidat zvláštní funkce do procesu instalace.</span><span class="sxs-lookup"><span data-stu-id="14b81-112">However, you may occasionally need to modify the contents of the installers if you need to add special functionality to the installation process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14b81-113">Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.</span><span class="sxs-lookup"><span data-stu-id="14b81-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="14b81-114">Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky.</span><span class="sxs-lookup"><span data-stu-id="14b81-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="14b81-115">Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="14b81-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-installers-to-your-service-application"></a><span data-ttu-id="14b81-116">K přidání instalačních programů do aplikace služby</span><span class="sxs-lookup"><span data-stu-id="14b81-116">To add installers to your service application</span></span>  
  
1.  <span data-ttu-id="14b81-117">V **Průzkumníku řešení**, přístup **návrhu** zobrazení pro danou službu, pro který chcete přidat součást instalace.</span><span class="sxs-lookup"><span data-stu-id="14b81-117">In **Solution Explorer**, access **Design** view for the service for which you want to add an installation component.</span></span>  
  
2.  <span data-ttu-id="14b81-118">Klikněte na pozadí návrháře vybrat službu sám sebe, než všechny její obsah.</span><span class="sxs-lookup"><span data-stu-id="14b81-118">Click the background of the designer to select the service itself, rather than any of its contents.</span></span>  
  
3.  <span data-ttu-id="14b81-119">Pomocí návrháře fokus, klikněte pravým tlačítkem a pak klikněte na **přidat instalační program**.</span><span class="sxs-lookup"><span data-stu-id="14b81-119">With the designer in focus, right-click, and then click **Add Installer**.</span></span>  
  
     <span data-ttu-id="14b81-120">Novou třídu, `ProjectInstaller`a dvě součásti instalace <xref:System.ServiceProcess.ServiceProcessInstaller> a <xref:System.ServiceProcess.ServiceInstaller>, jsou přidány do projektu a hodnoty vlastností pro službu se zkopírují do komponenty.</span><span class="sxs-lookup"><span data-stu-id="14b81-120">A new class, `ProjectInstaller`, and two installation components, <xref:System.ServiceProcess.ServiceProcessInstaller> and <xref:System.ServiceProcess.ServiceInstaller>, are added to your project, and property values for the service are copied to the components.</span></span>  
  
4.  <span data-ttu-id="14b81-121">Klikněte na tlačítko <xref:System.ServiceProcess.ServiceInstaller> součásti a ověřte, že hodnota <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> je nastavena na stejnou hodnotu jako <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> vlastnost na samotnou službu.</span><span class="sxs-lookup"><span data-stu-id="14b81-121">Click the <xref:System.ServiceProcess.ServiceInstaller> component and verify that the value of the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to the same value as the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property on the service itself.</span></span>  
  
5.  <span data-ttu-id="14b81-122">Chcete-li zjistit, jak bude vaše služba spuštěna, klikněte na tlačítko <xref:System.ServiceProcess.ServiceInstaller> součásti a nastavené <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> vlastnost na odpovídající hodnotu.</span><span class="sxs-lookup"><span data-stu-id="14b81-122">To determine how your service will be started, click the <xref:System.ServiceProcess.ServiceInstaller> component and set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to the appropriate value.</span></span>  
  
    |<span data-ttu-id="14b81-123">Hodnota</span><span class="sxs-lookup"><span data-stu-id="14b81-123">Value</span></span>|<span data-ttu-id="14b81-124">Výsledek</span><span class="sxs-lookup"><span data-stu-id="14b81-124">Result</span></span>|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|<span data-ttu-id="14b81-125">Služba je třeba spustit ručně, po instalaci.</span><span class="sxs-lookup"><span data-stu-id="14b81-125">The service must be manually started after installation.</span></span> <span data-ttu-id="14b81-126">Další informace najdete v tématu [postupy: spuštění služby](../../../docs/framework/windows-services/how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="14b81-126">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|<span data-ttu-id="14b81-127">Služba se spustí sám o sobě vždy, když je počítač se restartuje.</span><span class="sxs-lookup"><span data-stu-id="14b81-127">The service will start by itself whenever the computer reboots.</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|<span data-ttu-id="14b81-128">Službu nelze spustit.</span><span class="sxs-lookup"><span data-stu-id="14b81-128">The service cannot be started.</span></span>|  
  
6.  <span data-ttu-id="14b81-129">Chcete-li určit kontext zabezpečení, ve které vaše služba bude spuštěna, klikněte na tlačítko <xref:System.ServiceProcess.ServiceProcessInstaller> součásti a nastavte hodnoty odpovídající vlastnost.</span><span class="sxs-lookup"><span data-stu-id="14b81-129">To determine the security context in which your service will run, click the <xref:System.ServiceProcess.ServiceProcessInstaller> component and set the appropriate property values.</span></span> <span data-ttu-id="14b81-130">Další informace najdete v tématu [postupy: určení kontextu zabezpečení pro služby](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span><span class="sxs-lookup"><span data-stu-id="14b81-130">For more information, see [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span></span>  
  
7.  <span data-ttu-id="14b81-131">Přepište všechny metody, pro které je třeba provést vlastní zpracování.</span><span class="sxs-lookup"><span data-stu-id="14b81-131">Override any methods for which you need to perform custom processing.</span></span>  
  
8.  <span data-ttu-id="14b81-132">Proveďte kroky 1 až 7 pro každý další služby ve vašem projektu.</span><span class="sxs-lookup"><span data-stu-id="14b81-132">Perform steps 1 through 7 for each additional service in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14b81-133">U každé další služby ve vašem projektu, je nutné přidat další <xref:System.ServiceProcess.ServiceInstaller> komponentu do projektu `ProjectInstaller` třídy.</span><span class="sxs-lookup"><span data-stu-id="14b81-133">For each additional service in your project, you must add an additional <xref:System.ServiceProcess.ServiceInstaller> component to the project's `ProjectInstaller` class.</span></span> <span data-ttu-id="14b81-134"><xref:System.ServiceProcess.ServiceProcessInstaller> Součást přidali v kroku tři funguje se všemi instalační programy jednotlivé služby v projektu.</span><span class="sxs-lookup"><span data-stu-id="14b81-134">The <xref:System.ServiceProcess.ServiceProcessInstaller> component added in step three works with all of the individual service installers in the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b81-135">Viz také</span><span class="sxs-lookup"><span data-stu-id="14b81-135">See Also</span></span>  
 [<span data-ttu-id="14b81-136">Úvod do aplikace služby systému Windows</span><span class="sxs-lookup"><span data-stu-id="14b81-136">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="14b81-137">Postupy: instalace a odinstalace služeb</span><span class="sxs-lookup"><span data-stu-id="14b81-137">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="14b81-138">Postupy: spuštění služeb</span><span class="sxs-lookup"><span data-stu-id="14b81-138">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="14b81-139">Postupy: určení kontextu zabezpečení pro služby</span><span class="sxs-lookup"><span data-stu-id="14b81-139">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)