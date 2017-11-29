---
title: "StrongNameSignatureGenerationEx – funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureGenerationEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureGenerationEx
helpviewer_keywords: StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49000a00f278b4c1dd7a2eeded7eb91a592c863f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="4cd9f-102">StrongNameSignatureGenerationEx – funkce</span><span class="sxs-lookup"><span data-stu-id="4cd9f-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="4cd9f-103">Generuje pro zadané sestavení, podle zadaného příznaky podpis silného názvu.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="4cd9f-104">Tato funkce je zastaralá.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-104">This function has been deprecated.</span></span> <span data-ttu-id="4cd9f-105">Použití [iclrstrongname::strongnamesignaturegenerationex –](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) metoda místo.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd9f-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4cd9f-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cd9f-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="4cd9f-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4cd9f-108">[v] Cesta k souboru, který obsahuje manifest sestavení, pro které se budou generovat podpis silného názvu.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="4cd9f-109">[v] Název kontejneru klíčů, který obsahuje pár veřejného a privátního klíče.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="4cd9f-110">Pokud `pbKeyBlob` má hodnotu null, `wszKeyContainer` musíte zadat platný kontejner v rámci zprostředkovatele kryptografických služeb (CSP).</span><span class="sxs-lookup"><span data-stu-id="4cd9f-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="4cd9f-111">Pár klíčů, ukládat do kontejneru v takovém případě se používá k podepsání souboru.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="4cd9f-112">Pokud `pbKeyBlob` nemá hodnotu null, dvojici klíčů se předpokládá, že mají být obsažena v klíče binární rozsáhlý objekt (binární rozsáhlý OBJEKT).</span><span class="sxs-lookup"><span data-stu-id="4cd9f-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="4cd9f-113">[v] Ukazatel na pár veřejného a privátního klíče.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="4cd9f-114">Tato dvojice je ve formátu vytvořené Win32 `CryptExportKey` funkce.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="4cd9f-115">Pokud `pbKeyBlob` je null, kontejner klíčů určeného `wszKeyContainer` se předpokládá, že obsahovat dvojici klíčů.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="4cd9f-116">[v] Velikost v bajtech z `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="4cd9f-117">[out] Ukazatel na umístění, do které modul common language runtime vrátí podpis.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="4cd9f-118">Pokud `ppbSignatureBlob` je null, podpis modulu runtime ukládá do souboru určeného `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="4cd9f-119">Pokud `ppbSignatureBlob` je hodnotou not null, modul common language runtime přiděluje místo k vrácení podpis.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="4cd9f-120">Volající musí volné toto místo pomocí [strongnamefreebuffer –](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) funkce.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-120">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="4cd9f-121">[out] Velikost v bajtech vrácený podpis.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4cd9f-122">[v] Jeden nebo více z následujících hodnot:</span><span class="sxs-lookup"><span data-stu-id="4cd9f-122">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="4cd9f-123">`SN_SIGN_ALL_FILES`(0x00000001) - přepočítala všechny hodnoty hash pro propojené moduly.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="4cd9f-124">`SN_TEST_SIGN`(0x00000002) - test podepsání sestavení.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cd9f-125">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="4cd9f-125">Return Value</span></span>  
 <span data-ttu-id="4cd9f-126">`true`Při úspěšném dokončení; v opačném `false`.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cd9f-127">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4cd9f-127">Remarks</span></span>  
 <span data-ttu-id="4cd9f-128">Zadejte hodnotu null pro `wszFilePath` vypočítat velikost podpisu bez vytvoření podpisu.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="4cd9f-129">Podpis může být buď uložené přímo v souboru nebo vrácen volajícímu.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="4cd9f-130">Pokud `SN_SIGN_ALL_FILES` je zadán, ale není zahrnutý veřejný klíč (obě `pbKeyBlob` a `wszFilePath` mají hodnotu null), hodnoty hash pro propojené moduly jsou přepočítávány, ale není znovu podepisovat sestavení.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="4cd9f-131">Pokud `SN_TEST_SIGN` není zadaný, společné hlavičky runtime jazyka není upravit tak, aby znamenat, že je podepsaná sestavení se silným názvem.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="4cd9f-132">Pokud `StrongNameSignatureGenerationEx` není úspěšně dokončit, volání funkce [strongnameerrorinfo –](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funkce načíst poslední generované chyba.</span><span class="sxs-lookup"><span data-stu-id="4cd9f-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cd9f-133">Požadavky</span><span class="sxs-lookup"><span data-stu-id="4cd9f-133">Requirements</span></span>  
 <span data-ttu-id="4cd9f-134">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cd9f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cd9f-135">**Záhlaví:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="4cd9f-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4cd9f-136">**Knihovna:** zahrnuty jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cd9f-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4cd9f-137">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cd9f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd9f-138">Viz také</span><span class="sxs-lookup"><span data-stu-id="4cd9f-138">See Also</span></span>  
 [<span data-ttu-id="4cd9f-139">Strongnamesignaturegenerationex – metoda</span><span class="sxs-lookup"><span data-stu-id="4cd9f-139">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="4cd9f-140">Strongnamesignaturegeneration – metoda</span><span class="sxs-lookup"><span data-stu-id="4cd9f-140">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="4cd9f-141">Iclrstrongname – rozhraní</span><span class="sxs-lookup"><span data-stu-id="4cd9f-141">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)