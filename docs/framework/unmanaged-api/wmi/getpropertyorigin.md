---
title: "Funkce GetPropertyOrigin (referenční dokumentace rozhraní API Unmnaged)"
description: "Funkce GetPropertyOrigin Určuje třídu, ve kterém je deklarovaná vlastnost."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyOrigin
helpviewer_keywords: GetPropertyOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 68df29e88b41cb12d002913d5bbd42050395d871
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="5a3fe-103">GetPropertyOrigin – funkce</span><span class="sxs-lookup"><span data-stu-id="5a3fe-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="5a3fe-104">Určuje třídu, ve kterém je deklarovaná vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5a3fe-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5a3fe-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="5a3fe-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="5a3fe-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5a3fe-107">[v] Tento parametr se nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5a3fe-108">[v] Ukazatel na [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="5a3fe-109">[v] Název vlastnosti pro objekt, jehož vlastnícím třída je požadováno.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="5a3fe-110">[out] Získá název třídy, která vlastní vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="5a3fe-111">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="5a3fe-111">Return value</span></span>

<span data-ttu-id="5a3fe-112">Následující hodnoty, vrátí tato funkce jsou definovány v *WbemCli.h* soubor hlaviček, případně je možné definovat je jako konstanty ve vašem kódu:</span><span class="sxs-lookup"><span data-stu-id="5a3fe-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5a3fe-113">Konstanta</span><span class="sxs-lookup"><span data-stu-id="5a3fe-113">Constant</span></span>  |<span data-ttu-id="5a3fe-114">Hodnota</span><span class="sxs-lookup"><span data-stu-id="5a3fe-114">Value</span></span>  |<span data-ttu-id="5a3fe-115">Popis</span><span class="sxs-lookup"><span data-stu-id="5a3fe-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="5a3fe-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="5a3fe-116">0x80041001</span></span> | <span data-ttu-id="5a3fe-117">Došlo k obecné chybě.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="5a3fe-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="5a3fe-118">0x80041002</span></span> | <span data-ttu-id="5a3fe-119">Zadaná vlastnost nebyla nalezena.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5a3fe-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5a3fe-120">0x80041008</span></span> | <span data-ttu-id="5a3fe-121">Parametr není platný.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5a3fe-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5a3fe-122">0x80041006</span></span> | <span data-ttu-id="5a3fe-123">Je k dispozici k dokončení operace není dostatek paměti.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5a3fe-124">0</span><span class="sxs-lookup"><span data-stu-id="5a3fe-124">0</span></span> | <span data-ttu-id="5a3fe-125">Volání funkce byla úspěšná.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5a3fe-126">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5a3fe-126">Remarks</span></span>

<span data-ttu-id="5a3fe-127">Tato funkce zabalí volání [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) metoda.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="5a3fe-128">Protože třídu můžete dědí vlastnosti ze základní třídy jeden nebo více, vývojáři často chtějí zjistit vlastnosti, ve kterém je definovaný dané metody.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="5a3fe-129">`pstrClassName` Parametr nesmí přejděte na platnou `BSTR` předtím, než je volána funkce, protože se jedná `out` parametr; tato ukazatel není navrácena po funkce vrátí hodnotu.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a3fe-130">Požadavky</span><span class="sxs-lookup"><span data-stu-id="5a3fe-130">Requirements</span></span>  
<span data-ttu-id="5a3fe-131">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a3fe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a3fe-132">**Záhlaví:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5a3fe-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5a3fe-133">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5a3fe-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3fe-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="5a3fe-134">See also</span></span>  
[<span data-ttu-id="5a3fe-135">Rozhraní WMI a čítače výkonu (referenční dokumentace nespravovaného rozhraní API)</span><span class="sxs-lookup"><span data-stu-id="5a3fe-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)