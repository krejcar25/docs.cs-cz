---
title: "IMetaDataFilter – rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter
helpviewer_keywords: IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7c0afbb9be9af3ffe69ddfcac85b70de53a391ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="3557b-102">IMetaDataFilter – rozhraní</span><span class="sxs-lookup"><span data-stu-id="3557b-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="3557b-103">Poskytuje metody pro označování a filtrování tokenů metadat, aby se zabránilo opakující se akce, které již byla přijata.</span><span class="sxs-lookup"><span data-stu-id="3557b-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3557b-104">Metody</span><span class="sxs-lookup"><span data-stu-id="3557b-104">Methods</span></span>  
  
|<span data-ttu-id="3557b-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="3557b-105">Method</span></span>|<span data-ttu-id="3557b-106">Popis</span><span class="sxs-lookup"><span data-stu-id="3557b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3557b-107">Istokenmarked – metoda</span><span class="sxs-lookup"><span data-stu-id="3557b-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="3557b-108">Získá hodnotu označující, zda je zadaná metadata token byla zpracována.</span><span class="sxs-lookup"><span data-stu-id="3557b-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="3557b-109">Marktoken – metoda</span><span class="sxs-lookup"><span data-stu-id="3557b-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="3557b-110">Nastaví hodnotu, která určuje, že token Zadaná metadata byla zpracována.</span><span class="sxs-lookup"><span data-stu-id="3557b-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="3557b-111">Unmarkall – metoda</span><span class="sxs-lookup"><span data-stu-id="3557b-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="3557b-112">Odebere všechny tokeny, které jsou v aktuálním oboru metadata značky ve zpracování.</span><span class="sxs-lookup"><span data-stu-id="3557b-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3557b-113">Požadavky</span><span class="sxs-lookup"><span data-stu-id="3557b-113">Requirements</span></span>  
 <span data-ttu-id="3557b-114">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3557b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3557b-115">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3557b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3557b-116">**Knihovna:** používat jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3557b-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3557b-117">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3557b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3557b-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="3557b-118">See Also</span></span>  
 [<span data-ttu-id="3557b-119">Rozhraní metadat</span><span class="sxs-lookup"><span data-stu-id="3557b-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)