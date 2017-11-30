---
title: "ICorDebugSymbolProvider::GetTypeProps – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ba736caf8d8d823a4cb56c75aa2202ad616983fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="cbc09-102">ICorDebugSymbolProvider::GetTypeProps – metoda</span><span class="sxs-lookup"><span data-stu-id="cbc09-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>
<span data-ttu-id="cbc09-103">Zadaný relativní virtuální adresy (RVA) v tabulce vtable vrací informace o vlastnosti typ, například počet podpis jeho obecné parametry.</span><span class="sxs-lookup"><span data-stu-id="cbc09-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc09-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cbc09-104">Syntax</span></span>  
  
```  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbc09-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cbc09-105">Parameters</span></span>  
 `tableRva`  
 <span data-ttu-id="cbc09-106">[v] Vytvoření relativní virtuální adresy (RVA) vtable.</span><span class="sxs-lookup"><span data-stu-id="cbc09-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="cbc09-107">[v] Velikost `signature` pole.</span><span class="sxs-lookup"><span data-stu-id="cbc09-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="cbc09-108">Najdete v části poznámky.</span><span class="sxs-lookup"><span data-stu-id="cbc09-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="cbc09-109">[out] [out] Ukazatel na velikost vrácený `signature` pole.</span><span class="sxs-lookup"><span data-stu-id="cbc09-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="cbc09-110">[out] Vyrovnávací paměť, která obsahuje typ typespec signatur všechny obecné parametry.</span><span class="sxs-lookup"><span data-stu-id="cbc09-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbc09-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cbc09-111">Remarks</span></span>  
 <span data-ttu-id="cbc09-112">Získat požadovaná velikost typu `signature` pole, nastavte `cbSignature` argument na hodnotu 0 a `signature` k **null**.</span><span class="sxs-lookup"><span data-stu-id="cbc09-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="cbc09-113">Po návratu metody `pcbSignature` bude obsahovat počet bajtů požadovaných pro `signature` pole.</span><span class="sxs-lookup"><span data-stu-id="cbc09-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbc09-114">Tato metoda je k dispozici s .NET Native jenom.</span><span class="sxs-lookup"><span data-stu-id="cbc09-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbc09-115">Požadavky</span><span class="sxs-lookup"><span data-stu-id="cbc09-115">Requirements</span></span>  
 <span data-ttu-id="cbc09-116">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbc09-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbc09-117">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbc09-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbc09-118">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbc09-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbc09-119">**Verze rozhraní .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbc09-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc09-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="cbc09-120">See Also</span></span>  
 [<span data-ttu-id="cbc09-121">Getmethodprops – metoda</span><span class="sxs-lookup"><span data-stu-id="cbc09-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)  
 [<span data-ttu-id="cbc09-122">ICorDebugSymbolProvider rozhraní</span><span class="sxs-lookup"><span data-stu-id="cbc09-122">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="cbc09-123">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="cbc09-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)