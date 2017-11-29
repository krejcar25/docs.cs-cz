---
title: "Postupy: Hostování služby pracovního procesu pomocí Windows Server App Fabric"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 69911b2baf0e184957158ac536fa2271524cb2ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-a-workflow-service-with-windows-server-app-fabric"></a><span data-ttu-id="49fef-102">Postupy: Hostování služby pracovního procesu pomocí Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="49fef-102">How to: Host a Workflow Service with Windows Server App Fabric</span></span>
<span data-ttu-id="49fef-103">Hostování služeb pracovních postupů v App Fabric je podobná hostování v rámci služby IIS / byla.</span><span class="sxs-lookup"><span data-stu-id="49fef-103">Hosting workflow services in App Fabric is similar to hosting under IIS/WAS.</span></span> <span data-ttu-id="49fef-104">Jediným rozdílem je, nástroje, které poskytuje App Fabric pro nasazení, monitorování a správu služeb pracovních postupů.</span><span class="sxs-lookup"><span data-stu-id="49fef-104">The only difference is the tools App Fabric provides for deploying, monitoring, and managing workflow services.</span></span> <span data-ttu-id="49fef-105">Toto téma používá služby pracovního postupu, které jsou vytvořené v [vytvoření dlouhodobé služby pracovního postupu](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md).</span><span class="sxs-lookup"><span data-stu-id="49fef-105">This topic uses the workflow service created in the [Creating a Long-running Workflow Service](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md).</span></span> <span data-ttu-id="49fef-106">Toto téma vás procesem vytvoření služby pracovních postupů.</span><span class="sxs-lookup"><span data-stu-id="49fef-106">That topic will walk you through creating a workflow service.</span></span> <span data-ttu-id="49fef-107">Toto téma vysvětluje, jak hostitele služby pracovního postupu pomocí App Fabric.</span><span class="sxs-lookup"><span data-stu-id="49fef-107">This topic will explain how to host the workflow service using App Fabric.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="49fef-108">Windows Server App Fabric, najdete v části [dokumentaci systému Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="49fef-108"> Windows Server App Fabric, see [Windows Server App Fabric Documentation](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409).</span></span> <span data-ttu-id="49fef-109">Před dokončením následujících kroků zkontrolujte, zda že máte nainstalovaný Windows Server App Fabric.</span><span class="sxs-lookup"><span data-stu-id="49fef-109">Before completing the steps below make sure you have Windows Server App Fabric installed.</span></span>  <span data-ttu-id="49fef-110">Pokud chcete provést tuto, otevřete si Internetová informační služba (inetmgr.exe), klikněte na název serveru v **připojení** zobrazení, klikněte na tlačítko weby a klikněte na **Default Web Site**.</span><span class="sxs-lookup"><span data-stu-id="49fef-110">To do this open up Internet Information Services (inetmgr.exe), click your server name in the **Connections** view, click Sites, and click **Default Web Site**.</span></span> <span data-ttu-id="49fef-111">Na pravé straně obrazovky byste měli vidět části s názvem **App Fabric**.</span><span class="sxs-lookup"><span data-stu-id="49fef-111">In the right-hand side of the screen you should see a section called **App Fabric**.</span></span> <span data-ttu-id="49fef-112">Pokud nevidíte v této části (je nahoře v pravém podokně) nemáte App Fabric nainstalována.</span><span class="sxs-lookup"><span data-stu-id="49fef-112">If you don’t see this section (it will be on the top of the right-hand pane) you do not have App Fabric installed.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="49fef-113">instalace systému Windows Server App Fabric najdete v části [instalace systému Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193136).</span><span class="sxs-lookup"><span data-stu-id="49fef-113"> installing Windows Server App Fabric see [Installing Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193136).</span></span>  
  
### <a name="creating-a-simple-workflow-service"></a><span data-ttu-id="49fef-114">Vytvoření jednoduchého pracovního postupu služby</span><span class="sxs-lookup"><span data-stu-id="49fef-114">Creating a Simple Workflow Service</span></span>  
  
1.  <span data-ttu-id="49fef-115">Otevřete [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] a načtení OrderProcessing řešení, kterou jste vytvořili v [vytvoření dlouhodobé služby pracovního postupu](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="49fef-115">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and load the OrderProcessing solution you created in the [Creating a Long-running Workflow Service](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md) topic.</span></span>  
  
2.  <span data-ttu-id="49fef-116">Klikněte pravým tlačítkem **OrderService** projektu a vyberte **vlastnosti** a vyberte **webové** kartě.</span><span class="sxs-lookup"><span data-stu-id="49fef-116">Right click the **OrderService** project and select **Properties** and select the **Web** tab.</span></span>  
  
3.  <span data-ttu-id="49fef-117">V **spustit akci** část na stránku vlastností vyberte **konkrétní stránky** a do textového pole zadejte Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="49fef-117">In the **Start Action** section of the property page select **Specific Page** and type Service1.xamlx in the edit box.</span></span>  
  
4.  <span data-ttu-id="49fef-118">V **servery** část na stránku vlastností vyberte **použití místního webového serveru IIS** a zadejte následující adresu URL: `http://localhost/OrderService`.</span><span class="sxs-lookup"><span data-stu-id="49fef-118">In the **Servers** section of the property page select **Use Local IIS Web Server** and type in the following URL: `http://localhost/OrderService`.</span></span>  
  
5.  <span data-ttu-id="49fef-119">Klikněte **vytvořit virtuální adresář** tlačítko.</span><span class="sxs-lookup"><span data-stu-id="49fef-119">Click the **Create Virtual Directory** button.</span></span> <span data-ttu-id="49fef-120">To se vytvořit nový virtuální adresář a nastavení projektu při sestavení projektu zkopírovat potřebné soubory do virtuálního adresáře.</span><span class="sxs-lookup"><span data-stu-id="49fef-120">This will create a new virtual directory and set up the project to copy the needed files to the virtual directory when the project is built.</span></span>  <span data-ttu-id="49fef-121">Případně může ručně zkopírujete .xamlx, soubor web.config a všechny potřebné knihovny DLL do virtuálního adresáře.</span><span class="sxs-lookup"><span data-stu-id="49fef-121">Alternatively you could manually copy the .xamlx, the web.config, and any needed DLLs to the virtual directory.</span></span>  
  
### <a name="configuring-a-workflow-service-hosted-in-windows-server-app-fabric"></a><span data-ttu-id="49fef-122">Konfigurace pracovního postupu služby hostované v systému Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="49fef-122">Configuring a Workflow Service Hosted in Windows Server App Fabric</span></span>  
  
1.  <span data-ttu-id="49fef-123">Otevřete Správce Internetové informační služby (inetmgr.exe).</span><span class="sxs-lookup"><span data-stu-id="49fef-123">Open Internet Information Services Manager (inetmgr.exe).</span></span>  
  
2.  <span data-ttu-id="49fef-124">Přejděte do virtuálního adresáře OrderService v **připojení** podokně.</span><span class="sxs-lookup"><span data-stu-id="49fef-124">Navigate to the OrderService virtual directory in the **Connections** pane.</span></span>  
  
3.  <span data-ttu-id="49fef-125">Klikněte pravým tlačítkem na OrderService a vyberte **spravovat WCF a WF služby**, **konfigurace...** .</span><span class="sxs-lookup"><span data-stu-id="49fef-125">Right click OrderService and select **Manage WCF and WF Services**, **Configure…**.</span></span> <span data-ttu-id="49fef-126">**Konfigurace WCF a WF pro aplikaci** se zobrazí dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="49fef-126">The **Configure WCF and WF for Application** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="49fef-127">Vyberte **Obecné** kartě chcete zobrazit obecné informace o aplikaci, jak je znázorněno na následujícím snímku obrazovky.</span><span class="sxs-lookup"><span data-stu-id="49fef-127">Select the **General** tab to display general information about the application as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="49fef-128">![Karta Obecné, dialogové okno Konfigurace prostředků infrastruktury aplikace](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-general.gif "AppFabricConfiguration – obecné")</span><span class="sxs-lookup"><span data-stu-id="49fef-128">![General tab of the App Fabric Configuration dialog](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-general.gif "AppFabricConfiguration-General")</span></span>  
  
5.  <span data-ttu-id="49fef-129">Vyberte **monitorování** kartě. Ukazuje to různá nastavení monitorování, jak je znázorněno na následujícím snímku obrazovky.</span><span class="sxs-lookup"><span data-stu-id="49fef-129">Select the **Monitoring** tab. This shows various monitoring settings as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="49fef-130">![Aplikace monitorování konfigurace infrastruktury karta](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration monitorování")</span><span class="sxs-lookup"><span data-stu-id="49fef-130">![App Fabric Configuration Monitoring tab](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration-Monitoring")</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="49fef-131">Konfigurace pracovního postupu služby monitorování v nástroji App Fabric najdete v části [konfiguraci monitorování pomocí App Fabric](http://go.microsoft.com/fwlink/?LinkId=193153).</span><span class="sxs-lookup"><span data-stu-id="49fef-131"> configuring workflow service monitoring in App Fabric see [Configuring monitoring with App Fabric](http://go.microsoft.com/fwlink/?LinkId=193153).</span></span>  
  
6.  <span data-ttu-id="49fef-132">Vyberte **pracovního postupu trvalost** kartě. To umožňuje konfiguraci aplikace na použití App Fabric výchozí trvalost poskytovatele, jak je znázorněno na následujícím snímku obrazovky.</span><span class="sxs-lookup"><span data-stu-id="49fef-132">Select the **Workflow Persistence** tab. This allows you to configure your application to use App Fabric’s default persistence provider as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="49fef-133">![Konfigurace infrastruktury aplikace & č. 45; Trvalost](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-persistence.gif "AppFabricConfiguration trvalost")</span><span class="sxs-lookup"><span data-stu-id="49fef-133">![App Fabric Configuration &#45; Persistence](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-persistence.gif "AppFabricConfiguration-Persistence")</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="49fef-134">Konfigurace trvalosti pracovního postupu v systému Windows Server App Fabric najdete v části [konfigurace trvalosti pracovního postupu v App Fabric](http://go.microsoft.com/fwlink/?LinkId=193148).</span><span class="sxs-lookup"><span data-stu-id="49fef-134"> configuring workflow persistence in Windows Server App Fabric see [Configuring Workflow Persistence in App Fabric](http://go.microsoft.com/fwlink/?LinkId=193148).</span></span>  
  
7.  <span data-ttu-id="49fef-135">Vyberte **správu hostitele pracovního postupu** kartě. Můžete určit, když instance služby nečinnosti pracovního postupu by měla být uvolněna a jako trvalý, jak je znázorněno na následujícím snímku obrazovky.</span><span class="sxs-lookup"><span data-stu-id="49fef-135">Select the **Workflow Host Management** tab. This allows you to specify when idle workflow service instances should be unloaded and persisted as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="49fef-136">![Správa hostitele pracovního postupu konfigurace App Fabric](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-management.gif "AppFabricConfiguration-Management")</span><span class="sxs-lookup"><span data-stu-id="49fef-136">![App Fabric Configuration  Workflow Host Management](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-management.gif "AppFabricConfiguration-Management")</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="49fef-137">viz konfigurace správy hostitele pracovního postupu [konfigurace správy hostitele pracovního postupu v App Fabric](http://go.microsoft.com/fwlink/?LinkId=193151).</span><span class="sxs-lookup"><span data-stu-id="49fef-137"> workflow host management configuration see [Configuring Workflow Host Management in App Fabric](http://go.microsoft.com/fwlink/?LinkId=193151).</span></span>  
  
8.  <span data-ttu-id="49fef-138">Vyberte **automatického spuštění** kartě. To umožňuje určit nastavení automatického spouštění služby pracovních postupů v aplikaci, jak je znázorněno na následujícím snímku obrazovky.</span><span class="sxs-lookup"><span data-stu-id="49fef-138">Select the **Auto-Start** tab. This allows you to specify auto-start settings for the workflow services in the application as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="49fef-139">![Aplikace Fabric automaticky & č. 45; počáteční konfigurace](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationautostart.gif "AppFabricConfigurationAutostart")</span><span class="sxs-lookup"><span data-stu-id="49fef-139">![App Fabric Auto&#45;start configuration](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationautostart.gif "AppFabricConfigurationAutostart")</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="49fef-140">Konfigurace automatického spouštění najdete v části [konfigurace automatického – spuštění pomocí App Fabric](http://go.microsoft.com/fwlink/?LinkId=193150).</span><span class="sxs-lookup"><span data-stu-id="49fef-140"> configuring Auto-Start see [Configuring Auto-Start with App Fabric](http://go.microsoft.com/fwlink/?LinkId=193150).</span></span>  
  
9. <span data-ttu-id="49fef-141">Vyberte **omezování** kartě. To umožňuje konfigurovat nastavení omezení pro službu pracovní postup, jak je znázorněno na následujícím snímku obrazovky.</span><span class="sxs-lookup"><span data-stu-id="49fef-141">Select the **Throttling** tab. This allows you to configure throttling settings for the workflow service as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="49fef-142">![Omezení configuration App Fabric](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationthrottling.gif "AppFabricConfigurationThrottling")</span><span class="sxs-lookup"><span data-stu-id="49fef-142">![App Fabric configuration throttling](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationthrottling.gif "AppFabricConfigurationThrottling")</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="49fef-143">Konfigurace omezení najdete v části [konfigurace omezování pomocí App Fabric](http://go.microsoft.com/fwlink/?LinkId=193149).</span><span class="sxs-lookup"><span data-stu-id="49fef-143"> configuring throttling see [Configuring Throttling with App Fabric](http://go.microsoft.com/fwlink/?LinkId=193149).</span></span>  
  
10. <span data-ttu-id="49fef-144">Vyberte **zabezpečení** kartě. To umožňuje konfigurovat nastavení zabezpečení pro aplikace, jak je znázorněno na následujícím snímku obrazovky.</span><span class="sxs-lookup"><span data-stu-id="49fef-144">Select the **Security** tab. This allows you to configure security settings for the application as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="49fef-145">![Konfigurace zabezpečení aplikace infrastruktury](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-security.gif "AppFabricConfiguration zabezpečení")</span><span class="sxs-lookup"><span data-stu-id="49fef-145">![App Fabric Security Configuration](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-security.gif "AppFabricConfiguration-Security")</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="49fef-146">Konfigurace zabezpečení pomocí systému Windows Server App Fabric najdete v části [konfigurace zabezpečení s App Fabric](http://go.microsoft.com/fwlink/?LinkId=193152).</span><span class="sxs-lookup"><span data-stu-id="49fef-146"> configuring security with Windows Server App Fabric see [Configuring Security with App Fabric](http://go.microsoft.com/fwlink/?LinkId=193152).</span></span>  
  
### <a name="using-windows-server-app-fabric"></a><span data-ttu-id="49fef-147">Pomocí Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="49fef-147">Using Windows Server App Fabric</span></span>  
  
1.  <span data-ttu-id="49fef-148">Sestavte řešení zkopírovat potřebné soubory do virtuálního adresáře.</span><span class="sxs-lookup"><span data-stu-id="49fef-148">Build the solution to copy the necessary files to the virtual directory.</span></span>  
  
2.  <span data-ttu-id="49fef-149">Klikněte pravým tlačítkem na projekt OrderClient a vyberte **ladění**, **spustit novou instanci** spustit klientskou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="49fef-149">Right click the OrderClient project and select **Debug**, **Start New Instance** to launch the client application.</span></span>  
  
3.  <span data-ttu-id="49fef-150">Klient spustí a Visual Studio se zobrazí **připojit upozornění zabezpečení** dialogové okno, klikněte na tlačítko **nemáte připojení** tlačítko.</span><span class="sxs-lookup"><span data-stu-id="49fef-150">The client will run and Visual Studio will display an **Attach Security Warning** dialog box, click the **Don’t Attach** button.</span></span> <span data-ttu-id="49fef-151">Tato hodnota informuje Visual Studio není připojit k procesu služby IIS pro ladění.</span><span class="sxs-lookup"><span data-stu-id="49fef-151">This tells Visual Studio to not attach to the IIS process for debugging.</span></span>  
  
4.  <span data-ttu-id="49fef-152">Klientská aplikace bude okamžitě volání služby pracovního postupu a potom počkejte, než.</span><span class="sxs-lookup"><span data-stu-id="49fef-152">The client application will immediately call the Workflow service and then wait.</span></span> <span data-ttu-id="49fef-153">Služby pracovních postupů přejde nečinnosti a nastavit jako trvalý.</span><span class="sxs-lookup"><span data-stu-id="49fef-153">The workflow service will go idle and be persisted.</span></span> <span data-ttu-id="49fef-154">Můžete to ověřit spuštěním Internetová informační služba (inetmgr.exe), nejde přejít ke OrderService v podokně připojení a ho vyberete.</span><span class="sxs-lookup"><span data-stu-id="49fef-154">You can verify this by starting Internet Information Services (inetmgr.exe), navigating to the OrderService in the Connections pane and selecting it.</span></span> <span data-ttu-id="49fef-155">Potom klikněte na ikonu řídicí panel infrastruktury aplikace v pravém podokně.</span><span class="sxs-lookup"><span data-stu-id="49fef-155">Next, click the App Fabric Dashboard icon in the right-hand pane.</span></span> <span data-ttu-id="49fef-156">V rámci instance pracovního postupu jako trvalý, uvidíte, že existuje jedna instance služby pracovního postupu trvalou jak je znázorněno na následujícím snímku obrazovky.</span><span class="sxs-lookup"><span data-stu-id="49fef-156">Under Persisted WF Instances you will see there is one persisted workflow service instance as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="49fef-157">![Řídicí panel infrastruktury aplikace](../../../../docs/framework/wcf/feature-details/media/appfabricdashboard.gif "AppFabricDashboard")</span><span class="sxs-lookup"><span data-stu-id="49fef-157">![App Fabric Dashboard](../../../../docs/framework/wcf/feature-details/media/appfabricdashboard.gif "AppFabricDashboard")</span></span>  
  
     <span data-ttu-id="49fef-158">**WF Instance historie** uvádí informace týkající se služby pracovního postupu, například počet aktivací služby pracovního postupu, počet dokončených instance služby pracovního postupu a počet instancí pracovního postupu s chybami.</span><span class="sxs-lookup"><span data-stu-id="49fef-158">The **WF Instance History** lists information about the workflow service such as the number of workflow service activations, the number of workflow service instance completions, and the number of workflow instances with failures.</span></span> <span data-ttu-id="49fef-159">Pod aktivní a nečinnosti instance, které se zobrazí odkaz kliknutím na odkaz zobrazíte další informace o instancích nečinnosti pracovní postup, jak je znázorněno na následujícím snímku obrazovky.</span><span class="sxs-lookup"><span data-stu-id="49fef-159">Under Active or Idle instances a link will be displayed, clicking on the link will display more information about the idle workflow instances as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="49fef-160">![Trvalé podrobnosti Instance pracovního postupu](../../../../docs/framework/wcf/feature-details/media/persisteddetail.gif "PersistedDetail")</span><span class="sxs-lookup"><span data-stu-id="49fef-160">![Persisted Workflow Instance Details](../../../../docs/framework/wcf/feature-details/media/persisteddetail.gif "PersistedDetail")</span></span>  
  
     <span data-ttu-id="49fef-161">Další informace o systému Windows Server App Fabric funkcí a jejich použití najdete v části [hostování funkce systému Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=193143&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="49fef-161">For more information about Windows Server App Fabric features and how to use them see [Windows Server App Fabric Hosting Features](http://go.microsoft.com/fwlink/?LinkID=193143&clcid=0x409)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fef-162">Viz také</span><span class="sxs-lookup"><span data-stu-id="49fef-162">See Also</span></span>  
 [<span data-ttu-id="49fef-163">Vytvoření dlouhodobé služby pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="49fef-163">Creating a Long-running Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)  
 [<span data-ttu-id="49fef-164">Hostování funkcí systému Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="49fef-164">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=193143)  
 [<span data-ttu-id="49fef-165">Instalace systému Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="49fef-165">Installing Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=193136)  
 [<span data-ttu-id="49fef-166">Dokumentaci k systému Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="49fef-166">Windows Server App Fabric Documentation</span></span>](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409)