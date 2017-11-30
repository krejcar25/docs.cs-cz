---
title: "Přenosy ve službě Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 115e2a69c7d990c7d4c59634644fb557e83ad405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="126fc-102">Přenosy ve službě Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="126fc-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="126fc-103">Přenosová vrstva je na nejnižší úrovni kanálu zásobníku.</span><span class="sxs-lookup"><span data-stu-id="126fc-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="126fc-104">Hlavní přenosy použít v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] jsou HTTP, HTTPS, TCP a pojmenované kanály.</span><span class="sxs-lookup"><span data-stu-id="126fc-104">The main transports used in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="126fc-105">Témata v této části popisují výběru mezi tyto přenosy, konfigurace přenosu a nastavení, ladění vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="126fc-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="126fc-106">zahrnuje další přenosy.</span><span class="sxs-lookup"><span data-stu-id="126fc-106"> includes additional transports.</span></span> <span data-ttu-id="126fc-107">Informace o přenosu služby Řízení front zpráv (MSMQ) najdete v tématu [fronty a spolehlivé relace](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="126fc-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="126fc-108">Informace o přenosu peer-to-peer najdete v tématu [Peer-to-Peer sítě](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="126fc-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="126fc-109">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="126fc-109">In This Section</span></span>  
 [<span data-ttu-id="126fc-110">Volba přenosu</span><span class="sxs-lookup"><span data-stu-id="126fc-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="126fc-111">Popisuje tři hlavní přenosy a zvolením některé aspekty.</span><span class="sxs-lookup"><span data-stu-id="126fc-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="126fc-112">Výběr kodéru zprávy</span><span class="sxs-lookup"><span data-stu-id="126fc-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="126fc-113">Popisuje faktory, které je třeba zvážit při výběru element vazby kódování zprávy.</span><span class="sxs-lookup"><span data-stu-id="126fc-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="126fc-114">Streamování přenosu zpráv</span><span class="sxs-lookup"><span data-stu-id="126fc-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="126fc-115">Popisuje postup konfigurace přenosové vrstvy udělat streamování.</span><span class="sxs-lookup"><span data-stu-id="126fc-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="126fc-116">Konfigurace HTTP a HTTPS</span><span class="sxs-lookup"><span data-stu-id="126fc-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="126fc-117">Popisuje postup konfigurace elementů vazby přenosu HTTP a HTTPS.</span><span class="sxs-lookup"><span data-stu-id="126fc-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="126fc-118">Postupy: nahrazení rezervace adresy URL WCF omezenou rezervací</span><span class="sxs-lookup"><span data-stu-id="126fc-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="126fc-119">Popisuje způsob použití [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]omezený rezervace adresy URL.</span><span class="sxs-lookup"><span data-stu-id="126fc-119">Describes how to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]URL restricted reservations.</span></span>  
  
 [<span data-ttu-id="126fc-120">Přenosové kvóty</span><span class="sxs-lookup"><span data-stu-id="126fc-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="126fc-121">Popisuje důležité informace o nastavení kvóty, které jsou k dispozici v přenosové vrstvě.</span><span class="sxs-lookup"><span data-stu-id="126fc-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="126fc-122">Práce se zařízeními NAT a brány firewall</span><span class="sxs-lookup"><span data-stu-id="126fc-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="126fc-123">Popisuje postup konfigurace přenosové vrstvy, když jsou zprávy odesílané nebo přijímané za bránou firewall nebo když se nachází překlad síťových adres (NAT).</span><span class="sxs-lookup"><span data-stu-id="126fc-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="126fc-124">Sdílení portů Net.TCP</span><span class="sxs-lookup"><span data-stu-id="126fc-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="126fc-125">Popisuje postup používání sdílení portů Net.TCP komponenta [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="126fc-125">Describes how to use the Net.TCP Port Sharing component of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="126fc-126">Odkaz</span><span class="sxs-lookup"><span data-stu-id="126fc-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="126fc-127">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="126fc-127">Related Sections</span></span>  
 [<span data-ttu-id="126fc-128">Vazby</span><span class="sxs-lookup"><span data-stu-id="126fc-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="126fc-129">Rozšiřování vazeb</span><span class="sxs-lookup"><span data-stu-id="126fc-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)