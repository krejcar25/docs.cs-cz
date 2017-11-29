---
title: "IMetaDataAssemblyEmit::DefineAssembly – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 86002eb38d72ee628dbf54d0b5691f0816e6f996
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="9b2c7-102">IMetaDataAssemblyEmit::DefineAssembly – metoda</span><span class="sxs-lookup"><span data-stu-id="9b2c7-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="9b2c7-103">Vytvoří `Assembly` struktury obsahující metadata pro zadaného sestavení a vrátí token přidružených metadat.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b2c7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9b2c7-104">Syntax</span></span>  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b2c7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9b2c7-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="9b2c7-106">[v] Veřejný klíč, který identifikuje vydavatele sestavení, nebo hodnota NULL, pokud sestavení nemá silný název.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="9b2c7-107">[v] Velikost v bajtech `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="9b2c7-108">[v] Identifikátor algoritmu hash, který chcete použít k šifrování souborů v sestavení nebo NULL. Chcete-li určit algoritmus SHA-1.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="9b2c7-109">[v] Čitelný text název sestavení.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="9b2c7-110">Tato hodnota nesmí být delší než 1024 znaků.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="9b2c7-111">[v] Ukazatel na instanci assemblymetadata –, který obsahuje informace o verzi, platformy a národní prostředí pro sestavení.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="9b2c7-112">[v] Kombinace [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) hodnoty, které popisují funkce sestavení.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="9b2c7-113">[out] Ukazatel na token metadat.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b2c7-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="9b2c7-114">Remarks</span></span>  
 <span data-ttu-id="9b2c7-115">Pouze jeden `Assembly` v manifestu je možné definovat strukturu metadat.</span><span class="sxs-lookup"><span data-stu-id="9b2c7-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b2c7-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="9b2c7-116">Requirements</span></span>  
 <span data-ttu-id="9b2c7-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b2c7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b2c7-118">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b2c7-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b2c7-119">**Knihovna:** zahrnuty jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b2c7-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b2c7-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b2c7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2c7-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="9b2c7-121">See Also</span></span>  
 [<span data-ttu-id="9b2c7-122">Imetadataassemblyemit – rozhraní</span><span class="sxs-lookup"><span data-stu-id="9b2c7-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)