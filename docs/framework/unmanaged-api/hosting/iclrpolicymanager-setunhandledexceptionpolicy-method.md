---
title: "ICLRPolicyManager::SetUnhandledExceptionPolicy – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ad287fedbc06768dd683c254292e0c28760d59a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a>ICLRPolicyManager::SetUnhandledExceptionPolicy – metoda
Určuje chování common language runtime (CLR), když dojde k neošetřené výjimce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `policy`  
 [v] Jeden z [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) hodnoty, která určuje, zda je nastaven chování modulu CLR nebo hostitele.  
  
## <a name="return-value"></a>Návratová hodnota  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|`SetUnhandledExceptionPolicy`úspěšně vrácena.|  
|HOST_E_CLRNOTAVAILABLE|Modul CLR nebyla načtena do procesu nebo CLR je ve stavu, ve kterém nemůže běžet spravovaného kódu nebo úspěšně zpracovat volání.|  
|HOST_E_TIMEOUT|Vypršel časový limit volání.|  
|HOST_E_NOT_OWNER|Volající není vlastníkem zámek.|  
|HOST_E_ABANDONED|Událost byla zrušena při blokované vlákna nebo fiber čekal na něm.|  
|E_FAIL|Došlo k neznámému závažné selhání. Po návratu metoda E_FAIL modulu CLR již není použitelné v rámci procesu. Následující volání hostování metody vrací HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Poznámky  
 Ve výchozím modulu CLR je poslední obslužné rutiny pro všechny neošetřené výjimky a jeho výchozí chování je přerušit proces. Hostitel může toto chování změnit v nastavení `policy` hodnotu eHostDeterminedPolicy. Tato hodnota umožňuje hostiteli implementovat vlastní výchozí chování, stejně jako u starších verzí modulu CLR.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MSCorEE.h  
  
 **Knihovna:** zahrnuty jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [EClrUnhandledException – výčet](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 [ICLRControl – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRPolicyManager – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager – rozhraní](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
