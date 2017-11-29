---
title: Konfigurace podpory protokolu WS-AT (WS-Atomic Transactions)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WS-AT protocol [WCF], configuring WS-Atomic Transaction
ms.assetid: cb9f1c9c-1439-4172-b9bc-b01c3e09ac48
caps.latest.revision: "31"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5f03f39a58a574587aba09023c1d482debe31947
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-ws-atomic-transaction-support"></a><span data-ttu-id="9c44a-102">Konfigurace podpory protokolu WS-AT (WS-Atomic Transactions)</span><span class="sxs-lookup"><span data-stu-id="9c44a-102">Configuring WS-Atomic Transaction Support</span></span>
<span data-ttu-id="9c44a-103">Toto téma popisuje, jak můžete nakonfigurovat podporu protokolu WS-AtomicTransaction (WS-AT) pomocí nástroje Konfigurace služby WS-AT.</span><span class="sxs-lookup"><span data-stu-id="9c44a-103">This topic describes how you can configure WS-AtomicTransaction (WS-AT) support by using the WS-AT Configuration Utility.</span></span>  
  
## <a name="using-the-ws-at-configuration-utility"></a><span data-ttu-id="9c44a-104">Pomocí nástroje pro konfiguraci služby WS-AT</span><span class="sxs-lookup"><span data-stu-id="9c44a-104">Using the WS-AT Configuration Utility</span></span>  
 <span data-ttu-id="9c44a-105">Nástroj WS-AT Configuration Utility (wsatConfig.exe) se používá ke konfiguraci nastavení služby WS-AT.</span><span class="sxs-lookup"><span data-stu-id="9c44a-105">The WS-AT Configuration Utility (wsatConfig.exe) is used to configure WS-AT settings.</span></span> <span data-ttu-id="9c44a-106">Chcete-li povolit službu protokolu WS-AT, musíte použít nástroj pro konfiguraci ke konfiguraci HTTPS port pro WS-AT, vazbu certifikátu X.509. certifikát na HTTPS port a konfigurace certifikátů autorizovaný partner zadáním názvy předmětu certifikátu nebo kryptografické otisky certifikátů.</span><span class="sxs-lookup"><span data-stu-id="9c44a-106">In order to enable the WS-AT protocol service, you must use the configuration utility to configure the HTTPS port for WS-AT, bind an X.509 certificate to the HTTPS port, and configure authorized partner certificates by specifying certificate subject names or thumbprints.</span></span> <span data-ttu-id="9c44a-107">Nástroj pro konfiguraci můžete také vybrat režimu trasování a odchozí výchozí sadu a maximální časový limit příchozí transakce.</span><span class="sxs-lookup"><span data-stu-id="9c44a-107">The configuration utility also allows you to select the tracing mode and set default outgoing and maximum incoming transaction timeouts.</span></span>  
  
 <span data-ttu-id="9c44a-108">Tento nástroj funkce dostanete pomocí modul snap-in konzoly Microsoft Management Console (MMC) vlastnost stránky v konzole pro správu služby komponent nebo z okna příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="9c44a-108">You can access this tool's functionality by using a Microsoft Management Console (MMC) property page snap-in in the Component Services management console, or from a command-line window.</span></span> <span data-ttu-id="9c44a-109">Konfigurace podpory protokolu WS-AT v místním počítači pomocí okna příkazového řádku; Nakonfigurujte nastavení na místních i vzdálených počítačů pomocí modulu snap-in konzoly MMC.</span><span class="sxs-lookup"><span data-stu-id="9c44a-109">Configure WS-AT support on the local machine through the command-line window; configure settings on both local and remote machines by using the MMC snap-in.</span></span>  
  
 <span data-ttu-id="9c44a-110">Okno příkazového řádku jsou přístupné z umístění instalace sady Windows SDK "%WINDIR%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation".</span><span class="sxs-lookup"><span data-stu-id="9c44a-110">The command-line window can be accessed in the Windows SDK installation location "%WINDIR%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation".</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9c44a-111">Nástroj příkazového řádku najdete v části [WS-AtomicTransaction Configuration Utility (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9c44a-111"> the command-line tool, see [WS-AtomicTransaction Configuration Utility (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md).</span></span>  
  
 <span data-ttu-id="9c44a-112">Pokud používáte [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nebo [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], můžete přístup k modulu snap-in konzoly MMC přechodem na **ovládacích panelech nástroje/Component Services**, klikněte pravým tlačítkem na **Můj počítač**, a Výběr **vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="9c44a-112">If you are running [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], you can access the MMC snap-in by navigating to **Control Panel/Administrative Tools/Component Services**, right-clicking **My Computer**, and selecting **Properties**.</span></span> <span data-ttu-id="9c44a-113">Toto je stejné umístění, kde můžete nakonfigurovat Microsoft distribuované transakce koordinátora služba MSDTC ().</span><span class="sxs-lookup"><span data-stu-id="9c44a-113">This is the same location where you can configure the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="9c44a-114">Možnosti, které jsou k dispozici ke konfiguraci jsou seskupené v rámci **WS-AT** kartě. Pokud používáte systém Windows Vista nebo [!INCLUDE[lserver](../../../../includes/lserver-md.md)], modul snap-in konzoly MMC naleznete kliknutím **spustit** tlačítko a zadáním `dcomcnfg.exe` v **vyhledávání** pole.</span><span class="sxs-lookup"><span data-stu-id="9c44a-114">Options available for configuration are grouped under the **WS-AT** tab. If you are running Windows Vista or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], the MMC snap-in can be found by clicking the **Start** button, and entering `dcomcnfg.exe` in the **Search** box.</span></span> <span data-ttu-id="9c44a-115">Po otevření konzoly MMC, přejděte na **Moje Computer\Distributed transakce Coordinator\Local DTC** uzel, klikněte pravým tlačítkem a vyberte **vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="9c44a-115">When the MMC is opened, navigate to the **My Computer\Distributed Transaction Coordinator\Local DTC** node, right click and select **Properties**.</span></span> <span data-ttu-id="9c44a-116">Možnosti, které jsou k dispozici ke konfiguraci jsou seskupené v rámci **WS-AT** kartě.</span><span class="sxs-lookup"><span data-stu-id="9c44a-116">Options available for configuration are grouped under the **WS-AT** tab.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9c44a-117">modul snap-in najdete [modul Snap-in konzoly MMC WS-AtomicTransaction Configuration](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="9c44a-117"> the snap-in, see the [WS-AtomicTransaction Configuration MMC Snap-in](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md).</span></span>  
  
 <span data-ttu-id="9c44a-118">Pokud chcete povolit uživatelské rozhraní nástroje, nejprve je nutné zaregistrovat soubor WsatUI.dll, který je umístěný v následující cestě</span><span class="sxs-lookup"><span data-stu-id="9c44a-118">To enable the tool's user interface, you must first register the WsatUI.dll file, located at the following path</span></span>  
  
 <span data-ttu-id="9c44a-119">%ProgramFiles%\Microsoft SDKs\Windows\v6.0\Bin</span><span class="sxs-lookup"><span data-stu-id="9c44a-119">%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin</span></span>  
  
 <span data-ttu-id="9c44a-120">K registraci, spusťte následující příkaz z okna příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="9c44a-120">To register the product, execute the following command from a Command Prompt window:</span></span>  
  
 `regasm.exe /codebase WsatUI.dll`  
  
## <a name="enabling-ws-at"></a><span data-ttu-id="9c44a-121">Povolení služby WS-AT</span><span class="sxs-lookup"><span data-stu-id="9c44a-121">Enabling WS-AT</span></span>  
 <span data-ttu-id="9c44a-122">Chcete-li povolit služby protokolu WS-AT uvnitř služby MSDTC pomocí portu 443 a certifikátu X.509. certifikát s privátním klíčem, která byla nainstalována v úložišti místního počítače, použijte nástroj wsatConfig.exe pomocí následujícího příkazu.</span><span class="sxs-lookup"><span data-stu-id="9c44a-122">To enable the WS-AT protocol service inside MSDTC using port 443 and an X.509 certificate with a private key that has been installed in the local machine store, use the wsatConfig.exe tool with the following command.</span></span>  
  
 `WsatConfig.exe –network:enable –port:8443 –endpointCert:<machine|"Issuer\SubjectName"> -accountsCerts:<thumbprint|"Issuer\SubjectName"> -restart`  
  
 <span data-ttu-id="9c44a-123">Nahraďte příslušnými parametry s hodnotami, které jsou relevantní pro vaše prostředí.</span><span class="sxs-lookup"><span data-stu-id="9c44a-123">Substitute the respective parameters with values relevant to your environment.</span></span>  
  
 <span data-ttu-id="9c44a-124">Chcete-li zakázat službu protokolu WS-AT uvnitř služby MSDTC, použijte nástroj wsatConfig.exe pomocí následujícího příkazu.</span><span class="sxs-lookup"><span data-stu-id="9c44a-124">To disable the WS-AT protocol service inside MSDTC, use the wsatConfig.exe tool with the following command.</span></span>  
  
 `WsatConfig.exe –network:disable -restart`  
  
## <a name="configuring-trust-between-two-machines"></a><span data-ttu-id="9c44a-125">Konfigurace vztahu důvěryhodnosti mezi dva počítače</span><span class="sxs-lookup"><span data-stu-id="9c44a-125">Configuring Trust Between Two Machines</span></span>  
 <span data-ttu-id="9c44a-126">Služba protokolu WS-AT vyžaduje správce explicitně autorizovat jednotlivých účtů k účastnit v distribuovaných transakcích.</span><span class="sxs-lookup"><span data-stu-id="9c44a-126">The WS-AT protocol service requires the administrator to explicitly authorize individual accounts to participate in distributed transactions.</span></span> <span data-ttu-id="9c44a-127">Pokud jste správce pro dva počítače, můžete nakonfigurovat oba počítače k navázání vztahu důvěryhodnosti vzájemné výměna správnou sadu certifikátů mezi počítači, nainstalujete je do úložiště příslušné certifikátů a pomocí Nástroj wsatConfig.exe přidání certifikátu pro každý počítač do jiného seznam autorizovaných účastnické certifikátů.</span><span class="sxs-lookup"><span data-stu-id="9c44a-127">If you are an administrator for two machines, you can configure both machines to establish a mutual trust relationship by exchanging the right set of certificates between the machines, installing them into the appropriate certificate stores, and using the wsatConfig.exe tool to add each machine's certificate to the other's list of authorized participant certificates.</span></span> <span data-ttu-id="9c44a-128">Tento krok je nutný k provedení distribuované transakce mezi dvěma počítači pomocí protokolu WS-AT.</span><span class="sxs-lookup"><span data-stu-id="9c44a-128">This step is necessary to perform distributed transactions between two machines using WS-AT.</span></span>  
  
 <span data-ttu-id="9c44a-129">Následující příklad popisuje kroky k vybudování důvěry mezi dva počítače, A a B.</span><span class="sxs-lookup"><span data-stu-id="9c44a-129">In the following example outlines the steps to establish trust between two machines, A and B.</span></span>  
  
### <a name="creating-and-exporting-certificates"></a><span data-ttu-id="9c44a-130">Vytváření a exportování certifikátů</span><span class="sxs-lookup"><span data-stu-id="9c44a-130">Creating and Exporting Certificates</span></span>  
 <span data-ttu-id="9c44a-131">Tento postup vyžaduje modulu snap-in Certifikáty konzoly MMC.</span><span class="sxs-lookup"><span data-stu-id="9c44a-131">This procedure requires the MMC Certificates snap-in.</span></span> <span data-ttu-id="9c44a-132">Modul snap-in přístupná otevření nabídky Start nebo spustit, zadejte text "konzoly mmc" do vstupního pole a kliknutím na tlačítko OK.</span><span class="sxs-lookup"><span data-stu-id="9c44a-132">The snap-in can be accessed by opening the Start/Run menu, typing "mmc" in the input box and pressing OK.</span></span> <span data-ttu-id="9c44a-133">Potom v **Konzola1** okno, přejděte na **soubor nebo přidat nebo odebrat** modul Snap-in klikněte na tlačítko Přidat a vyberte **certifikáty** z **k dispozici samostatná Moduly snap-in** seznamu.</span><span class="sxs-lookup"><span data-stu-id="9c44a-133">Then, in the **Console1** window, navigate to **the File/Add-Remove** Snap-in, click Add, and choose **Certificates** from the **Available Standalone Snapins** list.</span></span> <span data-ttu-id="9c44a-134">Nakonec vyberte **účet počítače** Správa a klikněte na tlačítko **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c44a-134">Finally, select **Computer Account** to manage and click **OK**.</span></span> <span data-ttu-id="9c44a-135">**Certifikáty** uzel se objeví v modulu snap-in konzoly.</span><span class="sxs-lookup"><span data-stu-id="9c44a-135">The **Certificates** node appears in the snap-in console.</span></span>  
  
 <span data-ttu-id="9c44a-136">Musíte již mít požadované certifikáty k navázání vztahu důvěryhodnosti.</span><span class="sxs-lookup"><span data-stu-id="9c44a-136">You must already possess the required certificates to establish trust.</span></span> <span data-ttu-id="9c44a-137">Informace o vytvoření a nové certifikáty před následující kroky instalace najdete v tématu [postupy: vytvoření a nainstalovat dočasné klientské certifikáty ve WCF během vývoj](http://go.microsoft.com/fwlink/?LinkId=158925).</span><span class="sxs-lookup"><span data-stu-id="9c44a-137">To learn how to create and install new certificates prior to the following steps, see [How to: Create and Install Temporary Client Certificates in WCF During Development](http://go.microsoft.com/fwlink/?LinkId=158925).</span></span>  
  
1.  <span data-ttu-id="9c44a-138">Na počítač A pomocí importu modulu snap-in Certifikáty konzoly MMC existující certifikát (certA) do LocalMachine\MY (osobní uzel) a úložiště LocalMachine\ROOT (důvěryhodné kořenové certifikační autority uzel).</span><span class="sxs-lookup"><span data-stu-id="9c44a-138">On machine A, using the MMC Certificates snap-in, import the existing certificate (certA) into the LocalMachine\MY (Personal Node) and LocalMachine\ROOT store (trusted root certification authority node).</span></span> <span data-ttu-id="9c44a-139">Chcete-li importovat certifikát na konkrétním uzlu, klikněte pravým tlačítkem na uzel a zvolte **všechny úlohy nebo importovat**.</span><span class="sxs-lookup"><span data-stu-id="9c44a-139">To import a certificate to a specific node, right-click the node and choose **All Tasks/Import**.</span></span>  
  
2.  <span data-ttu-id="9c44a-140">Na počítači B, pomocí modulu snap-in Certifikáty konzoly MMC vytvořit nebo získat certB certifikátu s privátním klíčem a importujte ho do LocalMachine\MY (osobní uzel) a úložiště LocalMachine\ROOT (důvěryhodné kořenové certifikační autority uzel).</span><span class="sxs-lookup"><span data-stu-id="9c44a-140">On machine B, using the MMC Certificates snap-in, create or obtain a certificate certB with a private key and import it into the LocalMachine\MY (Personal Node) and LocalMachine\ROOT store (trusted root certification authority node).</span></span>  
  
3.  <span data-ttu-id="9c44a-141">Pokud to dosud neučinili, exportujte do souboru na certA veřejný klíč.</span><span class="sxs-lookup"><span data-stu-id="9c44a-141">Export certA's public key to a file if this has not been done already.</span></span>  
  
4.  <span data-ttu-id="9c44a-142">Pokud to dosud neučinili, exportujte do souboru na certB veřejný klíč.</span><span class="sxs-lookup"><span data-stu-id="9c44a-142">Export certB's public key to a file if this has not been done already.</span></span>  
  
### <a name="establishing-mutual-trust-between-machines"></a><span data-ttu-id="9c44a-143">Navázání vzájemného vztahu důvěryhodnosti mezi počítači</span><span class="sxs-lookup"><span data-stu-id="9c44a-143">Establishing Mutual Trust Between Machines</span></span>  
  
1.  <span data-ttu-id="9c44a-144">Na počítači A naimportujte do úložiště LocalMachine\MY a LocalMachine\ROOT reprezentace souboru certB.</span><span class="sxs-lookup"><span data-stu-id="9c44a-144">On machine A, import the file representation of certB into the LocalMachine\MY and LocalMachine\ROOT stores.</span></span> <span data-ttu-id="9c44a-145">To deklaruje, že počítač certB vztahy důvěryhodnosti pro komunikaci s ním.</span><span class="sxs-lookup"><span data-stu-id="9c44a-145">This declares that machine A trusts certB to communicate with it.</span></span>  
  
2.  <span data-ttu-id="9c44a-146">Na počítači B certA na soubor importujte do úložiště LocalMachine\MY a LocalMachine\ROOT.</span><span class="sxs-lookup"><span data-stu-id="9c44a-146">On machine B, import certA’s file into the LocalMachine\MY and LocalMachine\ROOT stores.</span></span> <span data-ttu-id="9c44a-147">To znamená, že počítač B certA vztahy důvěryhodnosti pro komunikaci s ním.</span><span class="sxs-lookup"><span data-stu-id="9c44a-147">This implies that machine B trusts certA to communicate with it.</span></span>  
  
 <span data-ttu-id="9c44a-148">Po dokončení těchto kroků, je navázán vztah důvěryhodnosti mezi dvěma počítači a dá se nakonfigurovat navzájem komunikují pomocí protokolu WS-AT.</span><span class="sxs-lookup"><span data-stu-id="9c44a-148">After completing these steps, trust is established between the two machines, and they can be configured to communicate with each other using WS-AT.</span></span>  
  
### <a name="configuring-msdtc-to-use-certificates"></a><span data-ttu-id="9c44a-149">Konfigurace služby MS DTC používat certifikáty</span><span class="sxs-lookup"><span data-stu-id="9c44a-149">Configuring MSDTC to Use Certificates</span></span>  
 <span data-ttu-id="9c44a-150">Vzhledem k tomu, že služba protokolu WS-AT funguje jako klient a server, musí oba přijímat příchozí připojení a zahájit odchozí připojení.</span><span class="sxs-lookup"><span data-stu-id="9c44a-150">Since the WS-AT protocol service acts as both a client and a server, it must both listen for incoming connections and initiate outgoing connections.</span></span> <span data-ttu-id="9c44a-151">Proto musíte nakonfigurovat služby MSDTC tak, aby věděl, že může který certifikát má použít při komunikaci s externími uživateli a které certifikáty k autorizaci při přijetí příchozí komunikaci.</span><span class="sxs-lookup"><span data-stu-id="9c44a-151">Therefore, you need to configure MSDTC so that it knows which certificate to use when communicating with external parties, and which certificates to authorize when accepting incoming communication.</span></span>  
  
 <span data-ttu-id="9c44a-152">To můžete nakonfigurovat pomocí modulu snap-in konzoly MMC WS-AT.</span><span class="sxs-lookup"><span data-stu-id="9c44a-152">You can configure this by using the MMC WS-AT snap-in.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9c44a-153">Tento nástroj najdete [modul Snap-in konzoly MMC WS-AtomicTransaction Configuration](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="9c44a-153"> this tool, see the [WS-AtomicTransaction Configuration MMC Snap-in](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md) topic.</span></span> <span data-ttu-id="9c44a-154">Následující kroky popisují, jak k navázání vztahu důvěryhodnosti mezi dvěma počítači spuštěna služba MSDTC.</span><span class="sxs-lookup"><span data-stu-id="9c44a-154">The following steps describe how to establish trust between two computers running MSDTC.</span></span>  
  
1.  <span data-ttu-id="9c44a-155">Nakonfigurujte nastavení počítače na.</span><span class="sxs-lookup"><span data-stu-id="9c44a-155">Configure machine A's settings.</span></span> <span data-ttu-id="9c44a-156">"Certifikát koncového bodu" Vyberte certA.</span><span class="sxs-lookup"><span data-stu-id="9c44a-156">For "Endpoint Certificate", select certA.</span></span> <span data-ttu-id="9c44a-157">Pro "Oprávnění certifikáty" Vyberte certB.</span><span class="sxs-lookup"><span data-stu-id="9c44a-157">For "Authorized Certificates", select the certB.</span></span>  
  
2.  <span data-ttu-id="9c44a-158">Nakonfigurujte počítač B.</span><span class="sxs-lookup"><span data-stu-id="9c44a-158">Configure machine B's settings.</span></span> <span data-ttu-id="9c44a-159">"Certifikát koncového bodu" Vyberte certB.</span><span class="sxs-lookup"><span data-stu-id="9c44a-159">For "Endpoint Certificate", select certB.</span></span> <span data-ttu-id="9c44a-160">Pro "Oprávnění certifikáty" Vyberte certA.</span><span class="sxs-lookup"><span data-stu-id="9c44a-160">For "Authorized Certificates", select the certA.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c44a-161">Když jeden počítač odešle zprávu do jiných počítačů, pokusí se odesílatel ověřte, jestli název předmětu certifikátu příjemce a název počítače příjemce odpovídají.</span><span class="sxs-lookup"><span data-stu-id="9c44a-161">When one machine sends a message to the other machine, the sender attempts to verify that the subject name of the recipient’s certificate and the name of the recipient’s machine match.</span></span> <span data-ttu-id="9c44a-162">Pokud se neshodují, certifikát ověření selže a dva počítače nemohou komunikovat.</span><span class="sxs-lookup"><span data-stu-id="9c44a-162">If they do not match, certificate verification fails and the two machines cannot communicate.</span></span>  
>   
>  <span data-ttu-id="9c44a-163">Pro počítač připojený k doméně je název s plně kvalifikovaným názvem domény.</span><span class="sxs-lookup"><span data-stu-id="9c44a-163">For a machine joined to a domain, the name is the fully qualified domain name.</span></span> <span data-ttu-id="9c44a-164">Ve výchozím nastavení je název počítače v pracovní skupině název pro rozhraní NetBIOS počítače.</span><span class="sxs-lookup"><span data-stu-id="9c44a-164">By default, the name of a machine on a workgroup is the machine’s NetBIOS name.</span></span> <span data-ttu-id="9c44a-165">Název může také mohou obsahovat příponu systému DNS (Domain Name)-Pokud je k dispozici pro připojení používá mezi dvěma počítači.</span><span class="sxs-lookup"><span data-stu-id="9c44a-165">However, the name can also include a Domain Name System (DNS) suffix if one is present for the connection being used between the two machines.</span></span>  
>   
>  <span data-ttu-id="9c44a-166">Pokud se změní název počítače, například při připojení k doméně, počítač pracovní skupiny musí obnášet opětovné vystavení certifikátů nebo ručně nakonfigurovat přípony DNS.</span><span class="sxs-lookup"><span data-stu-id="9c44a-166">If the name of the machine changes, for example, when a workgroup machine joins a domain, you must reissue certificates or manually configure DNS suffixes.</span></span>  
  
## <a name="security"></a><span data-ttu-id="9c44a-167">Zabezpečení</span><span class="sxs-lookup"><span data-stu-id="9c44a-167">Security</span></span>  
 <span data-ttu-id="9c44a-168">Vzhledem k tomu, že některá nastavení týkající se služby MS DTC a WS-AT jsou uložené v registru v HKLM\Software\Microsoft\MSDTC a HKLM\Software\Microsoft\WSAT, v uvedeném pořadí, ujistěte se, že jsou tyto klíče registru zabezpečené tak, aby k nim lze zapisovat pouze správci.</span><span class="sxs-lookup"><span data-stu-id="9c44a-168">Since some of the settings related to MSDTC and WS-AT are stored in the registry at HKLM\Software\Microsoft\MSDTC and at HKLM\Software\Microsoft\WSAT, respectively, ensure that these registry keys are secured so that only administrators can write to them.</span></span> <span data-ttu-id="9c44a-169">V nástroji Editor registru, klikněte pravým tlačítkem na klíč, který chcete zabezpečit a vyberte **oprávnění** o nastavení ovládacího prvku odpovídající přístup.</span><span class="sxs-lookup"><span data-stu-id="9c44a-169">In the Registry Editor tool, right-click the key you want to secure and select **Permission** to set the appropriate access control.</span></span> <span data-ttu-id="9c44a-170">Je velmi důležité pro zabezpečení a integrity systému, který důležité klíče jsou jen pro čtení pro uživatele s nízkými oprávněními.</span><span class="sxs-lookup"><span data-stu-id="9c44a-170">It is crucial to the security and integrity of the system that important keys are read-only for low-privileged users.</span></span>  
  
 <span data-ttu-id="9c44a-171">Při nasazování služby MSDTC, Správce musí zajistěte, aby byl žádné výměnu dat služby MSDTC zabezpečené.</span><span class="sxs-lookup"><span data-stu-id="9c44a-171">When deploying MSDTC, the administrator must ensure that any MSDTC data interchange is secure.</span></span> <span data-ttu-id="9c44a-172">V pracovní skupině nasazení izolovat transakční infrastruktury z uživatelé se zlými úmysly; v nasazení clusteru Zabezpečte registru clusteru.</span><span class="sxs-lookup"><span data-stu-id="9c44a-172">In a workgroup deployment, isolate the transactional infrastructure from malicious users; in a cluster deployment, secure the cluster registry.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="9c44a-173">Trasování</span><span class="sxs-lookup"><span data-stu-id="9c44a-173">Tracing</span></span>  
 <span data-ttu-id="9c44a-174">Integrovaná služba podporuje protokol WS-AT, transakce konkrétní trasování, která můžete povolit a spravovat prostřednictvím [modul Snap-in konzoly MMC WS-AtomicTransaction Configuration](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md) nástroj.</span><span class="sxs-lookup"><span data-stu-id="9c44a-174">The WS-AT protocol service supports integrated, transaction specific tracing that can be enabled and managed through the use of the [WS-AtomicTransaction Configuration MMC Snap-in](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md) tool.</span></span>  <span data-ttu-id="9c44a-175">Trasování může obsahovat data oznamující, že byl přijat v době zařazení se provádí pro konkrétní transakci, čas transakce dosáhne stavu terminálu, výsledek každé zařazení transakce.</span><span class="sxs-lookup"><span data-stu-id="9c44a-175">Traces can include data indicating the time an enlistment is made for a specific transaction, the time a transaction reaches its terminal state, the outcome each transaction enlistment has received.</span></span> <span data-ttu-id="9c44a-176">Všechny trasování lze zobrazit pomocí [nástroj Prohlížeč trasování služeb (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) nástroj.</span><span class="sxs-lookup"><span data-stu-id="9c44a-176">All traces can be viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) tool.</span></span>  
  
 <span data-ttu-id="9c44a-177">Služba protokolu WS-AT také podporuje integrované sledování ServiceModel v relaci trasování ETW.</span><span class="sxs-lookup"><span data-stu-id="9c44a-177">The WS-AT protocol service also supports integrated ServiceModel tracing through the ETW trace session.</span></span> <span data-ttu-id="9c44a-178">To poskytuje podrobnější, specifické pro komunikaci trasování kromě existujícím trasování transakce.</span><span class="sxs-lookup"><span data-stu-id="9c44a-178">This provides more detailed, communication-specific traces in addition to the existing transaction traces.</span></span>  <span data-ttu-id="9c44a-179">Pokud chcete povolit tyto další trasování, postupujte podle těchto kroků</span><span class="sxs-lookup"><span data-stu-id="9c44a-179">To enable these additional traces, follow these steps</span></span>  
  
1.  <span data-ttu-id="9c44a-180">Otevřete **spuštění a spuštění** nabídce do vstupního pole zadejte "regedit" a vyberte **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c44a-180">Open the **Start/Run** menu, type "regedit" in the input box and select **OK**.</span></span>  
  
2.  <span data-ttu-id="9c44a-181">V **Editor registru**, přejděte do následující složky, v levém podokně, Hkey_Local_Machine\SOFTWARE\Microsoft\WSAT\3.0\\</span><span class="sxs-lookup"><span data-stu-id="9c44a-181">In the **Registry Editor**, navigate to the following folder on the left pane, Hkey_Local_Machine\SOFTWARE\Microsoft\WSAT\3.0\\</span></span>  
  
3.  <span data-ttu-id="9c44a-182">Klikněte pravým tlačítkem `ServiceModelDiagnosticTracing` hodnotu v pravém podokně a vyberte **upravit**.</span><span class="sxs-lookup"><span data-stu-id="9c44a-182">Right click the `ServiceModelDiagnosticTracing` value in the right pane and select **Modify**.</span></span>  
  
4.  <span data-ttu-id="9c44a-183">V **údaj hodnoty** vstupní pole, zadejte jednu z následujících hodnot platný k určení úrovně trasování, které chcete povolit.</span><span class="sxs-lookup"><span data-stu-id="9c44a-183">In the **Value data** input box, enter one of the following valid values to specify the trace level you want to enable.</span></span>  
  
-   <span data-ttu-id="9c44a-184">0: vypnuto</span><span class="sxs-lookup"><span data-stu-id="9c44a-184">0: off</span></span>  
  
-   <span data-ttu-id="9c44a-185">1: kritické</span><span class="sxs-lookup"><span data-stu-id="9c44a-185">1: critical</span></span>  
  
-   <span data-ttu-id="9c44a-186">3: Chyba.</span><span class="sxs-lookup"><span data-stu-id="9c44a-186">3: error.</span></span> <span data-ttu-id="9c44a-187">Toto je výchozí hodnota</span><span class="sxs-lookup"><span data-stu-id="9c44a-187">This is the default value</span></span>  
  
-   <span data-ttu-id="9c44a-188">7: upozornění</span><span class="sxs-lookup"><span data-stu-id="9c44a-188">7: warning</span></span>  
  
-   <span data-ttu-id="9c44a-189">15: informace</span><span class="sxs-lookup"><span data-stu-id="9c44a-189">15: information</span></span>  
  
-   <span data-ttu-id="9c44a-190">31: verbose</span><span class="sxs-lookup"><span data-stu-id="9c44a-190">31: verbose</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c44a-191">Viz také</span><span class="sxs-lookup"><span data-stu-id="9c44a-191">See Also</span></span>  
 [<span data-ttu-id="9c44a-192">WS-AtomicTransaction Configuration Utility (wsatConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="9c44a-192">WS-AtomicTransaction Configuration Utility (wsatConfig.exe)</span></span>](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)  
 [<span data-ttu-id="9c44a-193">Modul Snap-in konzoly MMC WS-AtomicTransaction Configuration</span><span class="sxs-lookup"><span data-stu-id="9c44a-193">WS-AtomicTransaction Configuration MMC Snap-in</span></span>](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)