---
title: "ICorProfilerInfo::GetAssemblyInfo – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetAssemblyInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3ac5bd35d12bb4c9d9308dcdff3e1fb8385f6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a>ICorProfilerInfo::GetAssemblyInfo – metoda
Přijímá ID sestavení a vrátí název sestavení a ID jeho manifestu modul.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `assemblyId`  
 [v] Identifikátor sestavení.  
  
 `cchName`  
 [v] Délka ve znacích, z `szName`.  
  
 `pcchName`  
 [out] Ukazatel na celkový počet znaků názvu sestavení.  
  
 `szName`  
 [out] Zadaný volající široká znaková vyrovnávací paměti. Když funkce vrátí hodnotu, bude obsahovat název sestavení.  
  
 `pAppDomainId`  
 [out] Ukazatel na ID doménu aplikace, který obsahuje sestavení.  
  
 `pModuleId`  
 [out] Ukazatel na ID manifestu modulu sestavení.  
  
## <a name="remarks"></a>Poznámky  
 Po návratu tato metoda, musíte se ověřit, že `szName` vyrovnávací paměť byla dostatečně velký pro obsahovat úplný název sestavení. K tomuto účelu porovnat hodnotu, `pcchName` body s hodnotou `cchName` parametr. Pokud `pcchName` odkazuje na hodnotu, která je větší než `cchName`, přidělit větší `szName` vyrovnávací paměti, aktualizujte `cchName` s novou, větší velikost a volání `GetAssemblyInfo` znovu.  
  
 Alternativně můžete nejdřív volat `GetAssemblyInfo` s nulovou délkou `szName` vyrovnávací paměti se získat velikost správné vyrovnávací paměti. Potom můžete upravit velikost vyrovnávací paměti na základě hodnoty, vrátí se v `pcchName` a volání `GetAssemblyInfo` znovu.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ICorProfilerInfo – rozhraní](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Rozhraní pro profilaci](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilace](../../../../docs/framework/unmanaged-api/profiling/index.md)
