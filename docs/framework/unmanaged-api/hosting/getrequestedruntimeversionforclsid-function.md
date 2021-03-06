---
title: "GetRequestedRuntimeVersionForCLSID – funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersionForCLSID
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersionForCLSID
helpviewer_keywords: GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be55754bc626ce24c51eec7b10d9f46aec92cfe5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID – funkce
Získá odpovídající běžné language runtime (CLR) verze informace pro třídu se zadaným `CLSID`.  
  
 Tato funkce se již nepoužívá v [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `rclsid`  
 [v]  `CLSID` Součásti.  
  
 `pVersion`  
 [out]  Vyrovnávací paměť, která obsahuje řetězec číslo verze po úspěšném dokončení.  
  
 `cchBuffer`  
 [v]  Velikost v široké znaky z `pVersion` vyrovnávací paměti.  
  
 `dwLength`  
 [out] Délka v bajtech vrácený vyrovnávací paměti.  
  
 `dwResolutionFlags`  
 [v]  Jedna z hodnot CLSID_RESOLUTION_FLAGS. Podporovány jsou následující hodnoty:  
  
-   CLSID_RESOLUTION_DEFAULT: (0x0) určuje výchozí chování spolupráce by měl být použit.  
  
-   CLSID_RESOLUTION_REGISTERED: (0x1) určuje, že registru by měl být vyhledávat a kód shim zásad by měla být použita.  
  
## <a name="return-value"></a>Návratová hodnota  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|Funkce vrátila úspěšně.|  
|E_INVALIDARG|Jeden z parametrů má neplatný typ nebo formát.|  
|ERROR_INSUFFICIENT_BUFFER|`pVersion` Vyrovnávací paměť není dostatečně velký pro uložení řetězec celou verzi.|  
|REGDB_E_CLASSNOTREG|Neexistuje žádná třída zaregistrovat se zadaným `CLSID`.|  
|E_POINTER|`dwLength`má hodnotu null, nebo `cchBuffer` je dostatečně velký pro uložení řetězec verze, ale `pVersion` má hodnotu null.|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MSCorEE.h  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Zastaralé funkce pro hostování CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
