---
title: "Funkce GetObjectText (referenční dokumentace nespravovaného rozhraní API)"
description: "Funkce GetObjectText vrací textové vykreslování objektu v syntaxi MOF."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetObjectText
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetObjectText
helpviewer_keywords: GetObjectText function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b47dc73bb9da71b0c8593aa5758179327d7572d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="getobjecttext-function"></a>GetObjectText – funkce
Vrátí textovou vykreslit objekt ve formátu MOF (Managed Object) syntaxe.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>Parametry

`vFunc`  
[v] Tento parametr se nepoužívá.

`ptr`  
[v] Ukazatel na [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.

`lFlags`  
[v] Za normálních okolností 0. Pokud `WBEM_FLAG_NO_FLAVORS` (nebo 0x1) je zadán, jsou zahrnuty bez informací o šíření nebo příchuť kvalifikátory.

`pstrObjectText`   
[out] Ukazatel na `null` na položku. Na vrátit, nově přidělených `BSTR` vykreslování syntaxe MOF objektu, který obsahuje.  

## <a name="return-value"></a>Návratová hodnota

Následující hodnoty, vrátí tato funkce jsou definovány v *WbemCli.h* soubor hlaviček, případně je možné definovat je jako konstanty ve vašem kódu:

|Konstanta  |Hodnota  |Popis  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Došlo k obecné chybě. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametr není platný. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Je k dispozici k dokončení operace není dostatek paměti. |
|`WBEM_S_NO_ERROR` | 0 | Volání funkce byla úspěšná.  |
  
## <a name="remarks"></a>Poznámky

Tato funkce zabalí volání [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) metoda.

Vrátí text MOF neobsahuje všechny informace o objektu, ale pouze dostatek informací pro kompilátor MOF moct původní objekt znovu vytvořit. Žádné šířený kvalifikátory nebo vlastnosti nadřazené třídy pro instanci, jsou zahrnuty.

Následující algoritmus se používá k rekonstrukci text parametry metody:

1. Parametry jsou resequenced v pořadí podle jejich hodnot identifikátoru.
1. Parametry, které jsou určeny jako `[in]` a `[out]` jsou sloučeny do jednoho parametru.
 
`pstrObjectText`musí být ukazatel na `null` při volání funkce; nesmí bodu na řetězec, který je platný před voláním metody, protože ukazatel nesmí být navrácena.

## <a name="requirements"></a>Požadavky  
**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** WMINet_Utils.idl  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Viz také  
[Rozhraní WMI a čítače výkonu (referenční dokumentace nespravovaného rozhraní API)](index.md)
