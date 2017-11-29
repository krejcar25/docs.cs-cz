---
title: "ISymUnmanagedDocument::GetURL – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetURL
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 591383fee2f9b22a00956193555c719e72d722bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="211d5-102">ISymUnmanagedDocument::GetURL – metoda</span><span class="sxs-lookup"><span data-stu-id="211d5-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="211d5-103">Vrátí uniform resource locator (URL) pro tento dokument.</span><span class="sxs-lookup"><span data-stu-id="211d5-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="211d5-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="211d5-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="211d5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="211d5-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="211d5-106">[v] Velikost v znaků, z `szURL` vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="211d5-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="211d5-107">[out] Ukazatel na proměnnou, která přijímá velikost adresu URL, včetně null ukončení.</span><span class="sxs-lookup"><span data-stu-id="211d5-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="211d5-108">[out] Vyrovnávací paměti, který obsahuje adresu URL.</span><span class="sxs-lookup"><span data-stu-id="211d5-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="211d5-109">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="211d5-109">Return Value</span></span>  
 <span data-ttu-id="211d5-110">S_OK, pokud metoda úspěšně. jinak kód chyby.</span><span class="sxs-lookup"><span data-stu-id="211d5-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211d5-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="211d5-111">See Also</span></span>  
 [<span data-ttu-id="211d5-112">ISymUnmanagedDocument – rozhraní</span><span class="sxs-lookup"><span data-stu-id="211d5-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)