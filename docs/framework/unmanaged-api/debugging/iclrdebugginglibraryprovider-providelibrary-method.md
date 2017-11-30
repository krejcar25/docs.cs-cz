---
title: "ICLRDebuggingLibraryProvider::ProvideLibrary – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3a34579787e976022ffa8caf7c29d8a565a7c73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="ce28a-102">ICLRDebuggingLibraryProvider::ProvideLibrary – metoda</span><span class="sxs-lookup"><span data-stu-id="ce28a-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="ce28a-103">Získá zprostředkovatele knihovny rozhraní zpětné volání, které umožňuje common language runtime (CLR) specifické pro verzi ladění lze knihoven najít a načíst na vyžádání.</span><span class="sxs-lookup"><span data-stu-id="ce28a-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce28a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ce28a-104">Syntax</span></span>  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce28a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ce28a-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="ce28a-106">[v] Název modulu požadováno.</span><span class="sxs-lookup"><span data-stu-id="ce28a-106">[in] The name of the module being requested .</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="ce28a-107">[v] Časové razítko uložené v záhlaví souboru COFF PE souborů.</span><span class="sxs-lookup"><span data-stu-id="ce28a-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="ce28a-108">[v] `SizeOfImage` Pole, které jsou uložené v hlavičce COFF volitelný soubor PE souborů.</span><span class="sxs-lookup"><span data-stu-id="ce28a-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="ce28a-109">[out] Popisovač požadovaný modul.</span><span class="sxs-lookup"><span data-stu-id="ce28a-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce28a-110">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="ce28a-110">Return Value</span></span>  
 <span data-ttu-id="ce28a-111">Tato metoda vrátí následující konkrétní hodnoty HRESULT a také HRESULT chyby, které označují selhání metoda.</span><span class="sxs-lookup"><span data-stu-id="ce28a-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ce28a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce28a-112">HRESULT</span></span>|<span data-ttu-id="ce28a-113">Popis</span><span class="sxs-lookup"><span data-stu-id="ce28a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce28a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce28a-114">S_OK</span></span>|<span data-ttu-id="ce28a-115">Metoda byla úspěšně dokončena.</span><span class="sxs-lookup"><span data-stu-id="ce28a-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ce28a-116">Výjimky</span><span class="sxs-lookup"><span data-stu-id="ce28a-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce28a-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ce28a-117">Remarks</span></span>  
 <span data-ttu-id="ce28a-118">`ProvideLibrary`umožňuje zajistit moduly, které jsou potřebné pro ladění konkrétní soubory CLR například mscordbi.dll a souboru mscordacwks.dll ladicího programu.</span><span class="sxs-lookup"><span data-stu-id="ce28a-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="ce28a-119">Obslužné rutiny modulu muset nadále platné dokud volání [iclrdebugging::canunloadnow –](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) metoda označuje, že může být uvolněno na bod, který je odpovědností volajícího k bezplatným obslužné rutiny pro zpracování.</span><span class="sxs-lookup"><span data-stu-id="ce28a-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="ce28a-120">Ladicí program může používat všechny dostupné prostředky sami nebo můžete pořídit ladění modulu.</span><span class="sxs-lookup"><span data-stu-id="ce28a-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce28a-121">Tato funkce umožňuje rozhraní API volajícímu zadat modulů, které obsahují spustitelný soubor a potenciálně škodlivý kód.</span><span class="sxs-lookup"><span data-stu-id="ce28a-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="ce28a-122">Jako bezpečnostní opatření, neměli používat volající `ProvideLibrary` distribuovat žádný kód, že není chtěl provést sám sebe.</span><span class="sxs-lookup"><span data-stu-id="ce28a-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="ce28a-123">Pokud je zjištěno porušení zabezpečení závažné již vydaných knihovny, například mscordbi.dll nebo souboru mscordacwks.dll, dá shimu opravit rozpoznat chybná verze souborů.</span><span class="sxs-lookup"><span data-stu-id="ce28a-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="ce28a-124">Shim lze vydávat žádosti pro nainstalovanou opravou verze souborů a odmítnout chybná verze, pokud se poskytnou v reakci na žádnou žádostí.</span><span class="sxs-lookup"><span data-stu-id="ce28a-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="ce28a-125">Tato situace může nastat, pouze v případě, že uživatel má opravit na novou verzi shim.</span><span class="sxs-lookup"><span data-stu-id="ce28a-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="ce28a-126">Neopravené verze zůstane ohrožen.</span><span class="sxs-lookup"><span data-stu-id="ce28a-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce28a-127">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ce28a-127">Requirements</span></span>  
 <span data-ttu-id="ce28a-128">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce28a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce28a-129">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce28a-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce28a-130">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce28a-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce28a-131">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce28a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce28a-132">Viz také</span><span class="sxs-lookup"><span data-stu-id="ce28a-132">See Also</span></span>  
 [<span data-ttu-id="ce28a-133">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="ce28a-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ce28a-134">Ladění</span><span class="sxs-lookup"><span data-stu-id="ce28a-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)