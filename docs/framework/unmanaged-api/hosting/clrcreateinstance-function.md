---
title: "CLRCreateInstance – funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type: COM
f1_keywords: CLRCreateInstance
helpviewer_keywords: CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d95815dd0b2a1cdbddcb28a2e176bc12d3270ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="clrcreateinstance-function"></a>CLRCreateInstance – funkce
Poskytuje jedno z tři rozhraní: [iclrmetahost –](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [iclrmetahostpolicy –](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), nebo [iclrdebugging –](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `clsid`  
 [v] Mezi tři identifikátory třídy: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy nebo CLSID_CLRDebugging.  
  
 `riid`  
 [v] Mezi tři identifikátorů rozhraní (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy nebo IID_ICLRDebugging.  
  
 `ppInterface`  
 [out] Mezi tři rozhraní: [iclrmetahost –](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [iclrmetahostpolicy –](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), nebo [iclrdebugging –](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda vrátí následující konkrétní hodnoty HRESULT a také HRESULT chyby, které označují selhání metoda.  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|Metoda byla úspěšně dokončena.|  
|E_POINTER|`ppInterface`má hodnotu null.|  
  
## <a name="remarks"></a>Poznámky  
 Následující tabulka uvádí podporované kombinace pro `clsid` a `riid`.  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|CLSID_CLRMetaHost|IID_ICLRMetaHost|  
|CLSID_CLRMetaHostPolicy|IID_ICLRMetaHostPolicy|  
|CLSID_CLRDebugging|IID_ICLRDebugging|  
  
 Následující kód ukazuje, jak používat `CLRCreateInstance` získat všechna tři rozhraní:  
  
```  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MetaHost.h  
  
 **Knihovna:** zahrnuty jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Hostování](../../../../docs/framework/unmanaged-api/hosting/index.md)
