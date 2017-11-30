---
title: "ICorProfilerCallback::ManagedToUnmanagedTransition – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ManagedToUnmanagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9da8dd44d5b87cd1c65b8b8837c9dd378039d332
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="2a78c-102">ICorProfilerCallback::ManagedToUnmanagedTransition – metoda</span><span class="sxs-lookup"><span data-stu-id="2a78c-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="2a78c-103">Upozorní profileru došlo k chybě přechod ze spravovaného kódu na nespravovaný kód.</span><span class="sxs-lookup"><span data-stu-id="2a78c-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a78c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2a78c-104">Syntax</span></span>  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a78c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2a78c-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="2a78c-106">[v] ID funkce, která je volána.</span><span class="sxs-lookup"><span data-stu-id="2a78c-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="2a78c-107">[v] Hodnota [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) výčtu, která určuje, zda přechodu nebo došlo k chybě z důvodu volání nespravovaného kódu ze spravovaného kódu, z důvodu zpětné z některého nespravované spravované funkci.</span><span class="sxs-lookup"><span data-stu-id="2a78c-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a78c-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2a78c-108">Remarks</span></span>  
 <span data-ttu-id="2a78c-109">Pokud hodnota `reason` je COR_PRF_TRANSITION_CALL, funkce ID je, že nespravované funkce, které se nikdy sestavili jsme pomocí kompilátoru za běhu.</span><span class="sxs-lookup"><span data-stu-id="2a78c-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="2a78c-110">Nespravované funkce mají základní informace související s nimi, jako je například název a některá metadata.</span><span class="sxs-lookup"><span data-stu-id="2a78c-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="2a78c-111">Pokud nespravované funkce byla zavolána s použitím implicitního platformy vyvolání (kódu PInvoke), modul runtime nemůže určit cílové volání a hodnotu `functionId` bude mít hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="2a78c-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="2a78c-112">Další informace o implicitní PInvoke najdete v tématu [pomocí zprostředkovatele komunikace C++ (implicitní služba PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="2a78c-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a78c-113">Požadavky</span><span class="sxs-lookup"><span data-stu-id="2a78c-113">Requirements</span></span>  
 <span data-ttu-id="2a78c-114">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a78c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a78c-115">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a78c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a78c-116">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a78c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a78c-117">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a78c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a78c-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="2a78c-118">See Also</span></span>  
 [<span data-ttu-id="2a78c-119">Icorprofilercallback – rozhraní</span><span class="sxs-lookup"><span data-stu-id="2a78c-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="2a78c-120">Unmanagedtomanagedtransition – metoda</span><span class="sxs-lookup"><span data-stu-id="2a78c-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)  
 [<span data-ttu-id="2a78c-121">Použití explicitního volání PInvoke v jazyce C++ (atribut DllImport)</span><span class="sxs-lookup"><span data-stu-id="2a78c-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)