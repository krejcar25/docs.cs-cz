---
title: "Konfigurace ukládání do mezipaměti v síťových aplikací"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: cache [.NET Framework], configuring
ms.assetid: 3f694a1c-de5d-47cf-a6eb-cfc369fb8a9f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3c06c05f2d5102d1822aa11c81f2814090e10ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-caching-in-network-applications"></a><span data-ttu-id="1a690-102">Konfigurace ukládání do mezipaměti v síťových aplikací</span><span class="sxs-lookup"><span data-stu-id="1a690-102">Configuring Caching in Network Applications</span></span>
<span data-ttu-id="1a690-103">Chcete-li konfigurovat ukládání do mezipaměti, je nutné zadat zásady mezipaměti v aplikaci nebo <xref:System.Net.WebRequest> úroveň.</span><span class="sxs-lookup"><span data-stu-id="1a690-103">To configure caching, you must specify a cache policy at the application or <xref:System.Net.WebRequest> level.</span></span> <span data-ttu-id="1a690-104">Následující témata obsahují příklady kódu, která ukazují konfiguraci aplikace a požadavky na používání ukládání do mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="1a690-104">The following topics provide code examples that demonstrate configuring applications and requests to use caching.</span></span>  
  
-   [<span data-ttu-id="1a690-105">Postupy: nastavení zásad na základě umístění mezipaměti pro aplikaci</span><span class="sxs-lookup"><span data-stu-id="1a690-105">How to: Set a Location-Based Cache Policy for an Application</span></span>](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md)  
  
-   [<span data-ttu-id="1a690-106">Postupy: nastavení výchozích zásad založené na čase mezipaměti pro aplikaci</span><span class="sxs-lookup"><span data-stu-id="1a690-106">How to: Set the Default Time-Based Cache Policy for an Application</span></span>](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md)  
  
-   [<span data-ttu-id="1a690-107">Postupy: přizpůsobení zásady založené na čase mezipaměti</span><span class="sxs-lookup"><span data-stu-id="1a690-107">How to: Customize a Time-Based Cache Policy</span></span>](../../../docs/framework/network-programming/how-to-customize-a-time-based-cache-policy.md)  
  
-   [<span data-ttu-id="1a690-108">Postupy: nastavení zásad mezipaměti pro žádost</span><span class="sxs-lookup"><span data-stu-id="1a690-108">How to: Set Cache Policy for a Request</span></span>](../../../docs/framework/network-programming/how-to-set-cache-policy-for-a-request.md)  
  
 <span data-ttu-id="1a690-109">Můžete také nakonfigurovat zásady mezipaměti pomocí aplikace nebo počítač – konfigurační soubory.</span><span class="sxs-lookup"><span data-stu-id="1a690-109">You can also configure cache policy using application or machine configuration files.</span></span> <span data-ttu-id="1a690-110">Pro další informace, najdete v tématu &#124; [ \<requestCaching – > elementu (nastavení sítě)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1a690-110">For more information, see &#124; [\<requestCaching> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a690-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="1a690-111">See Also</span></span>  
 [<span data-ttu-id="1a690-112">Správa mezipaměti pro síťové aplikace</span><span class="sxs-lookup"><span data-stu-id="1a690-112">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="1a690-113">Zásady mezipaměti</span><span class="sxs-lookup"><span data-stu-id="1a690-113">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="1a690-114">Na základě umístění mezipaměti zásad</span><span class="sxs-lookup"><span data-stu-id="1a690-114">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="1a690-115">Zásady založené na čase mezipaměti</span><span class="sxs-lookup"><span data-stu-id="1a690-115">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)