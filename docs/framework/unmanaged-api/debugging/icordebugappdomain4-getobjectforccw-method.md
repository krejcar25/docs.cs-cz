---
title: Metoda ICorDebugAppDomain4::GetObjectForCCW
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: abce5563e8cd7eb0c599e835d0217157cf073485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="54c07-102">Metoda ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="54c07-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="54c07-103">Získá objekt spravovaného z COM ukazatel obálka volatelná aplikacemi (doleva).</span><span class="sxs-lookup"><span data-stu-id="54c07-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54c07-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="54c07-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54c07-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="54c07-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="54c07-106">[v] Obálka volatelná aplikacemi (doleva) ukazatel COM.</span><span class="sxs-lookup"><span data-stu-id="54c07-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="54c07-107">[out] Ukazatel na adresu "ICorDebugValue" objekt, který představuje spravovaný objekt, který odpovídá dané ukazatele doleva.</span><span class="sxs-lookup"><span data-stu-id="54c07-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54c07-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="54c07-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54c07-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="54c07-109">Requirements</span></span>  
 <span data-ttu-id="54c07-110">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54c07-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54c07-111">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54c07-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54c07-112">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54c07-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54c07-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54c07-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c07-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="54c07-114">See Also</span></span>  
 [<span data-ttu-id="54c07-115">Rozhraní ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="54c07-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [<span data-ttu-id="54c07-116">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="54c07-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)