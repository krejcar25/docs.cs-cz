---
title: "ICorDebugProcess6::GetCode – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c69ce290a486960978ddaf87203328df4f392b48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="803f4-102">ICorDebugProcess6::GetCode – metoda</span><span class="sxs-lookup"><span data-stu-id="803f4-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="803f4-103">Získá informace o spravovaného kódu na adrese konkrétního kódu.</span><span class="sxs-lookup"><span data-stu-id="803f4-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="803f4-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="803f4-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="803f4-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="803f4-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="803f4-106">[v] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) hodnotu, která určuje počáteční adresa segmentu spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="803f4-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="803f4-107">[out] Ukazatel na adresu "ICorDebugCode" objekt, který představuje segment spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="803f4-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="803f4-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="803f4-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="803f4-109">Tato metoda je k dispozici s .NET Native jenom.</span><span class="sxs-lookup"><span data-stu-id="803f4-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="803f4-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="803f4-110">Requirements</span></span>  
 <span data-ttu-id="803f4-111">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="803f4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="803f4-112">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="803f4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="803f4-113">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="803f4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="803f4-114">**Verze rozhraní .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="803f4-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="803f4-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="803f4-115">See Also</span></span>  
 [<span data-ttu-id="803f4-116">Rozhraní ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="803f4-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="803f4-117">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="803f4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)