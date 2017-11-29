---
title: "ICorDebugFunction2::SetJMCStatus – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ecbcd5b8171a169fbfdd7175d3d9dfbbcb3855f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="b224d-102">ICorDebugFunction2::SetJMCStatus – metoda</span><span class="sxs-lookup"><span data-stu-id="b224d-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="b224d-103">Označí funkce reprezentována tento ICorDebugFunction2 pro pouze můj kód krokování s.</span><span class="sxs-lookup"><span data-stu-id="b224d-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b224d-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b224d-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b224d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b224d-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="b224d-106">[v] Nastavte na `true` označit funkce jako uživatelský kód; jinak hodnota nastavena na `false`.</span><span class="sxs-lookup"><span data-stu-id="b224d-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="b224d-107">Návratové hodnoty</span><span class="sxs-lookup"><span data-stu-id="b224d-107">Return Values</span></span>  
  
|<span data-ttu-id="b224d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b224d-108">HRESULT</span></span>|<span data-ttu-id="b224d-109">Popis</span><span class="sxs-lookup"><span data-stu-id="b224d-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b224d-110">Funkci byl úspěšně označen.</span><span class="sxs-lookup"><span data-stu-id="b224d-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="b224d-111">Funkci nelze označit jako uživatelského kódu, protože nelze ladit.</span><span class="sxs-lookup"><span data-stu-id="b224d-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b224d-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b224d-112">Remarks</span></span>  
 <span data-ttu-id="b224d-113">Pouze můj kód krokovač přeskočí bez uživatelského kódu.</span><span class="sxs-lookup"><span data-stu-id="b224d-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="b224d-114">Uživatelský kód musí být podmnožinou debuggable kódu.</span><span class="sxs-lookup"><span data-stu-id="b224d-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b224d-115">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b224d-115">Requirements</span></span>  
 <span data-ttu-id="b224d-116">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b224d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b224d-117">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b224d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b224d-118">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b224d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b224d-119">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b224d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>