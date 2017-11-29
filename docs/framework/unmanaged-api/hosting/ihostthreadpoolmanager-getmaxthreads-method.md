---
title: "IHostThreadPoolManager::GetMaxThreads – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd15b1448c23785437b3dc62562b5d96abb3601c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="f322c-102">IHostThreadPoolManager::GetMaxThreads – metoda</span><span class="sxs-lookup"><span data-stu-id="f322c-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="f322c-103">Získá maximální počet vláken, která udržuje hostitele současně ve fondu vláken.</span><span class="sxs-lookup"><span data-stu-id="f322c-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f322c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f322c-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f322c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f322c-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="f322c-106">[out] Ukazatel na maximální počet vláken, která udržuje hostitele ve fondu vláken.</span><span class="sxs-lookup"><span data-stu-id="f322c-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f322c-107">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="f322c-107">Return Value</span></span>  
  
|<span data-ttu-id="f322c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f322c-108">HRESULT</span></span>|<span data-ttu-id="f322c-109">Popis</span><span class="sxs-lookup"><span data-stu-id="f322c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f322c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f322c-110">S_OK</span></span>|<span data-ttu-id="f322c-111">`GetMaxThreads`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="f322c-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="f322c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f322c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f322c-113">Modul common language runtime (CLR (nebyla načtena do procesu, nebo CLR je ve stavu, ve kterém it nelze spravovaného kódu nebo proces volání úspěšně spustit.</span><span class="sxs-lookup"><span data-stu-id="f322c-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f322c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f322c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f322c-115">Vypršel časový limit volání.</span><span class="sxs-lookup"><span data-stu-id="f322c-115">The call timed out.</span></span>|  
|<span data-ttu-id="f322c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f322c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f322c-117">Volající není vlastníkem zámek.</span><span class="sxs-lookup"><span data-stu-id="f322c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f322c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f322c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f322c-119">Událost byla zrušena při blokované vlákna nebo fiber čekal na něm.</span><span class="sxs-lookup"><span data-stu-id="f322c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f322c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f322c-120">E_FAIL</span></span>|<span data-ttu-id="f322c-121">Došlo k neznámému závažné selhání.</span><span class="sxs-lookup"><span data-stu-id="f322c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f322c-122">Po návratu metody E_FAIL modulu CLR již není použitelné v rámci procesu.</span><span class="sxs-lookup"><span data-stu-id="f322c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f322c-123">Následující volání hostování metody vrací HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f322c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f322c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f322c-124">E_NOTIMPL</span></span>|<span data-ttu-id="f322c-125">Hostitel neposkytuje implementace `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="f322c-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f322c-126">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f322c-126">Remarks</span></span>  
 <span data-ttu-id="f322c-127">Volání CLR `GetMaxThreads` můžete určit celkový počet vláken ve fondu vláken.</span><span class="sxs-lookup"><span data-stu-id="f322c-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="f322c-128">[Getavailablethreads –](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) metoda získá počet vláken, která nejsou aktuálně zpracování pracovní položky.</span><span class="sxs-lookup"><span data-stu-id="f322c-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="f322c-129">Všechny požadavky výše vrácená hodnota `pdwMaxWorkerThreads` parametr zůstanou ve frontě, dokud vláken k dispozici.</span><span class="sxs-lookup"><span data-stu-id="f322c-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="f322c-130">Pokud hostitel neposkytne implementace `GetMaxThreads`, má hodnotu HRESULT E_NOTIMPL má být vrácen.</span><span class="sxs-lookup"><span data-stu-id="f322c-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f322c-131">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f322c-131">Requirements</span></span>  
 <span data-ttu-id="f322c-132">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f322c-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f322c-133">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f322c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f322c-134">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f322c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f322c-135">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f322c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f322c-136">Viz také</span><span class="sxs-lookup"><span data-stu-id="f322c-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="f322c-137">Getminthreads – metoda</span><span class="sxs-lookup"><span data-stu-id="f322c-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="f322c-138">SetMaxThreads – metoda</span><span class="sxs-lookup"><span data-stu-id="f322c-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="f322c-139">Ihostthreadpoolmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="f322c-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)