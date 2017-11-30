---
title: "COR_PRF_GC_ROOT_FLAGS – výčet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords: COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f340f9ad83d28b00054a0997bf4b60c750192bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="45028-102">COR_PRF_GC_ROOT_FLAGS – výčet</span><span class="sxs-lookup"><span data-stu-id="45028-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="45028-103">Určuje vlastnost kořenové kolekce paměti.</span><span class="sxs-lookup"><span data-stu-id="45028-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45028-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="45028-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="45028-105">Členové</span><span class="sxs-lookup"><span data-stu-id="45028-105">Members</span></span>  
  
|<span data-ttu-id="45028-106">Člen</span><span class="sxs-lookup"><span data-stu-id="45028-106">Member</span></span>|<span data-ttu-id="45028-107">Popis</span><span class="sxs-lookup"><span data-stu-id="45028-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="45028-108">Kořenové zabraňuje uvolňování z přesunutí objektu.</span><span class="sxs-lookup"><span data-stu-id="45028-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="45028-109">Kořenové nezabrání uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="45028-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="45028-110">Kořenové odkazuje na pole objektu, nikoli samotného objektu.</span><span class="sxs-lookup"><span data-stu-id="45028-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="45028-111">Kořenové zabraňuje uvolňování paměti, pokud je tento počet odkaz objektu určitou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="45028-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45028-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="45028-112">Remarks</span></span>  
 <span data-ttu-id="45028-113">`COR_PRF_GC_ROOT_FLAGS`je bitová maska, která poskytuje další informace o speciální kořenových certifikačních autorit.</span><span class="sxs-lookup"><span data-stu-id="45028-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="45028-114">Ne všechny kořenové adresáře jsou ale zvláštní.</span><span class="sxs-lookup"><span data-stu-id="45028-114">However, not all roots are special.</span></span> <span data-ttu-id="45028-115">Například některé kořeny nejsou slabé odkazy, vnitřních ukazatelů, definovaného a započítány odkaz.</span><span class="sxs-lookup"><span data-stu-id="45028-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="45028-116">U takových kořenových certifikačních autorit neexistují žádné příznaky k předání informací o tom.</span><span class="sxs-lookup"><span data-stu-id="45028-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="45028-117">Proto metody, které používají tento výčet, jako [icorprofilercallback2::rootreferences2 –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) metoda, odeslání 0 bitové masky příznaky, která určuje, že všechny flags jsou vypnuté.</span><span class="sxs-lookup"><span data-stu-id="45028-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45028-118">Požadavky</span><span class="sxs-lookup"><span data-stu-id="45028-118">Requirements</span></span>  
 <span data-ttu-id="45028-119">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45028-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45028-120">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45028-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45028-121">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45028-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45028-122">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45028-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45028-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="45028-123">See Also</span></span>  
 [<span data-ttu-id="45028-124">Profilace výčtů</span><span class="sxs-lookup"><span data-stu-id="45028-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)