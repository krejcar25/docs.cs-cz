---
title: "Rozšířený výběr formátu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e02d9082-4d55-41d8-9329-98f6d1c77f06
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5b3c1bd6c63188b9b812248b8d815237832a4aad
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="advanced-format-selection"></a><span data-ttu-id="471ca-102">Rozšířený výběr formátu</span><span class="sxs-lookup"><span data-stu-id="471ca-102">Advanced Format Selection</span></span>
<span data-ttu-id="471ca-103">Tento příklad ukazuje, jak rozšířit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] programovací model REST pro podporu nových odchozí odpovědi formátů.</span><span class="sxs-lookup"><span data-stu-id="471ca-103">This sample demonstrates how to extend the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST programming model to support new outgoing response formats.</span></span> <span data-ttu-id="471ca-104">Kromě toho Ukázka používá šablony T4 k vrácení odpovědi jako stránku XHTML ukázka, jak se dají implementovat programovací model styl zobrazení.</span><span class="sxs-lookup"><span data-stu-id="471ca-104">In addition, the sample uses a T4 Template to return the response as an XHTML page, demonstrating how a view-style programming model can be implemented.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="471ca-105">Ukázka podrobnosti</span><span class="sxs-lookup"><span data-stu-id="471ca-105">Sample Details</span></span>  
 <span data-ttu-id="471ca-106">Ukázkový soubor obsahuje jednoduché služby společně s kód klienta, který slouží k žádosti o službu.</span><span class="sxs-lookup"><span data-stu-id="471ca-106">The sample consists of a simple service along with client code that makes requests to the service.</span></span>  <span data-ttu-id="471ca-107">Služba podporuje jedné operace [WebGet], který má označení následující metody:`Message EchoListWithGet(string list);`</span><span class="sxs-lookup"><span data-stu-id="471ca-107">The service supports a single [WebGet] operation, which has the following method signature: `Message EchoListWithGet(string list);`</span></span>  
  
 <span data-ttu-id="471ca-108">Když klient odešle požadavek na službu, poskytuje seznam položek z textový soubor s oddělovači `list` parametr s řetězcem dotazu a službu vrátí tento stejný seznam v jednom z následujících formátů: XML, JSON, Atom, XHTML nebo jpeg.</span><span class="sxs-lookup"><span data-stu-id="471ca-108">When the client makes a request to the service, it provides a comma-separated list of items from the `list` query-string parameter and the service returns that same list in one of the following formats: XML, JSON, Atom, XHTML, or jpeg.</span></span>  
  
 <span data-ttu-id="471ca-109">Služba vrátila formát odpovědi je nejdřív dáno `format` parametr s řetězcem dotazu a sekundu, které hlavičku HTTP přijmout zadaný v požadavku.</span><span class="sxs-lookup"><span data-stu-id="471ca-109">The response format returned by the service is determined first by a `format` query-string parameter and second by an HTTP Accept header supplied with the request.</span></span> <span data-ttu-id="471ca-110">Pokud hodnota `format` parametr s řetězcem dotazu je jedním z předchozí formátů a pak odpověď se vrátí v tomto formátu.</span><span class="sxs-lookup"><span data-stu-id="471ca-110">If the value of `format` query-string parameter is one of the preceding formats, then the response is returned in that format.</span></span> <span data-ttu-id="471ca-111">Pokud `format` řetězec dotazu není k dispozici, pak službu iteruje prvky hlavičky Accept z požadavku a vrátí formát první obsahu – typ, který podporuje službu.</span><span class="sxs-lookup"><span data-stu-id="471ca-111">If the `format` query-string is not present, then the service iterates through the Accept header elements from the request and returns the format of the first content-type that the service supports.</span></span>  
  
 <span data-ttu-id="471ca-112">Návratový typ operace je vhodné poznamenat.</span><span class="sxs-lookup"><span data-stu-id="471ca-112">The return type of the operation is worth noting.</span></span> <span data-ttu-id="471ca-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Jenom nativně programovací model REST podporuje formáty XML a JSON odpovědi při operace vrátí typ, jiné než <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="471ca-113">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST programming model only natively supports XML and JSON response formats when an operation returns a type other than <xref:System.ServiceModel.Channels.Message>.</span></span> <span data-ttu-id="471ca-114">Ale při použití <xref:System.ServiceModel.Channels.Message> jako návratový typ vývojář má plnou kontrolu nad formátování obsah zprávy.</span><span class="sxs-lookup"><span data-stu-id="471ca-114">However, when using <xref:System.ServiceModel.Channels.Message> as the return type, the developer has complete control over how the content of the message should be formatted.</span></span>  
  
 <span data-ttu-id="471ca-115">Ukázce se používá <xref:System.ServiceModel.Web.WebOperationContext.CreateXmlResponse%2A>, <xref:System.ServiceModel.Web.WebOperationContext.CreateJsonResponse%2A> a <xref:System.ServiceModel.Web.WebOperationContext.CreateAtom10Response%2A> metody k serializaci seznam řetězců do XML, JSON a ATOM zpráv v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="471ca-115">The sample uses the <xref:System.ServiceModel.Web.WebOperationContext.CreateXmlResponse%2A>, <xref:System.ServiceModel.Web.WebOperationContext.CreateJsonResponse%2A> and <xref:System.ServiceModel.Web.WebOperationContext.CreateAtom10Response%2A> methods to serialize the list of strings into XML, JSON, and ATOM messages respectively.</span></span> <span data-ttu-id="471ca-116">Pro formát odpovědi jpeg <xref:System.ServiceModel.Web.WebOperationContext.CreateStreamResponse%2A> metoda se používá a je obrázek uložen do datového proudu.</span><span class="sxs-lookup"><span data-stu-id="471ca-116">For the jpeg response format, the <xref:System.ServiceModel.Web.WebOperationContext.CreateStreamResponse%2A> method is used and the image is saved to the stream.</span></span> <span data-ttu-id="471ca-117">Pro odpověď v kódu XHTML <xref:System.ServiceModel.Web.WebOperationContext.CreateTextResponse%2A> se používá spolu s předběžně zpracované T4 šablonu, která se skládá z soubor .tt a .cs automaticky generovaný soubor.</span><span class="sxs-lookup"><span data-stu-id="471ca-117">For the XHTML response, the <xref:System.ServiceModel.Web.WebOperationContext.CreateTextResponse%2A> is used along with a preprocessed T4 template, which consists of a .tt file and an auto-generated .cs file.</span></span> <span data-ttu-id="471ca-118">Soubor .tt umožňuje vývojáři k zápisu odpovědi v podobě šablony, který obsahuje proměnné a řízení struktury.</span><span class="sxs-lookup"><span data-stu-id="471ca-118">The .tt file allows a developer to write a response in a template form that contains variables and control structures.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="471ca-119">T4, najdete v části [generování artefaktů podle pomocí textových šablon](http://go.microsoft.com/fwlink/?LinkId=166023).</span><span class="sxs-lookup"><span data-stu-id="471ca-119"> T4, see [Generating Artifacts By Using Text Templates](http://go.microsoft.com/fwlink/?LinkId=166023).</span></span>  
  
 <span data-ttu-id="471ca-120">Ukázkový soubor obsahuje služba s vlastním hostováním a klienta, který běží v konzolové aplikaci.</span><span class="sxs-lookup"><span data-stu-id="471ca-120">The sample consists of a self-hosted service and a client that runs within a console application.</span></span> <span data-ttu-id="471ca-121">Konzolové aplikace běží, klient odešle žádosti o službu a zapisuje příslušné informace z odpovědi do okna konzoly.</span><span class="sxs-lookup"><span data-stu-id="471ca-121">As the console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="471ca-122">Chcete tuto ukázku spustit</span><span class="sxs-lookup"><span data-stu-id="471ca-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="471ca-123">Otevřete řešení pro ukázku rozšířené výběr formátu.</span><span class="sxs-lookup"><span data-stu-id="471ca-123">Open the solution for the Advanced Format Selection Sample.</span></span> <span data-ttu-id="471ca-124">Při spouštění [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], byste měli spustit jako správce pro vzorovou proběhl úspěšně.</span><span class="sxs-lookup"><span data-stu-id="471ca-124">When launching [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], you should run as an administrator for the sample to execute successfully.</span></span> <span data-ttu-id="471ca-125">To můžete provést kliknutím pravým tlačítkem myši [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] ikonu a výběr **spustit jako správce** v místní nabídce.</span><span class="sxs-lookup"><span data-stu-id="471ca-125">Do this by right-clicking the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icon and choosing **Run as Administrator** from the context menu.</span></span>  
  
2.  <span data-ttu-id="471ca-126">Stisknutím kombinace kláves CTRL + SHIFT + B sestavte řešení a potom stiskněte klávesu Ctrl + F5 spusťte projekt konzolové aplikace AdvancedFormatSelection bez ladění.</span><span class="sxs-lookup"><span data-stu-id="471ca-126">Press CTRL+SHIFT+B to build the solution and then press Ctrl-F5 to run the console application AdvancedFormatSelection project without debugging.</span></span> <span data-ttu-id="471ca-127">V okně konzoly se zobrazí a poskytuje identifikátor URI spuštěné služby a identifikátor URI HTML stránka pro spuštěnou službu nápovědy.</span><span class="sxs-lookup"><span data-stu-id="471ca-127">The console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span>  
  
3.  <span data-ttu-id="471ca-128">Ukázka běží, klient odešle požadavky do služby a zapíše odpovědi do okna konzoly.</span><span class="sxs-lookup"><span data-stu-id="471ca-128">As the sample runs, the client sends requests to the service and writes the responses to the console window.</span></span> <span data-ttu-id="471ca-129">Všimněte si různých formátech odpovědí: XML, JSON, Atom a XHTML.</span><span class="sxs-lookup"><span data-stu-id="471ca-129">Notice the different formats of the responses: XML, JSON, Atom, and XHTML.</span></span>  
  
4.  <span data-ttu-id="471ca-130">Zobrazí se výzva k procházení k identifikátoru URI, ve kterém můžete požádat o odpovědi ve formátu .jpeg.</span><span class="sxs-lookup"><span data-stu-id="471ca-130">You are then prompted to browse to a URI in which you can request the response in a .jpeg format.</span></span> <span data-ttu-id="471ca-131">Otevřete prohlížeč a přejděte na daný identifikátor URI.</span><span class="sxs-lookup"><span data-stu-id="471ca-131">Open a browser and browse to the given URI.</span></span>  
  
5.  <span data-ttu-id="471ca-132">Stisknutím libovolné klávesy ukončit vzorku.</span><span class="sxs-lookup"><span data-stu-id="471ca-132">Press any key to terminate the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="471ca-133">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="471ca-133">The samples may already be installed on your machine.</span></span> <span data-ttu-id="471ca-134">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="471ca-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="471ca-135">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="471ca-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="471ca-136">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="471ca-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AdvancedFormatSelection`  
  
## <a name="see-also"></a><span data-ttu-id="471ca-137">Viz také</span><span class="sxs-lookup"><span data-stu-id="471ca-137">See Also</span></span>