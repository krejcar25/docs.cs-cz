---
title: ICorDebugBoxValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBoxValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBoxValue
helpviewer_keywords: ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7dfc50ab7caef79010e4e68380654c918514379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugboxvalue-interface1"></a><span data-ttu-id="ddd89-102">ICorDebugBoxValue Interface1</span><span class="sxs-lookup"><span data-stu-id="ddd89-102">ICorDebugBoxValue Interface1</span></span>
<span data-ttu-id="ddd89-103">Podtřídou třídy "Icordebugheapvalue –" představující objekt třídy zabalené hodnoty.</span><span class="sxs-lookup"><span data-stu-id="ddd89-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ddd89-104">Metody</span><span class="sxs-lookup"><span data-stu-id="ddd89-104">Methods</span></span>  
  
|<span data-ttu-id="ddd89-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="ddd89-105">Method</span></span>|<span data-ttu-id="ddd89-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ddd89-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ddd89-107">GetObject – metoda</span><span class="sxs-lookup"><span data-stu-id="ddd89-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="ddd89-108">Získá ukazatele rozhraní k zabalené "ICorDebugObjectValue" instanci.</span><span class="sxs-lookup"><span data-stu-id="ddd89-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddd89-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ddd89-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddd89-110">Toto rozhraní nepodporuje volané vzdáleně, mezi počítači nebo mezi procesy.</span><span class="sxs-lookup"><span data-stu-id="ddd89-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddd89-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ddd89-111">Requirements</span></span>  
 <span data-ttu-id="ddd89-112">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddd89-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddd89-113">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddd89-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddd89-114">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddd89-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddd89-115">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddd89-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd89-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="ddd89-116">See Also</span></span>  
 [<span data-ttu-id="ddd89-117">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="ddd89-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)