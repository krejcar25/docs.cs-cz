---
title: "ICLRDataTarget – rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget
helpviewer_keywords: ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a40276b28f3d20428f0d7eb0556a762fdb56801
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="04f96-102">ICLRDataTarget – rozhraní</span><span class="sxs-lookup"><span data-stu-id="04f96-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="04f96-103">Poskytuje metody pro interakci s cílová položka common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="04f96-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04f96-104">Metody</span><span class="sxs-lookup"><span data-stu-id="04f96-104">Methods</span></span>  
  
|<span data-ttu-id="04f96-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-105">Method</span></span>|<span data-ttu-id="04f96-106">Popis</span><span class="sxs-lookup"><span data-stu-id="04f96-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04f96-107">GetCurrentThreadId – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="04f96-108">Získá identifikátor pro aktuální vlákno.</span><span class="sxs-lookup"><span data-stu-id="04f96-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="04f96-109">Getimagebase – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="04f96-110">Získá adresu základní paměti pro zadanou bitovou kopii.</span><span class="sxs-lookup"><span data-stu-id="04f96-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="04f96-111">Getmachinetype – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="04f96-112">Získá identifikátor pro druh sada instrukcí, která používá tento cílový proces.</span><span class="sxs-lookup"><span data-stu-id="04f96-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="04f96-113">Getpointersize – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="04f96-114">Získá velikost v bajtech ukazatel na aktuální cíl.</span><span class="sxs-lookup"><span data-stu-id="04f96-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="04f96-115">Getthreadcontext – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="04f96-116">Získá ukazatel do kontextu vlákno se zadaným identifikátorem.</span><span class="sxs-lookup"><span data-stu-id="04f96-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="04f96-117">Gettlsvalue – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="04f96-118">Získá hodnotu v místní úložiště vláken (TLS) v zadaném indexu pro zadaný vlákno.</span><span class="sxs-lookup"><span data-stu-id="04f96-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="04f96-119">Readvirtual – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="04f96-120">Čte data z adresy zadaný virtuální paměti do zadané vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="04f96-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="04f96-121">Request – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="04f96-122">Voláno rozhraním běžné jazyk služby modulu runtime (CLR) data přístup požádat o operaci podle definice implementace.</span><span class="sxs-lookup"><span data-stu-id="04f96-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="04f96-123">Setthreadcontext – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="04f96-124">Nastaví aktuální kontext zadaný vlákno v tento cílový proces.</span><span class="sxs-lookup"><span data-stu-id="04f96-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="04f96-125">Settlsvalue – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="04f96-126">Nastaví hodnotu v místní úložiště vláken (TLS) zadaný vlákna v tento cílový proces.</span><span class="sxs-lookup"><span data-stu-id="04f96-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="04f96-127">Writevirtual – metoda</span><span class="sxs-lookup"><span data-stu-id="04f96-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="04f96-128">Zapíše data ze zadané vyrovnávací paměti na adresu zadanou virtuální paměti.</span><span class="sxs-lookup"><span data-stu-id="04f96-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04f96-129">Poznámky</span><span class="sxs-lookup"><span data-stu-id="04f96-129">Remarks</span></span>  
 <span data-ttu-id="04f96-130">Toto rozhraní podle potřeby pro konkrétní cílový položku musí implementovat rozhraní API klienta (ladicí program).</span><span class="sxs-lookup"><span data-stu-id="04f96-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="04f96-131">Například živý proces bude mít jinou implementaci než výpis paměti.</span><span class="sxs-lookup"><span data-stu-id="04f96-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f96-132">Požadavky</span><span class="sxs-lookup"><span data-stu-id="04f96-132">Requirements</span></span>  
 <span data-ttu-id="04f96-133">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04f96-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04f96-134">**Záhlaví:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="04f96-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="04f96-135">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04f96-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04f96-136">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04f96-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f96-137">Viz také</span><span class="sxs-lookup"><span data-stu-id="04f96-137">See Also</span></span>  
 [<span data-ttu-id="04f96-138">Iclrdatatarget2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="04f96-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="04f96-139">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="04f96-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)