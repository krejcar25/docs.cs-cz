---
title: "GetWin32ResBlob – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetWin32ResBlob
api_location: alink.dll
api_type: COM
f1_keywords: GetWin32ResBlob
helpviewer_keywords: GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c4456757c56440463010d4adc3d3eed90dbc07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="56507-102">GetWin32ResBlob – metoda</span><span class="sxs-lookup"><span data-stu-id="56507-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="56507-103">Načte objekt blob Win32 prostředků.</span><span class="sxs-lookup"><span data-stu-id="56507-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="56507-104">Tuto metodu volejte po nastavení možností sestavení.</span><span class="sxs-lookup"><span data-stu-id="56507-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56507-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="56507-105">Syntax</span></span>  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56507-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="56507-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="56507-107">ID sestavení.</span><span class="sxs-lookup"><span data-stu-id="56507-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="56507-108">Používá se k načtení název souboru, který se má použít při vytváření prostředků Win32 verze token souboru</span><span class="sxs-lookup"><span data-stu-id="56507-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="56507-109">Hodnota TRUE, pokud je soubor knihovny DLL, false pro EXE.</span><span class="sxs-lookup"><span data-stu-id="56507-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="56507-110">Volitelné ikony pro vložení do objektu blob prostředků.</span><span class="sxs-lookup"><span data-stu-id="56507-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="56507-111">Získá objekt blob prostředků.</span><span class="sxs-lookup"><span data-stu-id="56507-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="56507-112">Obdrží velikost objektu blob.</span><span class="sxs-lookup"><span data-stu-id="56507-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56507-113">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="56507-113">Return Value</span></span>  
 <span data-ttu-id="56507-114">Vrátí S_OK, pokud metoda bude úspěšná.</span><span class="sxs-lookup"><span data-stu-id="56507-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56507-115">Požadavky</span><span class="sxs-lookup"><span data-stu-id="56507-115">Requirements</span></span>  
 <span data-ttu-id="56507-116">Vyžaduje alink.h</span><span class="sxs-lookup"><span data-stu-id="56507-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56507-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="56507-117">See Also</span></span>  
 [<span data-ttu-id="56507-118">Ialink – rozhraní</span><span class="sxs-lookup"><span data-stu-id="56507-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="56507-119">Ialink2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="56507-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="56507-120">Rozhraní API ALink</span><span class="sxs-lookup"><span data-stu-id="56507-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)