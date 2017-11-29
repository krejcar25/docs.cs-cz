---
title: "Analytické trasování s ETW"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3c9486427660de792091297d2426c970cfe47bc1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="8314d-102">Analytické trasování s ETW</span><span class="sxs-lookup"><span data-stu-id="8314d-102">Analytic Tracing with ETW</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="8314d-103">analytické trasování nabízí způsob, jak zachytit diagnostické informace během provádění [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] služby.</span><span class="sxs-lookup"><span data-stu-id="8314d-103"> analytic tracing offers a way to capture diagnostic information during the execution of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span> [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="8314d-104">analytické trasování událostí jsou vygenerované v klíčové body [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] zásobníku umožňující řešení potíží s [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] služby v produkčním prostředí.</span><span class="sxs-lookup"><span data-stu-id="8314d-104"> analytic tracing events are emitted at key points in the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack to allow troubleshooting of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services in a production environment.</span></span> <span data-ttu-id="8314d-105">Analytické trasování pro [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] služeb má minimální dopad na výkon produktu serveru, který je hostitelem [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] služeb jako tyto události jsou velmi efektivně vygenerované relaci události trasování událostí pro Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="8314d-105">Analytic tracing for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8314d-106">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="8314d-106">In This Section</span></span>  
 [<span data-ttu-id="8314d-107">Analytické trasování – přehled</span><span class="sxs-lookup"><span data-stu-id="8314d-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="8314d-108">Popisuje, jak [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytické trasování funguje v [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8314d-108">Discusses how [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="8314d-109">Dynamické povolování analytického sledování</span><span class="sxs-lookup"><span data-stu-id="8314d-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="8314d-110">Popisuje, jak povolit nebo zakázat trasování dynamicky pomocí trasování událostí pro Windows.</span><span class="sxs-lookup"><span data-stu-id="8314d-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="8314d-111">Konfigurace trasování toku zpráv</span><span class="sxs-lookup"><span data-stu-id="8314d-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="8314d-112">Popisuje postup konfigurace trasování toku zpráv.</span><span class="sxs-lookup"><span data-stu-id="8314d-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="8314d-113">Analytické trasování událostí odkaz</span><span class="sxs-lookup"><span data-stu-id="8314d-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="8314d-114">Příklad ID událostí s úrovní událostí, zprávy o událostech a klíčová slova.</span><span class="sxs-lookup"><span data-stu-id="8314d-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8314d-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="8314d-115">See Also</span></span>  
 [<span data-ttu-id="8314d-116">Služby WCF a trasování událostí pro Windows</span><span class="sxs-lookup"><span data-stu-id="8314d-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="8314d-117">Sledování událostí do událostí trasování v systému Windows</span><span class="sxs-lookup"><span data-stu-id="8314d-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)