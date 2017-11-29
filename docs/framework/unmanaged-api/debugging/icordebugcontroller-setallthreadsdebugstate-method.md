---
title: "ICorDebugController::SetAllThreadsDebugState – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.SetAllThreadsDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5a033ef2efd8fa5e3b519e19b62ce2dfb84a5e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="e2188-102">ICorDebugController::SetAllThreadsDebugState – metoda</span><span class="sxs-lookup"><span data-stu-id="e2188-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="e2188-103">Nastaví ladění stav všech spravovaných vláken v procesu.</span><span class="sxs-lookup"><span data-stu-id="e2188-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2188-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e2188-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2188-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e2188-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="e2188-106">[v] Hodnota výčtu "CorDebugThreadState", který určuje stav vláken pro ladění.</span><span class="sxs-lookup"><span data-stu-id="e2188-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="e2188-107">[v] Ukazatel na objekt "ICorDebugThread", který představuje vlákno, aby byla vyjmuta z nastavení stavu ladění.</span><span class="sxs-lookup"><span data-stu-id="e2188-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="e2188-108">Pokud je tato hodnota null, je vyloučené žádný přístup z více vláken.</span><span class="sxs-lookup"><span data-stu-id="e2188-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2188-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e2188-109">Remarks</span></span>  
 <span data-ttu-id="e2188-110">`SetAllThreadsDebugState` Metoda může mít vliv na vláken, které nejsou viditelné prostřednictvím [enumeratethreads – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), tak vláken, které byly pozastaveno s `SetAllThreadsDebugState` metoda bude muset být pokračuje s `SetAllThreadsDebugState` metoda.</span><span class="sxs-lookup"><span data-stu-id="e2188-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2188-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="e2188-111">Requirements</span></span>  
 <span data-ttu-id="e2188-112">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2188-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2188-113">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2188-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2188-114">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2188-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2188-115">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2188-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2188-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="e2188-116">See Also</span></span>  
 