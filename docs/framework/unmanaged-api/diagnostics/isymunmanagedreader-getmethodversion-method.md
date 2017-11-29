---
title: "ISymUnmanagedReader::GetMethodVersion – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b57407cb12e4315b6a144d157a201f857614d9f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="a0351-102">ISymUnmanagedReader::GetMethodVersion – metoda</span><span class="sxs-lookup"><span data-stu-id="a0351-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="a0351-103">Získá verzi metoda.</span><span class="sxs-lookup"><span data-stu-id="a0351-103">Gets the method version.</span></span> <span data-ttu-id="a0351-104">Metoda verze začíná na 1 a se zvýší pokaždé, když znovu zkompiluje metodu.</span><span class="sxs-lookup"><span data-stu-id="a0351-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="a0351-105">Rekompilace může dojít bez změny metody.</span><span class="sxs-lookup"><span data-stu-id="a0351-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0351-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a0351-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0351-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="a0351-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="a0351-108">[v] Metoda, pro které chcete získat verzi.</span><span class="sxs-lookup"><span data-stu-id="a0351-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="a0351-109">[out] Ukazatel na proměnné, která přijímá metoda verze.</span><span class="sxs-lookup"><span data-stu-id="a0351-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0351-110">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="a0351-110">Return Value</span></span>  
 <span data-ttu-id="a0351-111">S_OK, pokud metoda úspěšně. v opačném E_FAIL nebo jiný kód chyby.</span><span class="sxs-lookup"><span data-stu-id="a0351-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0351-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="a0351-112">Requirements</span></span>  
 <span data-ttu-id="a0351-113">**Záhlaví:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a0351-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0351-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="a0351-114">See Also</span></span>  
 [<span data-ttu-id="a0351-115">ISymUnmanagedReader – rozhraní</span><span class="sxs-lookup"><span data-stu-id="a0351-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)