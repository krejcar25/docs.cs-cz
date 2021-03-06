---
title: "AssemblyBindInfo – struktura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyBindInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyBindInfo
helpviewer_keywords: AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bdf76b95e80d5d4d96d2b5ed8236018147167905
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="assemblybindinfo-structure"></a>AssemblyBindInfo – struktura
Poskytuje podrobné informace o odkazované sestavení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|`dwAppDomainId`|Jedinečný identifikátor `IStream` vrácený volání [ihostassemblystore::provideassembly –](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), ze které odkazované sestavení se jej načíst.|  
|`lpReferencedIdentity`|Jedinečný identifikátor pro odkazované sestavení.|  
|`lpPostPolicyIdentity`|Identifikátor pro odkazované sestavení po použití hodnoty zásad žádné vazby.|  
|`ePolicyLevel`|Jeden z [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) hodnoty, které označují, které zásady správy verzí, pokud existuje, bude použito k odkazované sestavení.|  
  
## <a name="remarks"></a>Poznámky  
 Hostitel poskytuje jedinečný identifikátor `dwAppDomainId` do common language runtime (CLR). Po volání `IHostAssemblyStore::ProvideAssembly` vrací, běhové prostředí používá k určení identifikátor zda obsah `IStream` namapované. Pokud ano, načte modul runtime existující kopie místo přemapování datového proudu. Modul runtime tento identifikátor také používá jako klíč vyhledávání pro datové proudy vrácená z volání [ihostassemblystore::providemodule –](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md). Identifikátor proto musí být jedinečný pro modul požadavky a požadavky sestavení.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MSCorEE.idl  
  
 **Knihovna:** zahrnuty jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Struktury pro hostování](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [ICLRAssemblyIdentityManager – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager – rozhraní](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore – rozhraní](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [ModuleBindInfo – struktura](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
