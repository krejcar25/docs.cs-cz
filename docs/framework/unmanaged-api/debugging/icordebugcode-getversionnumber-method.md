---
title: "ICorDebugCode::GetVersionNumber – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd467f047131bbb078c72db9daca2cbc5a87a7be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="b6be0-102">ICorDebugCode::GetVersionNumber – metoda</span><span class="sxs-lookup"><span data-stu-id="b6be0-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="b6be0-103">Získá počet základem jedna, která identifikuje verzi kód, který představuje tuto "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="b6be0-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6be0-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b6be0-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6be0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b6be0-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="b6be0-106">[out] Ukazatel na číslo verze kódu.</span><span class="sxs-lookup"><span data-stu-id="b6be0-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6be0-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b6be0-107">Remarks</span></span>  
 <span data-ttu-id="b6be0-108">Číslo verze se zvýší pokaždé, když probíhá operace upravit a pokračovat (Šif) kódu.</span><span class="sxs-lookup"><span data-stu-id="b6be0-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6be0-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b6be0-109">Requirements</span></span>  
 <span data-ttu-id="b6be0-110">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6be0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6be0-111">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6be0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6be0-112">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6be0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6be0-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6be0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6be0-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="b6be0-114">See Also</span></span>  
 