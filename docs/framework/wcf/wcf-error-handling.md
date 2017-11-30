---
title: "Zpracování chyb WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c5fa1aea718f3904eab38927d24a851043bbd896
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-error-handling"></a><span data-ttu-id="be124-102">Zpracování chyb WCF</span><span class="sxs-lookup"><span data-stu-id="be124-102">WCF Error Handling</span></span>
<span data-ttu-id="be124-103">Chyby, kterými aplikace WCF patřit do jedné ze tří skupin:</span><span class="sxs-lookup"><span data-stu-id="be124-103">The errors encountered by a WCF application belong to one of three groups:</span></span>  
  
1.  <span data-ttu-id="be124-104">Chyby komunikace</span><span class="sxs-lookup"><span data-stu-id="be124-104">Communication Errors</span></span>  
  
2.  <span data-ttu-id="be124-105">Proxy server/kanál chyby</span><span class="sxs-lookup"><span data-stu-id="be124-105">Proxy/Channel Errors</span></span>  
  
3.  <span data-ttu-id="be124-106">Chyby aplikace</span><span class="sxs-lookup"><span data-stu-id="be124-106">Application Errors</span></span>  
  
 <span data-ttu-id="be124-107">Dochází k chybám komunikace, když síť není k dispozici, klient používá adresu nesprávný nebo hostitele služby nenaslouchá pro příchozí zprávy.</span><span class="sxs-lookup"><span data-stu-id="be124-107">Communication errors occur when a network is unavailable, a client uses an incorrect address, or the service host is not listening for incoming messages.</span></span> <span data-ttu-id="be124-108">Chyby tohoto typu se vrátí klientovi jako <xref:System.ServiceModel.CommunicationException> nebo <xref:System.ServiceModel.CommunicationException>-odvozených třídách.</span><span class="sxs-lookup"><span data-stu-id="be124-108">Errors of this type are returned to the client as <xref:System.ServiceModel.CommunicationException> or <xref:System.ServiceModel.CommunicationException>-derived classes.</span></span>  
  
 <span data-ttu-id="be124-109">Proxy server/kanál chyby jsou chyby, které se vyskytují v kanálu nebo proxy, sám sebe.</span><span class="sxs-lookup"><span data-stu-id="be124-109">Proxy/Channel errors are errors that occur within the channel or proxy itself.</span></span> <span data-ttu-id="be124-110">Chyby tohoto typu patří: pokouší použít server proxy nebo kanálu, který byl uzavřen, existuje neshoda kontrakt mezi klientem a službou nebo odmítne pověření klienta služby.</span><span class="sxs-lookup"><span data-stu-id="be124-110">Errors of this type include: attempting to use a proxy or channel that has been closed, a contract mismatch exists between the client and service, or the client’s credentials are rejected by the service.</span></span> <span data-ttu-id="be124-111">Existuje mnoho různých typů chyb v této kategorii příliš mnoho seznam sem.</span><span class="sxs-lookup"><span data-stu-id="be124-111">There are many different types of errors in this category, too many to list here.</span></span> <span data-ttu-id="be124-112">Chyby tohoto typu se vrátí klientovi jako-je (na objekty výjimek není provedena žádná transformace).</span><span class="sxs-lookup"><span data-stu-id="be124-112">Errors of this type are returned to the client as-is (no transformation is performed on the exception objects).</span></span>  
  
 <span data-ttu-id="be124-113">Chyby aplikace, ke kterým došlo během provádění operace služby.</span><span class="sxs-lookup"><span data-stu-id="be124-113">Application errors occur during the execution of a service operation.</span></span> <span data-ttu-id="be124-114">Chyby tohoto druhu, jsou odeslány klientovi jako <xref:System.ServiceModel.FaultException> nebo <xref:System.ServiceModel.FaultException%601>.</span><span class="sxs-lookup"><span data-stu-id="be124-114">Errors of this kind are sent to the client as <xref:System.ServiceModel.FaultException> or <xref:System.ServiceModel.FaultException%601>.</span></span>  
  
 <span data-ttu-id="be124-115">Zpracování chyb v WCF se provádí jednou nebo více z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="be124-115">Error handling in WCF is performed by one or more of the following:</span></span>  
  
-   <span data-ttu-id="be124-116">Přímo zpracování došlo k výjimce.</span><span class="sxs-lookup"><span data-stu-id="be124-116">Directly handling the exception thrown.</span></span> <span data-ttu-id="be124-117">Důvodem je pouze pro komunikaci a proxy serveru nebo kanály.</span><span class="sxs-lookup"><span data-stu-id="be124-117">This is only done for communication and proxy/channel errors.</span></span>  
  
-   <span data-ttu-id="be124-118">Použití kontraktů selhání</span><span class="sxs-lookup"><span data-stu-id="be124-118">Using fault contracts</span></span>  
  
-   <span data-ttu-id="be124-119">Implementace <xref:System.ServiceModel.Dispatcher.IErrorHandler> rozhraní</span><span class="sxs-lookup"><span data-stu-id="be124-119">Implementing the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface</span></span>  
  
-   <span data-ttu-id="be124-120">Zpracování <xref:System.ServiceModel.ServiceHost> události</span><span class="sxs-lookup"><span data-stu-id="be124-120">Handling <xref:System.ServiceModel.ServiceHost> events</span></span>  
  
## <a name="fault-contracts"></a><span data-ttu-id="be124-121">Kontrakty selhání</span><span class="sxs-lookup"><span data-stu-id="be124-121">Fault Contracts</span></span>  
 <span data-ttu-id="be124-122">Kontrakty selhání umožňují definovat chybách, ke kterým může dojít během operace služby na platformě nezávislý způsobem.</span><span class="sxs-lookup"><span data-stu-id="be124-122">Fault contracts allow you to define the errors that can occur during service operation in a platform independent way.</span></span> <span data-ttu-id="be124-123">Ve výchozím nastavení všechny výjimky vyvolány z v rámci operace služby bude vrácen do klienta jako <xref:System.ServiceModel.FaultException> objektu.</span><span class="sxs-lookup"><span data-stu-id="be124-123">By default all exceptions thrown from within a service operation will be returned to the client as a <xref:System.ServiceModel.FaultException> object.</span></span> <span data-ttu-id="be124-124"><xref:System.ServiceModel.FaultException> Objektu bude obsahovat velmi málo informací.</span><span class="sxs-lookup"><span data-stu-id="be124-124">The <xref:System.ServiceModel.FaultException> object will contain very little information.</span></span> <span data-ttu-id="be124-125">Můžete řídit informace odesílané do klienta definování kontraktu odolnost a vrací chybu jako <xref:System.ServiceModel.FaultException%601>.</span><span class="sxs-lookup"><span data-stu-id="be124-125">You can control the information sent to the client by defining a fault contract and returning the error as a <xref:System.ServiceModel.FaultException%601>.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="be124-126">[Určování a zpracování chyb v kontraktech a službách](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="be124-126"> [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
## <a name="ierrorhandler"></a><span data-ttu-id="be124-127">IErrorHandler</span><span class="sxs-lookup"><span data-stu-id="be124-127">IErrorHandler</span></span>  
 <span data-ttu-id="be124-128"><xref:System.ServiceModel.Dispatcher.IErrorHandler> Rozhraní vám umožní větší kontrolu nad jak aplikace WCF reagují na chyby.</span><span class="sxs-lookup"><span data-stu-id="be124-128">The <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface allows you more control over how your WCF application responds to errors.</span></span>  <span data-ttu-id="be124-129">Nabízí plnou kontrolu nad chybová zpráva, která je vrácen do klienta a umožňuje provádět vlastní chyba při zpracování například protokolování.</span><span class="sxs-lookup"><span data-stu-id="be124-129">It gives you full control over the fault message that is returned to the client and allows you to perform custom error processing such as logging.</span></span>  [!INCLUDE[crdefault](../../../includes/crabout-md.md)]<span data-ttu-id="be124-130"><xref:System.ServiceModel.Dispatcher.IErrorHandler> a [rozšíření kontroly nad zpracováním a vykazováním chyb](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)</span><span class="sxs-lookup"><span data-stu-id="be124-130"> <xref:System.ServiceModel.Dispatcher.IErrorHandler> and [Extending Control Over Error Handling and Reporting](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)</span></span>  
  
## <a name="servicehost-events"></a><span data-ttu-id="be124-131">Hostitel služby události</span><span class="sxs-lookup"><span data-stu-id="be124-131">ServiceHost Events</span></span>  
 <span data-ttu-id="be124-132"><xref:System.ServiceModel.ServiceHost> Třídy hostitelů služby a definuje několik událostí, které mohou být potřebné pro zpracování chyb.</span><span class="sxs-lookup"><span data-stu-id="be124-132">The <xref:System.ServiceModel.ServiceHost> class hosts services and defines several events that may be needed for handling errors.</span></span> <span data-ttu-id="be124-133">Příklad:</span><span class="sxs-lookup"><span data-stu-id="be124-133">For example:</span></span>  
  
1.  <!--zz <xref:System.ServiceModel.ServiceHost.Faulted>-->  `System.ServiceModel.ServiceHost.Faulted`
  
2. <!--zz  <xref:System.ServiceModel.ServiceHost.UnknownMessageReceived>  --> `System.ServiceModel.ServiceHost.UnknownMessageReceived`
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="be124-134"><xref:System.ServiceModel.ServiceHost></span><span class="sxs-lookup"><span data-stu-id="be124-134"> <xref:System.ServiceModel.ServiceHost></span></span>