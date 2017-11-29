---
title: "IGCHost2 – rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost2
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost2
helpviewer_keywords: IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c6706696e3fd5158d2b49a4d114d978a26510b67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="igchost2-interface"></a><span data-ttu-id="d8484-102">IGCHost2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="d8484-102">IGCHost2 Interface</span></span>
<span data-ttu-id="d8484-103">Poskytuje metody pro získání informací o systém kolekce paměti a řízení některých aspektů uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="d8484-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8484-104">Pro nový vývoj, doporučujeme použít [iclrgcmanager2 –](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) místo toho rozhraní.</span><span class="sxs-lookup"><span data-stu-id="d8484-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8484-105">Metody</span><span class="sxs-lookup"><span data-stu-id="d8484-105">Methods</span></span>  
  
|<span data-ttu-id="d8484-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="d8484-106">Method</span></span>|<span data-ttu-id="d8484-107">Popis</span><span class="sxs-lookup"><span data-stu-id="d8484-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8484-108">Setgcstartuplimitsex – metoda</span><span class="sxs-lookup"><span data-stu-id="d8484-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="d8484-109">Nastaví velikost segmentu a maximální velikost pro generování 0.</span><span class="sxs-lookup"><span data-stu-id="d8484-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="d8484-110">Umožňuje 0. generace a velikost segmentu větší než `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="d8484-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8484-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d8484-111">Requirements</span></span>  
 <span data-ttu-id="d8484-112">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8484-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8484-113">**Záhlaví:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="d8484-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="d8484-114">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8484-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8484-115">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8484-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8484-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="d8484-116">See Also</span></span>  
 [<span data-ttu-id="d8484-117">Rozhraní hostování</span><span class="sxs-lookup"><span data-stu-id="d8484-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="d8484-118">Rozhraní hostování CLR</span><span class="sxs-lookup"><span data-stu-id="d8484-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="d8484-119">Corruntimehost – třída typu Coclass</span><span class="sxs-lookup"><span data-stu-id="d8484-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)