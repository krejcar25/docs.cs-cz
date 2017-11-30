---
title: "IMetaDataEmit::DefineEvent – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf790ce270565abaf1d91e54c9e3569a50ab3435
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="2695b-102">IMetaDataEmit::DefineEvent – metoda</span><span class="sxs-lookup"><span data-stu-id="2695b-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="2695b-103">Vytvoří definici pro události s podpisem Zadaná metadata a získá token tuto definici událostí.</span><span class="sxs-lookup"><span data-stu-id="2695b-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2695b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2695b-104">Syntax</span></span>  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2695b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2695b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="2695b-106">[v] Token pro danou cílovou třídu nebo rozhraní.</span><span class="sxs-lookup"><span data-stu-id="2695b-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="2695b-107">To znamená buď `mdTypeDef` nebo `mdTypeDefNil` tokenu.</span><span class="sxs-lookup"><span data-stu-id="2695b-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="2695b-108">[v] Název události.</span><span class="sxs-lookup"><span data-stu-id="2695b-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="2695b-109">[v] Příznaky událostí.</span><span class="sxs-lookup"><span data-stu-id="2695b-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="2695b-110">[v] Token pro třídy události.</span><span class="sxs-lookup"><span data-stu-id="2695b-110">[in] The token for the event class.</span></span> <span data-ttu-id="2695b-111">Toto je `mdTypeDef`, `mdTypeRef`, nebo `mdTokenNil` tokenu.</span><span class="sxs-lookup"><span data-stu-id="2695b-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="2695b-112">[v] Metoda použitá k odběru události, nebo hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="2695b-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="2695b-113">[v] Metoda použitá k odhlášení odběru událostí, nebo hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="2695b-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="2695b-114">[v] Metoda použitá k vyvolání události (podle odvozené třídy).</span><span class="sxs-lookup"><span data-stu-id="2695b-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="2695b-115">[v] Pole tokeny pro jiné metody přidružený k události.</span><span class="sxs-lookup"><span data-stu-id="2695b-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="2695b-116">Toto pole je byla ukončena s `mdMethodDefNil` tokenu.</span><span class="sxs-lookup"><span data-stu-id="2695b-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="2695b-117">[out] Metadata token přiřazené k události.</span><span class="sxs-lookup"><span data-stu-id="2695b-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2695b-118">Požadavky</span><span class="sxs-lookup"><span data-stu-id="2695b-118">Requirements</span></span>  
 <span data-ttu-id="2695b-119">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2695b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2695b-120">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2695b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2695b-121">**Knihovna:** používat jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2695b-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2695b-122">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2695b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2695b-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="2695b-123">See Also</span></span>  
 [<span data-ttu-id="2695b-124">Imetadataemit – rozhraní</span><span class="sxs-lookup"><span data-stu-id="2695b-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="2695b-125">Imetadataemit2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="2695b-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)