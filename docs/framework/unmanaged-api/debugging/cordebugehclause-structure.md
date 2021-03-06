---
title: Struktura CorDebugEHClause
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugEHClause
api_location: mscordbi.dll
api_type: COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97428837d78c246915381b51fb5005a68518b7bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugehclause-structure"></a>Struktura CorDebugEHClause
[Podporované v rozhraní .NET Framework 4.5.2 a novějších verzích]  
  
 Představuje výjimku zpracování (EH) klauzuli pro určitou část kód intermediate language (IL).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|`Flags`|Bitová pole, které popisuje informace o výjimce v klauzuli EH. Další informace najdete v části poznámky.|  
|`TryOffset`|Posun v bajtech z `try` bloku od začátku těla metody.|  
|`TryLength`|Délka v bajtech z `try` bloku.|  
|`HandlerOffset`|Umístění obslužná rutina pro tento `try` bloku.|  
|`HandlerLength`|Velikost v bajtech kód obslužné rutiny.|  
|`ClassToken`|Token metadata pro obslužnou rutinu výjimky založený na typu.|  
|`FilterOffset`|Posun v bajtech, od začátku těla metody pro obslužnou rutinu na základě filtru výjimek.|  
  
## <a name="remarks"></a>Poznámky  
 Pole `CoreDebugEHClause` hodnoty vrátí [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) metoda.  
  
 Informace klauzule EH je definován specifikací rozhraní příkazového řádku. Další informace najdete v tématu [standardní ECMA-355: společné jazykové infrastruktury (CLI), 6. Edition](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 `flags` Pole může obsahovat následující příznaky. Všimněte si, že nejsou definovány v CorDebug.idl nebo CorDebug.h.  
  
|Příznak|Hodnota|Popis|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|0x00000000|Klauzuli typu výjimka.|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|0x00000001|Výjimka filtr a obslužné rutiny klauzuli.|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|0x00000002|A `finally` klauzule.|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|0x00000004|Klauzuli selhání ( `finally` klauzuli, která je volána, pouze když je vyvolána výjimka).|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [GetEHClauses – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)  
 [Struktury pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
