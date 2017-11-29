---
title: "ICLRTask2::BeginPreventAsyncAbort – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2.BeginPreventAsyncAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33136dfbfa8bb3e0147bc1a1c1bb9e88ab2e4239
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="f2960-102">ICLRTask2::BeginPreventAsyncAbort – metoda</span><span class="sxs-lookup"><span data-stu-id="f2960-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="f2960-103">Zpoždění nové vlákno přerušení požadavky od vést k přerušení přístup z více vláken na aktuální vlákno.</span><span class="sxs-lookup"><span data-stu-id="f2960-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2960-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f2960-104">Syntax</span></span>  
  
```  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f2960-105">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="f2960-105">Return Value</span></span>  
 <span data-ttu-id="f2960-106">Tato metoda vrátí následující konkrétní hodnoty HRESULT a také HRESULT chyby, které označují selhání metoda.</span><span class="sxs-lookup"><span data-stu-id="f2960-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f2960-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2960-107">HRESULT</span></span>|<span data-ttu-id="f2960-108">Popis</span><span class="sxs-lookup"><span data-stu-id="f2960-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2960-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2960-109">S_OK</span></span>|<span data-ttu-id="f2960-110">Metoda byla úspěšně dokončena.</span><span class="sxs-lookup"><span data-stu-id="f2960-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="f2960-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="f2960-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="f2960-112">Volání metody na vlákno, která není aktuální vlákno.</span><span class="sxs-lookup"><span data-stu-id="f2960-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2960-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f2960-113">Remarks</span></span>  
 <span data-ttu-id="f2960-114">Voláním této metody zvýší čítač přerušení podprocesu zpoždění pro aktuální vlákno o jednu.</span><span class="sxs-lookup"><span data-stu-id="f2960-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="f2960-115">Volání `BeginPreventAsyncAbort` a [iclrtask2::endpreventasyncabort –](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) mohou být použity.</span><span class="sxs-lookup"><span data-stu-id="f2960-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="f2960-116">Tak dlouho, dokud hodnota čítače je větší než nula, jsou odložené přerušení přístup z více vláken pro aktuální vlákno.</span><span class="sxs-lookup"><span data-stu-id="f2960-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="f2960-117">Pokud toto volání není spárovaný s volání `EndPreventAsyncAbort` metoda, je možné dosáhnout stavu, ve které vlákno přerušení nelze doručit do aktuální vlákno.</span><span class="sxs-lookup"><span data-stu-id="f2960-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="f2960-118">Zpoždění není dodržení pro vlákno, které zruší sám sebe.</span><span class="sxs-lookup"><span data-stu-id="f2960-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="f2960-119">Funkce, který je zveřejněný prostřednictvím této funkce se používá interně pro virtuální počítač (VM).</span><span class="sxs-lookup"><span data-stu-id="f2960-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="f2960-120">Zneužití z těchto metod může způsobit neurčené chování ve virtuálním počítači.</span><span class="sxs-lookup"><span data-stu-id="f2960-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="f2960-121">Například volání `EndPreventAsyncAbort` bez první volání `BeginPreventAsyncAbort` čítač může nastavit na hodnotu nula, pokud virtuální počítač má dříve se zvýší.</span><span class="sxs-lookup"><span data-stu-id="f2960-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="f2960-122">Podobně není čítač interní kontrola přetečení.</span><span class="sxs-lookup"><span data-stu-id="f2960-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="f2960-123">Pokud překročí limitu integrální vzhledem k tomu, že se zvýší o hostitel a virtuální počítač, neurčené jejich výsledné chování.</span><span class="sxs-lookup"><span data-stu-id="f2960-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2960-124">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f2960-124">Requirements</span></span>  
 <span data-ttu-id="f2960-125">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2960-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2960-126">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2960-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2960-127">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2960-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2960-128">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2960-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2960-129">Viz také</span><span class="sxs-lookup"><span data-stu-id="f2960-129">See Also</span></span>  
 [<span data-ttu-id="f2960-130">Endpreventasyncabort – metoda</span><span class="sxs-lookup"><span data-stu-id="f2960-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)  
 [<span data-ttu-id="f2960-131">Iclrtask2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="f2960-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="f2960-132">Iclrtaskmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="f2960-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f2960-133">Ihosttask – rozhraní</span><span class="sxs-lookup"><span data-stu-id="f2960-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f2960-134">Ihosttaskmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="f2960-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="f2960-135">Rozhraní hostování</span><span class="sxs-lookup"><span data-stu-id="f2960-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)