---
title: "IManagedObject::GetObjectIdentity – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IManagedObject.GetObjectIdentity
api_location: mscoree.dll
api_type: COM
f1_keywords: GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c0dabfca147b203c3bcf93a362e6670ae295338
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="c637b-102">IManagedObject::GetObjectIdentity – metoda</span><span class="sxs-lookup"><span data-stu-id="c637b-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="c637b-103">Získá identitu tomto spravovaném objektu.</span><span class="sxs-lookup"><span data-stu-id="c637b-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c637b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c637b-104">Syntax</span></span>  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c637b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c637b-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="c637b-106">[out] Ukazatel na identifikátor GUID procesu, ve kterém se objekt nachází.</span><span class="sxs-lookup"><span data-stu-id="c637b-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="c637b-107">[out] Ukazatel na ID objektu domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="c637b-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="c637b-108">[out] Ukazatel na index objektu v modelu COM classic tabulky v.</span><span class="sxs-lookup"><span data-stu-id="c637b-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c637b-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c637b-109">Remarks</span></span>  
 <span data-ttu-id="c637b-110">Identitu spravovaného objektu zahrnuje proces identifikátor GUID, ID domény aplikace a objektu indexu v modelu COM classic tabulky v.</span><span class="sxs-lookup"><span data-stu-id="c637b-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c637b-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="c637b-111">Requirements</span></span>  
 <span data-ttu-id="c637b-112">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c637b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c637b-113">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c637b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c637b-114">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c637b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c637b-115">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c637b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c637b-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="c637b-116">See Also</span></span>  
 [<span data-ttu-id="c637b-117">IManagedObject – rozhraní</span><span class="sxs-lookup"><span data-stu-id="c637b-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)