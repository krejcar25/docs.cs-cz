---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b09d7fc476d5eed7f7c534fdde46cb18eeac30d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="84840-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="84840-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="84840-103">Bezpečnostní ověření typu handshake s potenciální sousedním nebyla úspěšná.</span><span class="sxs-lookup"><span data-stu-id="84840-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="84840-104">Popis</span><span class="sxs-lookup"><span data-stu-id="84840-104">Description</span></span>  
 <span data-ttu-id="84840-105">Při pokusu o vytvoření zabezpečeného sousedním připojení dojde k trasování.</span><span class="sxs-lookup"><span data-stu-id="84840-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="84840-106">K tomu dochází z důvodu nedostatečné nebo nesprávné přihlašovací údaje.</span><span class="sxs-lookup"><span data-stu-id="84840-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="84840-107">PeerChannel rozpozná jeden typ tokenu pro silné identifikaci X.509 – certifikáty, které poskytují model silné identity na základě typu ověřování a autorizace, který může být implementováno.</span><span class="sxs-lookup"><span data-stu-id="84840-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="84840-108">PeerChannel taky poskytuje podporu pro jednoduché aplikace pomocí hesla.</span><span class="sxs-lookup"><span data-stu-id="84840-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="84840-109">Hesla je možné jenom do relace; položku Povolit nelze použít k provedení ověřování zpráv.</span><span class="sxs-lookup"><span data-stu-id="84840-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="84840-110">Je to proto symetrický token, který sdílet skupiny partnerských uzlů je obtížné a nevhodných používané při ověřování zdroje.</span><span class="sxs-lookup"><span data-stu-id="84840-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="84840-111">Poradce při potížích</span><span class="sxs-lookup"><span data-stu-id="84840-111">Troubleshooting</span></span>  
 <span data-ttu-id="84840-112">Zajistěte, aby všechny okolí příslušná zabezpečovací přihlašovací údaje.</span><span class="sxs-lookup"><span data-stu-id="84840-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84840-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="84840-113">See Also</span></span>  
 [<span data-ttu-id="84840-114">Zabezpečení rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="84840-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [<span data-ttu-id="84840-115">Trasování</span><span class="sxs-lookup"><span data-stu-id="84840-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="84840-116">Řešení potíží s vaší aplikace pomocí trasování</span><span class="sxs-lookup"><span data-stu-id="84840-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="84840-117">Správa a Diagnostika</span><span class="sxs-lookup"><span data-stu-id="84840-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)