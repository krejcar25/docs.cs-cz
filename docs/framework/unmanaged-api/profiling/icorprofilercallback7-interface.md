---
title: "ICorProfilerCallback7 rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8eb370e4f16212c536c252661163b7eca6f74d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="1d63e-102">ICorProfilerCallback7 rozhraní</span><span class="sxs-lookup"><span data-stu-id="1d63e-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="1d63e-103">[Podporované v rozhraní .NET Framework 4.6.1 a novějších verzích]</span><span class="sxs-lookup"><span data-stu-id="1d63e-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="1d63e-104">Podtřídou třídy [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) , který poskytuje metody zpětného volání, která používá modul common language runtime profileru oznámit, že se aktualizuje symbol datový proud přidružený modul v paměti.</span><span class="sxs-lookup"><span data-stu-id="1d63e-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d63e-105">Metody</span><span class="sxs-lookup"><span data-stu-id="1d63e-105">Methods</span></span>  
  
|<span data-ttu-id="1d63e-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="1d63e-106">Method</span></span>|<span data-ttu-id="1d63e-107">Popis</span><span class="sxs-lookup"><span data-stu-id="1d63e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d63e-108">ModuleInMemorySymbolsUpdated – metoda</span><span class="sxs-lookup"><span data-stu-id="1d63e-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="1d63e-109">Upozorní profileru, že se aktualizuje symbol datový proud přidružený modul v paměti.</span><span class="sxs-lookup"><span data-stu-id="1d63e-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d63e-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="1d63e-110">Requirements</span></span>  
 <span data-ttu-id="1d63e-111">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d63e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d63e-112">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d63e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d63e-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d63e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d63e-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="1d63e-114">See Also</span></span>  
 [<span data-ttu-id="1d63e-115">Rozhraní pro profilaci</span><span class="sxs-lookup"><span data-stu-id="1d63e-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)