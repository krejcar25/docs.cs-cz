---
title: "ICorDebugController::HasQueuedCallbacks – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.HasQueuedCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03d52bb31a81876a00e1af33494b14fb99fee0fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks – metoda
Získá hodnotu, která určuje, zda všechny spravované zpětná volání jsou aktuálně ve frontě pro zadaný vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [v] Ukazatel na objekt "ICorDebugThread", který představuje vlákno.  
  
 `pbQueued`  
 [out] Ukazatel na hodnotu, která je `true` Pokud žádné spravované zpětná volání jsou aktuálně ve frontě pro zadaný vlákno, jinak hodnota `false`.  
  
 Pokud je zadána hodnota null pro `pThread` parametr `HasQueuedCallbacks` vrátí `true` Pokud aktuálně nejsou k dispozici spravované zpětná volání zařazených do fronty pro všechny přístup z více vláken.  
  
## <a name="remarks"></a>Poznámky  
 Zpětná volání bude odeslat jeden po druhém, pokaždé, když [icordebugcontroller::Continue –](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) je volána. Ladicí program můžete zkontrolovat tento příznak, pokud chcete ohlásit více ladění událostí, které nastat současně.  
  
 Při ladění událostí jsou zařazeny do fronty, se již došlo, takže ladicí program musí vyprazdňování celý frontu jistotu stav ladění. (Volání `ICorDebugController::Continue` na vyprazdňování fronty.) Například, pokud fronty obsahuje dvě ladění události ve vlákně *X*, a ladicí program pozastaví vlákno *X* po první ladění událostí a volání `ICorDebugController::Continue`, druhá událost ladění pro vlákno *X* bude odeslána, i když vlákno bylo pozastaveno.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 
