---
title: "ICorDebugAppDomain3 – rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3
helpviewer_keywords: ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 017a2f018569b17c0b0011638e16f1921b6c9801
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain3-interface"></a>ICorDebugAppDomain3 – rozhraní
Poskytuje metody k načtení informací o spravovaných reprezentace [!INCLUDE[wrt](../../../../includes/wrt-md.md)] typy momentálně načtených v doméně aplikace. Toto rozhraní je rozšířením ICorDebugAppDomain a icordebugappdomain2 – rozhraní.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Icordebugappdomain3::getcachedwinrttypes –](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Získá enumerátor pro všechny uložené v mezipaměti [!INCLUDE[wrt](../../../../includes/wrt-md.md)] typy.|  
|[Icordebugappdomain3::getcachedwinrttypesforiids –](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Získá enumerátor pro uložené v mezipaměti [!INCLUDE[wrt](../../../../includes/wrt-md.md)] typy v doméně aplikace podle jejich identifikátory rozhraní.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je určen pro použití ve ladicí program ve spojení s vyhodnocení volání funkce `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Když metoda načte identifikátory rozhraní nepodporuje [!INCLUDE[wrt](../../../../includes/wrt-md.md)] objektu serveru ladicí program může používat metody definované v tomto rozhraní mapování na spravované typy, které odpovídají těchto rozhraní.  
  
 Chcete-li načíst instanci tohoto rozhraní, spusťte `QueryInterface` v instanci ICorDebugAppDomain nebo icordebugappdomain2 – rozhraní.  
  
> [!NOTE]
>  Toto rozhraní nepodporuje volané vzdáleně, mezi počítači nebo mezi procesy.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
