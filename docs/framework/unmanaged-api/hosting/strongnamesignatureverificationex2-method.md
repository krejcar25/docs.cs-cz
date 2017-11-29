---
title: "StrongNameSignatureVerificationEx2 – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 823eac67a53c4534a12122b118ac46bb91530d1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="d7ef7-102">StrongNameSignatureVerificationEx2 – metoda</span><span class="sxs-lookup"><span data-stu-id="d7ef7-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="d7ef7-103">Ověří podpis silně pojmenované sestavení a poskytuje mapování z klíče ECMA skutečné klíče.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7ef7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d7ef7-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7ef7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d7ef7-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d7ef7-106">[v] Cesta k přenosné spustitelný soubor (.exe nebo .dll) souboru pro sestavení, které má být ověřen.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="d7ef7-107">[v] `true` provést ověření, i když je nezbytné pro přepsání nastavení registru; v opačném `false`.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="d7ef7-108">[v] Ukazatel na mapování z ECMA veřejný klíč do skutečné klíče používané pro ověřování.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="d7ef7-109">[v] Délka skutečné ECMA veřejný klíč.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="d7ef7-110">[out] `true` Pokud podpis silného názvu byl ověřený, jinak hodnota `false`.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="d7ef7-111">Tento parametr je také nastavena na `false` Pokud ověření bylo úspěšné z důvodu nastavení registru.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7ef7-112">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="d7ef7-112">Return Value</span></span>  
 <span data-ttu-id="d7ef7-113">`S_OK`Pokud ověření byla úspěšná. jinak hodnota hodnotou HRESULT označující selhání (viz [běžné hodnoty HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) seznam).</span><span class="sxs-lookup"><span data-stu-id="d7ef7-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7ef7-114">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d7ef7-114">Requirements</span></span>  
 <span data-ttu-id="d7ef7-115">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7ef7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7ef7-116">**Záhlaví:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d7ef7-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d7ef7-117">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7ef7-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7ef7-118">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7ef7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ef7-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="d7ef7-119">See Also</span></span>  
 [<span data-ttu-id="d7ef7-120">Strongnamesignatureverification – metoda</span><span class="sxs-lookup"><span data-stu-id="d7ef7-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="d7ef7-121">Strongnamesignatureverificationex – metoda</span><span class="sxs-lookup"><span data-stu-id="d7ef7-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="d7ef7-122">Iclrstrongname – rozhraní</span><span class="sxs-lookup"><span data-stu-id="d7ef7-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)