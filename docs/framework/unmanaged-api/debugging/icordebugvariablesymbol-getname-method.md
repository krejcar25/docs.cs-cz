---
title: "ICorDebugVariableSymbol::GetName – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aff18efb6781aee5b6a148fcd59863a2ce657023
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="3e52f-102">ICorDebugVariableSymbol::GetName – metoda</span><span class="sxs-lookup"><span data-stu-id="3e52f-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="3e52f-103">Získá název proměnné.</span><span class="sxs-lookup"><span data-stu-id="3e52f-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e52f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3e52f-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e52f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3e52f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3e52f-106">[v] Počet znaků `szName` vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="3e52f-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3e52f-107">[out] Ukazatel na počet znaků, které jsou ve skutečnosti zapsána do `szName` vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="3e52f-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="3e52f-108">Ukazatel na pole znaků, který obsahuje název proměnné.</span><span class="sxs-lookup"><span data-stu-id="3e52f-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e52f-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3e52f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e52f-110">Tato metoda je k dispozici s .NET Native jenom.</span><span class="sxs-lookup"><span data-stu-id="3e52f-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e52f-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="3e52f-111">Requirements</span></span>  
 <span data-ttu-id="3e52f-112">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e52f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e52f-113">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e52f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e52f-114">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e52f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e52f-115">**Verze rozhraní .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e52f-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e52f-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="3e52f-116">See Also</span></span>  
 [<span data-ttu-id="3e52f-117">ICorDebugVariableSymbol rozhraní</span><span class="sxs-lookup"><span data-stu-id="3e52f-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="3e52f-118">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="3e52f-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)