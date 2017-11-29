---
title: "IMetaDataImport::EnumPermissionSets – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumPermissionSets
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 031e97ad1b8180a64bc789ae52e141932d600782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="b25d2-102">IMetaDataImport::EnumPermissionSets – metoda</span><span class="sxs-lookup"><span data-stu-id="b25d2-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="b25d2-103">Vytvoří výčet oprávnění pro objekty v oboru Zadaná metadata.</span><span class="sxs-lookup"><span data-stu-id="b25d2-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b25d2-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b25d2-104">Syntax</span></span>  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b25d2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b25d2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b25d2-106">[ve out] Ukazatel na enumerátor.</span><span class="sxs-lookup"><span data-stu-id="b25d2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b25d2-107">Toto musí mít hodnotu NULL pro první volání této metody.</span><span class="sxs-lookup"><span data-stu-id="b25d2-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="b25d2-108">[v] Metadata token, který omezuje obor vyhledávání, nebo hodnota NULL pro vyhledávání možné nejširší rozsahu vyhledávání.</span><span class="sxs-lookup"><span data-stu-id="b25d2-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="b25d2-109">[v] Flags – představující <xref:System.Security.Permissions.SecurityAction> hodnoty, které chcete zahrnout do `rPermission`, nebo nula, která vrátí všechny akce.</span><span class="sxs-lookup"><span data-stu-id="b25d2-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="b25d2-110">[out] Pole používá k ukládání tokenů oprávnění.</span><span class="sxs-lookup"><span data-stu-id="b25d2-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b25d2-111">[v] Maximální velikost `rPermission` pole.</span><span class="sxs-lookup"><span data-stu-id="b25d2-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b25d2-112">[out] Číslo, vrátí se v tokenů oprávnění `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="b25d2-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b25d2-113">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="b25d2-113">Return Value</span></span>  
  
|<span data-ttu-id="b25d2-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b25d2-114">HRESULT</span></span>|<span data-ttu-id="b25d2-115">Popis</span><span class="sxs-lookup"><span data-stu-id="b25d2-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b25d2-116">`EnumPermissionSets`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="b25d2-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b25d2-117">Neexistují žádné tokenů pro zobrazení výčtu.</span><span class="sxs-lookup"><span data-stu-id="b25d2-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="b25d2-118">V takovém případě `pcTokens` je nulová.</span><span class="sxs-lookup"><span data-stu-id="b25d2-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b25d2-119">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b25d2-119">Requirements</span></span>  
 <span data-ttu-id="b25d2-120">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b25d2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b25d2-121">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b25d2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b25d2-122">**Knihovna:** zahrnuty jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b25d2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b25d2-123">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b25d2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b25d2-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="b25d2-124">See Also</span></span>  
 [<span data-ttu-id="b25d2-125">Imetadataimport – rozhraní</span><span class="sxs-lookup"><span data-stu-id="b25d2-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b25d2-126">Imetadataimport2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="b25d2-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)