---
title: "IAssemblyName::GetName – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 612efc9d5334fd34cc61f2243914de59370c45a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="8f46b-102">IAssemblyName::GetName – metoda</span><span class="sxs-lookup"><span data-stu-id="8f46b-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="8f46b-103">Získá název sestavení odkazuje toto jednoduché, nezašifrované [iassemblyname –](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) objektu.</span><span class="sxs-lookup"><span data-stu-id="8f46b-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f46b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8f46b-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f46b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8f46b-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="8f46b-106">[ve out] Velikost `pwzName` v široké znaky, včetně null ukončovací znak.</span><span class="sxs-lookup"><span data-stu-id="8f46b-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="8f46b-107">[out] Vyrovnávací paměť pro název odkazované sestavení.</span><span class="sxs-lookup"><span data-stu-id="8f46b-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f46b-108">Požadavky</span><span class="sxs-lookup"><span data-stu-id="8f46b-108">Requirements</span></span>  
 <span data-ttu-id="8f46b-109">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f46b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f46b-110">**Záhlaví:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8f46b-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8f46b-111">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f46b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f46b-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="8f46b-112">See Also</span></span>  
 [<span data-ttu-id="8f46b-113">Iassemblyname – rozhraní</span><span class="sxs-lookup"><span data-stu-id="8f46b-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)