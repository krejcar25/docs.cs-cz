---
title: "ClrCreateManagedInstance – funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: ClrCreateManagedInstance
helpviewer_keywords: ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2d27a881f84121f0d096eae7c693dec5b674caec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="1604b-102">ClrCreateManagedInstance – funkce</span><span class="sxs-lookup"><span data-stu-id="1604b-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="1604b-103">Vytvoří instanci je určeného spravovaného typu.</span><span class="sxs-lookup"><span data-stu-id="1604b-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="1604b-104">Tato funkce se již nepoužívá v [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1604b-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="1604b-105">Použijte aktivace COM vytvořit instanci spravovaného typu, nebo použijte hostování (viz [CLR hostování rozhraní přidaná v rozhraní .NET Framework 4 a 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="1604b-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1604b-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1604b-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1604b-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="1604b-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="1604b-108">[v] Ukazatel na název požadovaného typu instance.</span><span class="sxs-lookup"><span data-stu-id="1604b-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="1604b-109">[v] `IID` Instance typu požadováno.</span><span class="sxs-lookup"><span data-stu-id="1604b-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="1604b-110">[out] Ukazatel na ukazatel na instanci spravovaného typu, který byl vyžádán volajícího.</span><span class="sxs-lookup"><span data-stu-id="1604b-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1604b-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1604b-111">Remarks</span></span>  
 <span data-ttu-id="1604b-112">Modul common language runtime by měl být již načtena do procesu.</span><span class="sxs-lookup"><span data-stu-id="1604b-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="1604b-113">Například můžete načíst pomocí volání [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funkce před `ClrCreateManagedInstance` funkce je volána.</span><span class="sxs-lookup"><span data-stu-id="1604b-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="1604b-114">Pokud není načteno modul runtime, `ClrCreateManagedInstance` poprvé pokusí načíst v1.0.3705 modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="1604b-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="1604b-115">Pokud to nepomůže, pokusí se načíst nejnovější verzi modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="1604b-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1604b-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="1604b-116">Requirements</span></span>  
 <span data-ttu-id="1604b-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1604b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1604b-118">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1604b-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1604b-119">**Knihovna:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1604b-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1604b-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1604b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1604b-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="1604b-121">See Also</span></span>  
 [<span data-ttu-id="1604b-122">Zastaralé funkce hostování CLR</span><span class="sxs-lookup"><span data-stu-id="1604b-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="1604b-123">Hostování</span><span class="sxs-lookup"><span data-stu-id="1604b-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)