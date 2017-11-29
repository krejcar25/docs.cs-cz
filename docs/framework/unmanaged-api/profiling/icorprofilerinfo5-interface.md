---
title: "Rozhraní ICorProfilerInfo5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo5
api_location: mscorwks.dll
api_type: COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84744474b9eca96cae5e96b8c4eadc4109f85f82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="c3006-102">Rozhraní ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="c3006-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="c3006-103">[Podporované v rozhraní .NET Framework 4.5.2 a novějších verzích]</span><span class="sxs-lookup"><span data-stu-id="c3006-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c3006-104">Podtřídou třídy [icorprofilerinfo4 –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) , který poskytuje metody pro použití profilery kódu ke komunikaci s modul CLR (CLR) řízení události monitorování.</span><span class="sxs-lookup"><span data-stu-id="c3006-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3006-105">Metody</span><span class="sxs-lookup"><span data-stu-id="c3006-105">Methods</span></span>  
  
|<span data-ttu-id="c3006-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="c3006-106">Method</span></span>|<span data-ttu-id="c3006-107">Popis</span><span class="sxs-lookup"><span data-stu-id="c3006-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3006-108">Metoda GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="c3006-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="c3006-109">Získá aktuální kategorií událostí, pro které profileru chce dostávat oznámení z modulu CLR.</span><span class="sxs-lookup"><span data-stu-id="c3006-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="c3006-110">Metoda SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="c3006-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="c3006-111">Nastaví hodnotu, která určuje typy událostí, pro které profileru chce dostávat oznámení událostí z modulu CLR.</span><span class="sxs-lookup"><span data-stu-id="c3006-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3006-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c3006-112">Remarks</span></span>  
 <span data-ttu-id="c3006-113">Dostupné metody u tohoto rozhraní slouží k nahrazení [icorprofilerinfo::geteventmask –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) a [icorprofilerinfo::seteventmask –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metody.</span><span class="sxs-lookup"><span data-stu-id="c3006-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3006-114">Požadavky</span><span class="sxs-lookup"><span data-stu-id="c3006-114">Requirements</span></span>  
 <span data-ttu-id="c3006-115">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3006-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3006-116">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3006-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3006-117">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3006-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3006-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="c3006-118">See Also</span></span>  
 [<span data-ttu-id="c3006-119">Rozhraní pro profilaci</span><span class="sxs-lookup"><span data-stu-id="c3006-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)