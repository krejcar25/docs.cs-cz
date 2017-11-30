---
title: "COR_GC_STAT_TYPES – výčet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_STAT_TYPES
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_STAT_TYPES
helpviewer_keywords: COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4cf66026ecf92d0158a1010e82c078478c280f9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="3663c-102">COR_GC_STAT_TYPES – výčet</span><span class="sxs-lookup"><span data-stu-id="3663c-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="3663c-103">Určuje statistiky, které mají být zaznamenány pro uvolnění paměti.</span><span class="sxs-lookup"><span data-stu-id="3663c-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3663c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3663c-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="3663c-105">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3663c-105">Remarks</span></span>  
 <span data-ttu-id="3663c-106">Tento výčet Určuje, jaké statistické údaje ve [cor_gc_stats –](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) struktura jsou nastavení [iclrgcmanager::getstats –](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="3663c-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="3663c-107">Členové</span><span class="sxs-lookup"><span data-stu-id="3663c-107">Members</span></span>  
  
|<span data-ttu-id="3663c-108">Člen</span><span class="sxs-lookup"><span data-stu-id="3663c-108">Member</span></span>|<span data-ttu-id="3663c-109">Popis</span><span class="sxs-lookup"><span data-stu-id="3663c-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="3663c-110">Zaznamenává počet kolekce provést pro každou generaci.</span><span class="sxs-lookup"><span data-stu-id="3663c-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="3663c-111">Zaznamenává paměť a využití paměti kolekce velikost statistiky.</span><span class="sxs-lookup"><span data-stu-id="3663c-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3663c-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="3663c-112">Requirements</span></span>  
 <span data-ttu-id="3663c-113">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3663c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3663c-114">**Záhlaví:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="3663c-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="3663c-115">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3663c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3663c-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="3663c-116">See Also</span></span>  
 [<span data-ttu-id="3663c-117">Cor_gc_stats – struktura</span><span class="sxs-lookup"><span data-stu-id="3663c-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="3663c-118">Výčty hostování</span><span class="sxs-lookup"><span data-stu-id="3663c-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)