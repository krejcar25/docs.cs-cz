---
title: "ICorDebugReferenceValue::Dereference – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.Dereference
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4eb3287612a8301d551a1443d803e60e4d03f7db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="713ee-102">ICorDebugReferenceValue::Dereference – metoda</span><span class="sxs-lookup"><span data-stu-id="713ee-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="713ee-103">Získá objekt, který se odkazuje.</span><span class="sxs-lookup"><span data-stu-id="713ee-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="713ee-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="713ee-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="713ee-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="713ee-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="713ee-106">[out] Ukazatel na adresu ICorDebugValue, který představuje objekt, na kterou odkazuje tento objekt ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="713ee-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="713ee-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="713ee-107">Remarks</span></span>  
 <span data-ttu-id="713ee-108">`ICorDebugValue` Objektu je platná pouze tehdy, když jeho referenční nebyla dosud zakázána.</span><span class="sxs-lookup"><span data-stu-id="713ee-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="713ee-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="713ee-109">Requirements</span></span>  
 <span data-ttu-id="713ee-110">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="713ee-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="713ee-111">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="713ee-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="713ee-112">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="713ee-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="713ee-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="713ee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>