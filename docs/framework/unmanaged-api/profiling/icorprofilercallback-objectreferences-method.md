---
title: "ICorProfilerCallback::ObjectReferences – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30b8f6b5f424ff81ace36baa8d2ae39e0a2f1d1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences – metoda
Upozorní profileru o objektech v paměti, které se odkazuje zadaný objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a>Parametry  
 `objectId`  
 [v] ID objektu, která odkazují objekty.  
  
 `classId`  
 [v] ID třídy, která představuje instanci zadaného objektu.  
  
 `cObjectRefs`  
 [v] Počet objektů, které odkazuje zadaný objekt (který je počet elementů ve `objectRefIds` pole).  
  
 `objectRefIds`  
 [v] Pole ID objektů, které se odkazuje `objectId`.  
  
## <a name="remarks"></a>Poznámky  
 `ObjectReferences` Metoda je volána pro každý objekt v haldě zbývající po dokončení uvolnění paměti. Pokud profileru vrátí chybu z této zpětné volání, bude zastaveno profilování služby vyvolání tento zpětného volání až do další uvolnění paměti.  
  
 `ObjectReferences` Zpětného volání lze použít ve spojení s [icorprofilercallback::rootreferences –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) zpětné volání pro vytvoření grafu odkaz dokončení objektu pro modul runtime. Modul CLR (CLR) zajišťuje, že každý odkaz na objekt je hlášen jenom jednou `ObjectReferences` metoda.  
  
 Vrácený objekt ID `ObjectReferences` nejsou platné během zpětného volání sebe, protože kolekce paměti může být uprostřed přesun objektů. Proto se profilery nesmíte pokoušet zkontrolovat objekty během `ObjectReferences` volání. Když [icorprofilercallback2::garbagecollectionfinished –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) je volána paměti kolekce je úplný a kontroly lze bezpečně provést.  
  
 Null `ClassId` znamená, že `objectId` má typ, který je uvolnění.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ICorProfilerCallback – rozhraní](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
