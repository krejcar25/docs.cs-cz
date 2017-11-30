---
title: "ICorDebugThread3::GetActiveInternalFrames – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.GetActiveInternalFrames Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9b94827ac49c69c5e72c2e300a80914774cc498
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="f6822-102">ICorDebugThread3::GetActiveInternalFrames – metoda</span><span class="sxs-lookup"><span data-stu-id="f6822-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="f6822-103">Vrátí pole interní rámce ([icordebuginternalframe2 –](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objekty) v zásobníku.</span><span class="sxs-lookup"><span data-stu-id="f6822-103">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6822-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f6822-104">Syntax</span></span>  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6822-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f6822-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="f6822-106">[v] Počet interní rámce v očekává `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="f6822-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="f6822-107">[out] Ukazatel na `ULONG32` obsahující počet interní rámce v zásobníku.</span><span class="sxs-lookup"><span data-stu-id="f6822-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="f6822-108">[ve out] Ukazatel na adresu pole interní rámce v zásobníku.</span><span class="sxs-lookup"><span data-stu-id="f6822-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6822-109">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="f6822-109">Return Value</span></span>  
 <span data-ttu-id="f6822-110">Tato metoda vrátí následující konkrétní hodnoty HRESULT a také HRESULT chyby, které označují selhání metoda.</span><span class="sxs-lookup"><span data-stu-id="f6822-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f6822-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6822-111">HRESULT</span></span>|<span data-ttu-id="f6822-112">Popis</span><span class="sxs-lookup"><span data-stu-id="f6822-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6822-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6822-113">S_OK</span></span>|<span data-ttu-id="f6822-114">[Icordebuginternalframe2 –](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objekt byl úspěšně vytvořen.</span><span class="sxs-lookup"><span data-stu-id="f6822-114">The [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="f6822-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f6822-115">E_INVALIDARG</span></span>|<span data-ttu-id="f6822-116">`cInternalFrames`není nula a `ppInternalFrames` je `null`, nebo `pcInternalFrames` je `null`.</span><span class="sxs-lookup"><span data-stu-id="f6822-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="f6822-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="f6822-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="f6822-118">`ppInternalFrames`je menší než počet interní rámce.</span><span class="sxs-lookup"><span data-stu-id="f6822-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f6822-119">Výjimky</span><span class="sxs-lookup"><span data-stu-id="f6822-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6822-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f6822-120">Remarks</span></span>  
 <span data-ttu-id="f6822-121">Interní rámce jsou vloženy do zásobníku modulem runtime pro uložení dočasných dat datové struktury.</span><span class="sxs-lookup"><span data-stu-id="f6822-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="f6822-122">Při prvním volání `GetActiveInternalFrames`, byste měli nastavit `cInternalFrames` parametru na hodnotu 0 (nula) a `ppInternalFrames` parametr na hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="f6822-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="f6822-123">Když `GetActiveInternalFrames` nejprve vrátí, `pcInternalFrames` obsahuje počet interní rámce v zásobníku.</span><span class="sxs-lookup"><span data-stu-id="f6822-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="f6822-124">`GetActiveInternalFrames`by pak volat ještě jednou.</span><span class="sxs-lookup"><span data-stu-id="f6822-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="f6822-125">By měla předávat správný počet (`pcInternalFrames`) v `cInternalFrames` parametr, a zadejte ukazatel na odpovídajícím způsobem velikosti pole v `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="f6822-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="f6822-126">Použití [icordebugstackwalk::getframe –](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) metoda vrátí skutečné zásobníku.</span><span class="sxs-lookup"><span data-stu-id="f6822-126">Use the [ICorDebugStackWalk::GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6822-127">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f6822-127">Requirements</span></span>  
 <span data-ttu-id="f6822-128">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6822-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6822-129">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6822-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6822-130">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6822-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6822-131">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6822-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6822-132">Viz také</span><span class="sxs-lookup"><span data-stu-id="f6822-132">See Also</span></span>  
 [<span data-ttu-id="f6822-133">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="f6822-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f6822-134">Ladění</span><span class="sxs-lookup"><span data-stu-id="f6822-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)