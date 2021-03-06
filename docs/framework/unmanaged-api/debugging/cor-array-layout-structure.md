---
title: "COR_ARRAY_LAYOUT – struktura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_ARRAY_LAYOUT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_ARRAY_LAYOUT
helpviewer_keywords: COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b936b1b2187ec68db7f5fdecb0344e6cac211ab1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="corarraylayout-structure"></a>COR_ARRAY_LAYOUT – struktura
Poskytuje informace o rozložení objektu pole v paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;   
    ULONG32 rankSize;   
    ULONG32 numRanks;   
    ULONG32 rankOffset;   
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|`componentID`|Identifikátor typu objektů, které obsahuje pole.|  
|`componentType`|CorElementType – výčet hodnotu, která určuje, zda je součást odkaz kolekce paměti, – hodnotová třída nebo jednoduchého typu.|  
|`firstElementOffset`|Posun oproti první prvek v poli.|  
|`elementSize`|Velikost jednotlivých prvků.|  
|`countOffset`|Posun oproti počet prvků v poli.|  
|`rankSize`|Velikost pořadí, v bajtech.|  
|`numRanks`|Počet pořadí v poli.|  
|`rankOffset`|Posun, ve kterém je pořadí spuštění.|  
  
## <a name="remarks"></a>Poznámky  
 `rankSize` Pole určuje velikost pořadí v vícerozměrné. Je přesné pro také jednorozměrná pole.  
  
 Hodnota `numRanks` 1 pro jednorozměrná pole a `N` pro multidimenzionální pole `N` dimenzí.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Struktury pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Ladění](../../../../docs/framework/unmanaged-api/debugging/index.md)
