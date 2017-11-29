---
title: "Pomocí F # na Azure"
description: "Průvodce pomocí služeb Azure s F #"
keywords: "Azure cloud, visual f #, f # funkční programování, .NET, .NET Core"
author: sylvanc
ms.author: phcart
ms.date: 09/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: FAD4D11E-703A-42D4-9F72-893D9E0F569B
ms.openlocfilehash: 636604b1a0b645f13ac20d7ed85bde9abae3f9f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="using-f-on-azure"></a><span data-ttu-id="c9a3f-104">Pomocí F # na Azure</span><span class="sxs-lookup"><span data-stu-id="c9a3f-104">Using F# on Azure</span></span>

<span data-ttu-id="c9a3f-105">F # je vynikající jazyk pro programování cloudu a se často používá k zápisu webových aplikací, cloudové služby, mikroslužeb hostovaných v cloudu a pro škálovatelnou zpracování dat.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-105">F# is a superb language for cloud programming and is frequently used to write web applications, cloud services, cloud-hosted microservices, and for scalable data processing.</span></span>

<span data-ttu-id="c9a3f-106">V následujících částech najdete prostředky na použití služby oblast Azure s F #.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-106">In the following sections, you will find resources on how to use a range of Azure services with F#.</span></span>

> [!NOTE]
> <span data-ttu-id="c9a3f-107">Pokud konkrétní službu Azure není v této dokumentaci, přečtěte si dokumentaci Azure Functions nebo rozhraní .NET pro tuto službu.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-107">If a particular Azure service isn't in this documentation set, please consult either the Azure Functions or .NET documentation for that service.</span></span> <span data-ttu-id="c9a3f-108">Některé služby Azure jsou nezávislé na jazyku a vyžadují žádná konkrétní jazyk dokumentace a zde nejsou uvedeny.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-108">Some Azure services are language-independent and require no language-specific documentation and are not listed here.</span></span>

## <a name="using-azure-virtual-machines-with-f"></a><span data-ttu-id="c9a3f-109">Pomocí virtuální počítače Azure F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-109">Using Azure Virtual Machines with F#</span></span> #

<span data-ttu-id="c9a3f-110">Azure podporuje širokou škálu konfigurace virtuálních počítačů (VM), najdete v části [Linux a virtuální počítače Azure](https://azure.microsoft.com/services/virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="c9a3f-110">Azure supports a wide range of virtual machine (VM) configurations, see [Linux and Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/).</span></span>

<span data-ttu-id="c9a3f-111">Chcete-li nainstalovat F # na virtuálním počítači pro spuštění, kompilace a skriptování najdete v tématu [pomocí F # v systému Linux](http://fsharp.org/use/linux) a [pomocí F # v systému Windows](http://fsharp.org/use/windows).</span><span class="sxs-lookup"><span data-stu-id="c9a3f-111">To install F# on a virtual machine for execution, compilation and/or scripting see [Using F# on Linux](http://fsharp.org/use/linux) and [Using F# on Windows](http://fsharp.org/use/windows).</span></span>


## <a name="using-azure-functions-with-f"></a><span data-ttu-id="c9a3f-112">Pomocí Azure Functions F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-112">Using Azure Functions with F#</span></span> #

<span data-ttu-id="c9a3f-113">[Azure Functions](https://azure.microsoft.com/services/functions/) je řešení umožňující snadno spouštět malé části kódu, nebo "funkce" v cloudu.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-113">[Azure Functions](https://azure.microsoft.com/services/functions/) is a solution for easily running small pieces of code, or "functions," in the cloud.</span></span> <span data-ttu-id="c9a3f-114">Můžete napsat přesně takový kód, potřebujete pro aktuální problém, bez starostí o infrastrukturu nebo aplikaci jako celek ji spustit.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-114">You can write just the code you need for the problem at hand, without worrying about a whole application or the infrastructure to run it.</span></span> <span data-ttu-id="c9a3f-115">Funkce jsou připojené k události v úložišti Azure a dalším prostředkům hostovaných v cloudu.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-115">Your functions are connected to events in Azure storage and other cloud-hosted resources.</span></span> <span data-ttu-id="c9a3f-116">Toky dat do funkce F # prostřednictvím argumenty funkce.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-116">Data flows into your F# functions via function arguments.</span></span> <span data-ttu-id="c9a3f-117">Můžete použít svůj vývoj jazyk podle vlastní volby, důvěřující Azure škálovat podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-117">You can use your development language of choice, trusting Azure to scale as needed.</span></span>

<span data-ttu-id="c9a3f-118">Azure Functions podporovat F # jako první třídy jazyk s efektivní, reaktivní, škálovatelné spuštění kódu F #.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-118">Azure Functions support F# as a first-class language with efficient, reactive, scalable execution of F# code.</span></span> <span data-ttu-id="c9a3f-119">Najdete v článku [Azure funkce F # referenční informace pro vývojáře](/azure/azure-functions/functions-reference-fsharp) pro referenční dokumentaci o tom, jak používat F # s Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-119">See the [Azure Functions F# Developer Reference](/azure/azure-functions/functions-reference-fsharp) for reference documentation on how to use F# with Azure Functions.</span></span>

<span data-ttu-id="c9a3f-120">Další zdroje informací pro používání Azure Functions a F #:</span><span class="sxs-lookup"><span data-stu-id="c9a3f-120">Other resources for using Azure Functions and F#:</span></span>

* [<span data-ttu-id="c9a3f-121">Škálování Azure Functions v F # s použitím Suave</span><span class="sxs-lookup"><span data-stu-id="c9a3f-121">Scale Up Azure Functions in F# Using Suave</span></span>](http://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/)
* [<span data-ttu-id="c9a3f-122">Postup vytvoření funkce Azure v jazyce F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-122">How to create Azure function in F#</span></span>](https://mnie.github.io/2016-09-08-AzureFunctions/)
* [<span data-ttu-id="c9a3f-123">Zprostředkovatel Azure typu pomocí Azure Functions</span><span class="sxs-lookup"><span data-stu-id="c9a3f-123">Using the Azure Type Provider with Azure Functions</span></span>](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)

## <a name="using-azure-storage-with-f"></a><span data-ttu-id="c9a3f-124">Používání Azure Storage s F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-124">Using Azure Storage with F#</span></span> #

<span data-ttu-id="c9a3f-125">Azure Storage je základní vrstvu služby úložiště pro moderní aplikace, které jsou závislé na odolnost, dostupnost a škálovatelnost, abyste splnili požadavky zákazníků.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-125">Azure Storage is a base layer of storage services for modern applications that rely on durability, availability, and scalability to meet the needs of customers.</span></span> <span data-ttu-id="c9a3f-126">F # programy mohou komunikovat přímo s služby Azure storage, pomocí techinques popsané v následujících článcích.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-126">F# programs can interact directly with Azure storage services, using the techinques described in the following articles.</span></span>

* [<span data-ttu-id="c9a3f-127">Začínáme s Azure Blob storage pomocí F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-127">Get started with Azure Blob storage using F#</span></span>](blob-storage.md)
* [<span data-ttu-id="c9a3f-128">Začínáme s Azure File storage pomocí F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-128">Get started with Azure File storage using F#</span></span>](file-storage.md)
* [<span data-ttu-id="c9a3f-129">Začínáme s Azure Queue storage pomocí F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-129">Get started with Azure Queue storage using F#</span></span>](queue-storage.md)
* [<span data-ttu-id="c9a3f-130">Začínáme s Azure Table storage pomocí F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-130">Get started with Azure Table storage using F#</span></span>](table-storage.md)

<span data-ttu-id="c9a3f-131">Úložiště Azure můžete také použít ve spojení s Azure Functions prostřednictvím deklarativní konfigurace spíše než explicitní volání rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-131">Azure Storage can also be used in conjunction with Azure Functions through declarative configuration rather than explicit API calls.</span></span> <span data-ttu-id="c9a3f-132">V tématu [Azure Functions triggerů a vazeb pro Azure Storage](/azure/azure-functions/functions-bindings-storage) což zahrnuje příklady F #.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-132">See [Azure Functions triggers and bindings for Azure Storage](/azure/azure-functions/functions-bindings-storage) which includes F# examples.</span></span>

## <a name="using-azure-app-service-with-f"></a><span data-ttu-id="c9a3f-133">Pomocí služby Azure App Service F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-133">Using Azure App Service with F#</span></span> #

<span data-ttu-id="c9a3f-134">[Aplikační služba Azure](https://azure.microsoft.com/services/app-service/) je Cloudová platforma vytvářet výkonné webové a mobilní aplikace, které se připojují k datům kdekoliv a v cloudu nebo místně.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-134">[Azure App Service](https://azure.microsoft.com/services/app-service/) is a cloud platform to build powerful web and mobile apps that connect to data anywhere, in the cloud or on-premises.</span></span>

* [<span data-ttu-id="c9a3f-135">Příklad F # Azure webového rozhraní API</span><span class="sxs-lookup"><span data-stu-id="c9a3f-135">F# Azure Web API example</span></span>](https://github.com/fsprojects/azure-webapi-example)
* [<span data-ttu-id="c9a3f-136">Hostování F # ve webové aplikaci v Azure</span><span class="sxs-lookup"><span data-stu-id="c9a3f-136">Hosting F# in a web application on Azure</span></span>](https://github.com/isaacabraham/fsharp-demonstrator)

## <a name="using-apache-spark-with-f-with-azure-hdinsight"></a><span data-ttu-id="c9a3f-137">Pomocí Apache Spark F # s Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="c9a3f-137">Using Apache Spark with F# with Azure HDInsight</span></span>

<span data-ttu-id="c9a3f-138">[Apache Spark pro Azure HDInsight](https://azure.microsoft.com/services/hdinsight/apache-spark/) je představuje rozhraní s otevřeným zdrojem zpracování, které běží aplikace, rozsáhlé datové analýzy.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-138">[Apache Spark for Azure HDInsight](https://azure.microsoft.com/services/hdinsight/apache-spark/) is an open source processing framework that runs large-scale data analytics applications.</span></span> <span data-ttu-id="c9a3f-139">Azure umožňuje Apache Spark snadný a nákladově efektivní pro nasazení.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-139">Azure makes Apache Spark easy and cost effective to deploy.</span></span> <span data-ttu-id="c9a3f-140">Vývoj aplikace Spark v F # pomocí [Mobius](https://github.com/Microsoft/Mobius), .NET API pro Spark.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-140">Develop your Spark application in F# using [Mobius](https://github.com/Microsoft/Mobius), a .NET API for Spark.</span></span>

* [<span data-ttu-id="c9a3f-141">Implementace aplikací Spark v F # s použitím Mobius</span><span class="sxs-lookup"><span data-stu-id="c9a3f-141">Implementing Spark Apps in F# using Mobius</span></span>](https://github.com/Microsoft/Mobius/blob/master/notes/spark-fsharp-mobius.md)
* [<span data-ttu-id="c9a3f-142">Příklad F # Spark aplikací pomocí Mobius</span><span class="sxs-lookup"><span data-stu-id="c9a3f-142">Example F# Spark Apps using Mobius</span></span>](https://github.com/Microsoft/Mobius/tree/master/examples/fsharp)

## <a name="using-azure-documentdb-with-f"></a><span data-ttu-id="c9a3f-143">Pomocí Azure DocumentDB F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-143">Using Azure DocumentDB with F#</span></span> #

<span data-ttu-id="c9a3f-144">[Azure DocumentDB](https://azure.microsoft.com/services/documentdb/) je služba NoSQL pro vysokou dostupnost, globálně distribuované aplikace.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-144">[Azure DocumentDB](https://azure.microsoft.com/services/documentdb/) is a NoSQL service for highly available, globally distributed apps.</span></span>

<span data-ttu-id="c9a3f-145">Azure DocumentDB a F # lze použít dvěma způsoby:</span><span class="sxs-lookup"><span data-stu-id="c9a3f-145">Azure DocumentDB can be used with F# in two ways:</span></span>

1. <span data-ttu-id="c9a3f-146">Prostřednictvím vytváření sad Azure Functions F # které reagovat na nebo mění na kolekce DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-146">Through the creation of F# Azure Functions which react to or cause changes to DocumentDB collections.</span></span> <span data-ttu-id="c9a3f-147">V tématu [aktivuje funkce Azure documentdb](/azure/azure-functions/functions-bindings-documentdb), nebo</span><span class="sxs-lookup"><span data-stu-id="c9a3f-147">See [Azure Function triggers for DocumentDB](/azure/azure-functions/functions-bindings-documentdb), or</span></span>
2. <span data-ttu-id="c9a3f-148">Pomocí [.NET SDK pro Azure](/azure/documentdb/documentdb-get-started-quickstart).</span><span class="sxs-lookup"><span data-stu-id="c9a3f-148">By using the [.NET SDK for Azure](/azure/documentdb/documentdb-get-started-quickstart).</span></span> <span data-ttu-id="c9a3f-149">Všimněte si, že tyto příklady jsou v jazyce C#.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-149">Note these examples are in C#.</span></span>

## <a name="using-azure-event-hubs-with-f"></a><span data-ttu-id="c9a3f-150">Pomocí služby Azure Event Hubs F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-150">Using Azure Event Hubs with F#</span></span> #

<span data-ttu-id="c9a3f-151">[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) poskytnout cloudového škálovatelného přijímání telemetrie z webů, aplikací a zařízení.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-151">[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) provide cloud-scale telemetry ingestion from websites, apps, and devices.</span></span>

<span data-ttu-id="c9a3f-152">Azure Event Hubs s F # lze použít dvěma způsoby:</span><span class="sxs-lookup"><span data-stu-id="c9a3f-152">Azure Event Hubs can be used with F# in two ways:</span></span>

1. <span data-ttu-id="c9a3f-153">Prostřednictvím vytváření F # Azure funkcí, které jsou aktivovány události.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-153">Through the creation of F# Azure Functions which are triggered by events.</span></span> <span data-ttu-id="c9a3f-154">V tématu [aktivuje funkce Azure pro službu Event Hubs](/azure/azure-functions/functions-bindings-event-hubs), nebo</span><span class="sxs-lookup"><span data-stu-id="c9a3f-154">See [Azure Function triggers for Event Hubs](/azure/azure-functions/functions-bindings-event-hubs), or</span></span>
2. <span data-ttu-id="c9a3f-155">Pomocí [.NET SDK pro Azure](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted).</span><span class="sxs-lookup"><span data-stu-id="c9a3f-155">By using the [.NET SDK for Azure](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted).</span></span> <span data-ttu-id="c9a3f-156">Všimněte si, že tyto příklady jsou v jazyce C#.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-156">Note these examples are in C#.</span></span>

## <a name="using-azure-notification-hubs-with-f"></a><span data-ttu-id="c9a3f-157">Pomocí Azure Notification Hubs F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-157">Using Azure Notification Hubs with F#</span></span> #

<span data-ttu-id="c9a3f-158">[Služba Azure Notification Hubs](/azure/notification-hubs/) jsou s více platformami a horizontálně škálovanou infrastrukturu, která vám umožní odesílat mobilní nabízená oznámení z jakékoli back-end (v cloudu nebo místní) na libovolnou mobilní platformu.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-158">[Azure Notification Hubs](/azure/notification-hubs/) are multiplatform, scaled-out push infrastructure that enable you to send mobile push notifications from any backend (in the cloud or on-premises) to any mobile platform.</span></span>

<span data-ttu-id="c9a3f-159">Služba Azure Notification Hubs s F # lze použít dvěma způsoby:</span><span class="sxs-lookup"><span data-stu-id="c9a3f-159">Azure Notification Hubs can be used with F# in two ways:</span></span>

1. <span data-ttu-id="c9a3f-160">Prostřednictvím vytváření sad Azure Functions F # který odeslat výsledky do centra oznámení.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-160">Through the creation of F# Azure Functions which send results to a notification hub.</span></span> <span data-ttu-id="c9a3f-161">V tématu [funkce Azure výstup aktivační události služby Notification Hubs](/azure/azure-functions/functions-bindings-notification-hubs), nebo</span><span class="sxs-lookup"><span data-stu-id="c9a3f-161">See [Azure Function output triggers for Notification Hubs](/azure/azure-functions/functions-bindings-notification-hubs), or</span></span>
2. <span data-ttu-id="c9a3f-162">Pomocí [.NET SDK pro Azure](https://blogs.msdn.microsoft.com/azuremobile/2014/04/08/push-notifications-using-notification-hub-and-net-backend/).</span><span class="sxs-lookup"><span data-stu-id="c9a3f-162">By using the [.NET SDK for Azure](https://blogs.msdn.microsoft.com/azuremobile/2014/04/08/push-notifications-using-notification-hub-and-net-backend/).</span></span> <span data-ttu-id="c9a3f-163">Všimněte si, že tyto příklady jsou v jazyce C#.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-163">Note these examples are in C#.</span></span>


## <a name="implementing-webhooks-on-azure-with-f"></a><span data-ttu-id="c9a3f-164">Implementace Webhooky v Azure s F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-164">Implementing WebHooks on Azure with F#</span></span> #

<span data-ttu-id="c9a3f-165">A [Webhooku](https://en.wikipedia.org/wiki/Webhook) je zpětné volání aktivaci prostřednictvím webového požadavku.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-165">A [Webhook](https://en.wikipedia.org/wiki/Webhook) is a callback triggered via a web request.</span></span> <span data-ttu-id="c9a3f-166">Webhooky jsou používány webů, jako je Githubu na signál události.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-166">Webhooks are used by sites such as GitHub to signal events.</span></span> 

<span data-ttu-id="c9a3f-167">Webhooky můžete implementovat v jazyce F # a hostované v Azure pomocí [funkce Azure v F # s Webhooku vazbou](/azure/azure-functions/functions-bindings-http-webhook).</span><span class="sxs-lookup"><span data-stu-id="c9a3f-167">Webhooks can be implemented in F# and hosted on Azure via an [Azure Function in F# with a Webhook Binding](/azure/azure-functions/functions-bindings-http-webhook).</span></span>

## <a name="using-webjobs-with-f"></a><span data-ttu-id="c9a3f-168">Pomocí Webjobs F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-168">Using Webjobs with F#</span></span> #

<span data-ttu-id="c9a3f-169">[Webjobs](/azure/app-service-web/web-sites-create-web-jobs) se o programy, které lze spustit ve vaší webové aplikace služby App Service třemi způsoby: na vyžádání, nepřetržitě, nebo podle plánu.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-169">[Webjobs](/azure/app-service-web/web-sites-create-web-jobs) are programs you can run in your App Service web app in three ways: on demand, continuously, or on a schedule.</span></span>

[<span data-ttu-id="c9a3f-170">Příklad F # webovou úlohu</span><span class="sxs-lookup"><span data-stu-id="c9a3f-170">Example F# Webjob</span></span>](https://github.com/andredublin/fsharp-azure-webjob)

## <a name="implementing-timers-on-azure-with-f"></a><span data-ttu-id="c9a3f-171">Implementace časovače v Azure s F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-171">Implementing Timers on Azure with F#</span></span> #

<span data-ttu-id="c9a3f-172">Časovač spustí podle plánu, jednorázově nebo opakovaně volat funkce.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-172">Timer triggers call functions based on a schedule, one time or recurring.</span></span>

<span data-ttu-id="c9a3f-173">Časovače můžete implementovat v jazyce F # a hostované v Azure pomocí [funkce Azure v F # s aktivační událost časovače](/azure/azure-functions/functions-bindings-timer).</span><span class="sxs-lookup"><span data-stu-id="c9a3f-173">Timers can be implemented in F# and hosted on Azure via an [Azure Function in F# with a Timer Trigger](/azure/azure-functions/functions-bindings-timer).</span></span>

## <a name="deploying-and-managing-azure-resources-with-f-scripts"></a><span data-ttu-id="c9a3f-174">Nasazení a správě prostředků Azure pomocí skriptů F #</span><span class="sxs-lookup"><span data-stu-id="c9a3f-174">Deploying and Managing Azure Resources with F# Scripts</span></span> #

<span data-ttu-id="c9a3f-175">Virtuální počítače Azure mohou prostřednictvím kódu programu nasadit a spravovat z F # skripty pomocí rozhraní API a Microsoft.Azure.Management balíčky.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-175">Azure VMs may be programmatically deployed and managed from F# scripts by using the Microsoft.Azure.Management packages and APIs.</span></span> <span data-ttu-id="c9a3f-176">Například v tématu [začít pracovat s knihovnami správu pro platformu .NET](https://msdn.microsoft.com/library/dn722415.aspx) a [pomocí Azure Resource Manager](/azure/azure-resource-manager/resource-manager-deployment-model).</span><span class="sxs-lookup"><span data-stu-id="c9a3f-176">For example, see [Get Started with the Management Libraries for .NET](https://msdn.microsoft.com/library/dn722415.aspx) and [Using Azure Resource Manager](/azure/azure-resource-manager/resource-manager-deployment-model).</span></span>

<span data-ttu-id="c9a3f-177">Podobně ostatní prostředky služby Azure mohou také nasazení a spravovat z F # skripty s použitím komponenty stejné.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-177">Likewise, other Azure resources may also be deployed and managed from F# scripts using the same components.</span></span> <span data-ttu-id="c9a3f-178">Můžete například vytvořit účty úložiště, nasazení Azure Cloud Services, vytváření instancí služby Azure DocumentDB a spravovat centra oznámení Azure prostřednictvím kódu programu z F # skriptů.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-178">For example, you can create storage accounts, deploy Azure Cloud Services, create Azure DocumentDB instances and manage Azure Notifcation Hubs programmatically from F# scripts.</span></span>

<span data-ttu-id="c9a3f-179">Pomocí skriptů F # pro nasazení a správě prostředků není obvykle nutné.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-179">Using F# scripts to deploy and manage resources is not normally necessary.</span></span> <span data-ttu-id="c9a3f-180">Prostředky Azure může být například také nasazené přímo z JSON šablony popisy, které lze nastavit parametry.</span><span class="sxs-lookup"><span data-stu-id="c9a3f-180">For example, Azure resources may also be deployed directy from JSON template descriptions, which can be parameterized.</span></span> <span data-ttu-id="c9a3f-181">V tématu [šablon Azure Resource Manageru](/azure/azure-resource-manager/resource-manager-template-best-practices) včetně příkladů, jako [šablon Azure rychlý Start](https://azure.microsoft.com/documentation/templates/).</span><span class="sxs-lookup"><span data-stu-id="c9a3f-181">See [Azure Resource Manager Templates](/azure/azure-resource-manager/resource-manager-template-best-practices) including examples such as the [Azure Quickstart Templates](https://azure.microsoft.com/documentation/templates/).</span></span>

## <a name="other-resources"></a><span data-ttu-id="c9a3f-182">Další zdroje</span><span class="sxs-lookup"><span data-stu-id="c9a3f-182">Other resources</span></span>

* [<span data-ttu-id="c9a3f-183">Úplnou dokumentaci o všech služeb Azure</span><span class="sxs-lookup"><span data-stu-id="c9a3f-183">Full documentation on all Azure services</span></span>](/azure/)