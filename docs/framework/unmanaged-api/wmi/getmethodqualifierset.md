---
title: "Funkce GetMethodQualifierSet (referenční dokumentace nespravovaného rozhraní API)"
description: "Funkce GetMethodQualifierSet načte metoda kvalifikátor sady."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethodQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethodQualifierSet
helpviewer_keywords: GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2999bef31576cf2bc025868260c2b1782a9b69f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="getmethodqualifierset-function"></a>GetMethodQualifierSet – funkce
Načte kvalifikátor nastavit pro konkrétní metody.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>Parametry

`vFunc`  
[v] Tento parametr se nepoužívá.

`ptr`  
[v] Ukazatel na [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.

`wszMethod`  
[v] Název metody. `wszMethod`musí odkazovat na platný `LPCWSTR`. 

`ppQualSet`  
[out] Ukazatel rozhraní, které umožňuje přístup k kvalifikátory metody obdrží. `ppQualSet`nemůže být `null`. Pokud dojde k chybě, nevrátí nový objekt a ukazatel je nastaven tak, aby odkazoval na `null`. 

## <a name="return-value"></a>Návratová hodnota

Následující hodnoty, vrátí tato funkce jsou definovány v *WbemCli.h* soubor hlaviček, případně je možné definovat je jako konstanty ve vašem kódu:

|Konstanta  |Hodnota  |Popis  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Zadaná metoda neexistuje. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametr je `null`. |
|`WBEM_S_NO_ERROR` | 0 | Volání funkce byla úspěšná.  |
  
## <a name="remarks"></a>Poznámky

Tato funkce zabalí volání [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) metoda. 

Volání této funkce je podporována pouze v případě, že je aktuální objekt definice třídy CIM. Není k dispozici pro manipulaci s metoda [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters, které odkazují na modelu CIM instancí.

Protože každá metoda může mít svůj vlastní kvalifikátory [IWbemQualifierSet ukazatel](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) umožňuje přidat, upravit nebo odstranit tyto kvalifikátory volající.

## <a name="requirements"></a>Požadavky  
**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** WMINet_Utils.idl  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Viz také  
[Rozhraní WMI a čítače výkonu (referenční dokumentace nespravovaného rozhraní API)](index.md)
