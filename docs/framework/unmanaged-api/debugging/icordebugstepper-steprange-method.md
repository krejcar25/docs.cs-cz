---
title: "ICorDebugStepper::StepRange – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72a68000691dd23a55b77265cae839bea8b4ae1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="377b4-102">ICorDebugStepper::StepRange – metoda</span><span class="sxs-lookup"><span data-stu-id="377b4-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="377b4-103">Způsobí, že tento ICorDebugStepper jedním krokem prostřednictvím jeho obsahující přístup z více vláken a vrátí, když dorazí do kódu nad rámec poslední zadaný rozsah.</span><span class="sxs-lookup"><span data-stu-id="377b4-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377b4-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="377b4-104">Syntax</span></span>  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="377b4-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="377b4-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="377b4-106">[v] Nastavte na `true` k krokování s vnořením funkci, která je volána v rámci vlákno.</span><span class="sxs-lookup"><span data-stu-id="377b4-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="377b4-107">Nastavte na `false` krok přes funkci.</span><span class="sxs-lookup"><span data-stu-id="377b4-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="377b4-108">[v] Pole cor_debug_step_range – struktury, z nichž každý určuje rozsah.</span><span class="sxs-lookup"><span data-stu-id="377b4-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="377b4-109">[v] Velikost `ranges` pole.</span><span class="sxs-lookup"><span data-stu-id="377b4-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="377b4-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="377b4-110">Remarks</span></span>  
 <span data-ttu-id="377b4-111">`StepRange` Metoda se dá použít jako [icordebugstepper::Step –](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) metoda, s tím rozdílem, že dokud kód mimo zadaný rozsah nedokončí bylo dosaženo.</span><span class="sxs-lookup"><span data-stu-id="377b4-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="377b4-112">To může být efektivnější než krokování s jedné instrukce v čase.</span><span class="sxs-lookup"><span data-stu-id="377b4-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="377b4-113">Rozsahy jsou zadané jako seznam dvojic posunutí od začátku krokovač rámce.</span><span class="sxs-lookup"><span data-stu-id="377b4-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="377b4-114">Rozsahy jsou relativní vzhledem k kód Microsoft (MSIL intermediate language) metody.</span><span class="sxs-lookup"><span data-stu-id="377b4-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="377b4-115">Volání [icordebugstepper::setrangeil –](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) s `false` aby rozsahy relativně k nativní kód metody.</span><span class="sxs-lookup"><span data-stu-id="377b4-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377b4-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="377b4-116">Requirements</span></span>  
 <span data-ttu-id="377b4-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="377b4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377b4-118">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="377b4-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="377b4-119">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="377b4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="377b4-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377b4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>