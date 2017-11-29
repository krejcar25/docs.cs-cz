---
title: "Funkce NextMethod (referenční dokumentace nespravovaného rozhraní API)"
description: "Funkce NextMethod načte další metoda ve výčtu."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: NextMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: NextMethod
helpviewer_keywords: NextMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9b14424bb914be3ba127670e1b6490f79854d6e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="nextmethod-function"></a><span data-ttu-id="fdd2f-103">NextMethod – funkce</span><span class="sxs-lookup"><span data-stu-id="fdd2f-103">NextMethod function</span></span>
<span data-ttu-id="fdd2f-104">Načte metodu další v výčet, který začíná volání [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="fdd2f-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fdd2f-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fdd2f-105">Syntax</span></span>  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="fdd2f-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="fdd2f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fdd2f-107">[v] Tento parametr se nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="fdd2f-108">[v] Ukazatel na [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="fdd2f-109">[v] Vyhrazena.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-109">[in] Reserved.</span></span> <span data-ttu-id="fdd2f-110">Tento parametr musí být 0.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="fdd2f-111">[out] Ukazatele, který odkazuje na `null` před voláním.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="fdd2f-112">Když funkce vrátí hodnotu, na novou adresu `BSTR` obsahující název metody.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="fdd2f-113">[out] Ukazatele, který obdrží ukazatel na [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) obsahující `in` parametry pro metodu.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-113">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="fdd2f-114">[out] Ukazatele, který obdrží ukazatel na [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) obsahující `out` parametry pro metodu.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-114">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="fdd2f-115">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="fdd2f-115">Return value</span></span>

<span data-ttu-id="fdd2f-116">Následující hodnoty, vrátí tato funkce jsou definovány v *WbemCli.h* soubor hlaviček, případně je možné definovat je jako konstanty ve vašem kódu:</span><span class="sxs-lookup"><span data-stu-id="fdd2f-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fdd2f-117">Konstanta</span><span class="sxs-lookup"><span data-stu-id="fdd2f-117">Constant</span></span>  |<span data-ttu-id="fdd2f-118">Hodnota</span><span class="sxs-lookup"><span data-stu-id="fdd2f-118">Value</span></span>  |<span data-ttu-id="fdd2f-119">Popis</span><span class="sxs-lookup"><span data-stu-id="fdd2f-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="fdd2f-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="fdd2f-120">0x8004101d</span></span> | <span data-ttu-id="fdd2f-121">Byl bez volání [ `BeginEnumeration` ](beginenumeration.md) funkce.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="fdd2f-122">0</span><span class="sxs-lookup"><span data-stu-id="fdd2f-122">0</span></span> | <span data-ttu-id="fdd2f-123">Volání funkce byla úspěšná.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="fdd2f-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="fdd2f-124">0x40005</span></span> | <span data-ttu-id="fdd2f-125">Ve výčtu nejsou žádné další vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="fdd2f-126">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fdd2f-126">Remarks</span></span>

<span data-ttu-id="fdd2f-127">Tato funkce zabalí volání [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) metoda.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-127">This function wraps a call to the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="fdd2f-128">Volající začne pořadí výčtu voláním [BeginMethodEnumeration](beginmethodenumeration.md) fungovat a pak zavolá funkci [NextMethod], dokud funkce vrátí hodnotu `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="fdd2f-129">Volitelně volající dokončení sekvenci voláním [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="fdd2f-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="fdd2f-130">Volající ukončovat výčtu již v rané fázi voláním [EndMethodEnumeration](endmethodenumeration.md) kdykoli.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="fdd2f-131">Příklad</span><span class="sxs-lookup"><span data-stu-id="fdd2f-131">Example</span></span>

<span data-ttu-id="fdd2f-132">Příklad, C++, najdete v článku [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) metoda.</span><span class="sxs-lookup"><span data-stu-id="fdd2f-132">For a C++ example, see the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fdd2f-133">Požadavky</span><span class="sxs-lookup"><span data-stu-id="fdd2f-133">Requirements</span></span>  
 <span data-ttu-id="fdd2f-134">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdd2f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdd2f-135">**Záhlaví:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fdd2f-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fdd2f-136">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fdd2f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd2f-137">Viz také</span><span class="sxs-lookup"><span data-stu-id="fdd2f-137">See also</span></span>  
[<span data-ttu-id="fdd2f-138">Rozhraní WMI a čítače výkonu (referenční dokumentace nespravovaného rozhraní API)</span><span class="sxs-lookup"><span data-stu-id="fdd2f-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)