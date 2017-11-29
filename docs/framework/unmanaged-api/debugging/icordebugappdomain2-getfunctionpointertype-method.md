---
title: "ICorDebugAppDomain2::GetFunctionPointerType – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2.GetFunctionPointerType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 85c07ec6177621b571a376ad58a386e8ed31ea63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="1a5b2-102">ICorDebugAppDomain2::GetFunctionPointerType – metoda</span><span class="sxs-lookup"><span data-stu-id="1a5b2-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="1a5b2-103">Získá ukazatel na funkci, která má daný podpis.</span><span class="sxs-lookup"><span data-stu-id="1a5b2-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a5b2-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1a5b2-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a5b2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1a5b2-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="1a5b2-106">[v] Počet argumentů pro funkci.</span><span class="sxs-lookup"><span data-stu-id="1a5b2-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="1a5b2-107">[v] Pole ukazatele, každý z nich odkazuje na objekt ICorDebugType, který představuje argument typu funkce.</span><span class="sxs-lookup"><span data-stu-id="1a5b2-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="1a5b2-108">První prvek je návratový typ; Každá z dalších prvků je typ parametru.</span><span class="sxs-lookup"><span data-stu-id="1a5b2-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="1a5b2-109">[out] Ukazatel na adresu `ICorDebugType` objekt, který reprezentuje ukazatele na funkce.</span><span class="sxs-lookup"><span data-stu-id="1a5b2-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a5b2-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="1a5b2-110">Requirements</span></span>  
 <span data-ttu-id="1a5b2-111">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a5b2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a5b2-112">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a5b2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a5b2-113">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a5b2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a5b2-114">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a5b2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>