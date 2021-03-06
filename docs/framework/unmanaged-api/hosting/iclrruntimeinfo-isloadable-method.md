---
title: "ICLRRuntimeInfo::IsLoadable – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsLoadable
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d3825f8dc529cf9c5fbfc44ae70008695e32054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a>ICLRRuntimeInfo::IsLoadable – metoda
Určuje, zda modul runtime přidružené toto rozhraní je možné načíst do aktuální proces, vezme v úvahu další moduly runtime, který může být již načtena do procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbLoadable`  
 [out] `true` Pokud tento modul runtime by mohla být načtena do aktuální proces, jinak hodnota `false`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda vrátí následující konkrétní hodnoty HRESULT a také HRESULT chyby, které označují selhání metoda.  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|Metoda byla úspěšně dokončena.|  
|E_POINTER|`pbLoadable`má hodnotu null.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud jiný modul runtime je již načtena do procesu a v procesu spuštění vedle sebe, mohou být načteny runtime spojené s tímto rozhraním `pbLoadable` vrátí `true`. Pokud dva moduly Runtime nelze spustit vedle sebe v rámci procesu, `pbLoadable` vrátí `false`. Modul CLR (CLR) verze 4 můžete například spustit-souběžného v rámci jednoho procesu s CLR verze 2.0 nebo CLR verze 1.1. Modul CLR verze 1.1 a verze modulu CLR 2.0 však nelze spustit vedle sebe v procesu.  
  
 Pokud jsou načteny žádné moduly runtime do procesu, tato metoda vždy vrátí `true`.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MetaHost.h  
  
 **Knihovna:** zahrnuty jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ICLRRuntimeInfo – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Rozhraní pro hostování](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hostování](../../../../docs/framework/unmanaged-api/hosting/index.md)
