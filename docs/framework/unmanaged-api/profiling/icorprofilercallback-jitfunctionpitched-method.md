---
title: "ICorProfilerCallback::JITFunctionPitched – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITFunctionPitched
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48432911d7844e6519689961c985da37219179a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>ICorProfilerCallback::JITFunctionPitched – metoda
Upozorní profileru, funkci, která byla v běhu (JIT)-zkompilovat byl odebrán z paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `functionId`  
 [v] ID funkce, která byla odebrána.  
  
## <a name="remarks"></a>Poznámky  
 Pokud odebrané funkce je volána, obdrží profileru nové události JIT – kompilace při znovu zkompiluje funkce. V současné době běžné language runtime (CLR) JIT kompilátoru neodebere funkce z paměti, tak, aby tento zpětného volání není aktuálně používá a nebude přijatých profileru.  
  
 Hodnota `functionId` není platná, dokud nebude znovu zkompiluje funkce. Když znovu zkompiluje funkce stejné `functionId` bude použita hodnota.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ICorProfilerCallback – rozhraní](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
