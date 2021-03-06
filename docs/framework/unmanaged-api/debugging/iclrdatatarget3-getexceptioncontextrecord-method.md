---
title: "ICLRDataTarget3::GetExceptionContextRecord – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetContextRecord
api_location: mscordbi.dll
api_type: COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 517e2a692c3b67a85bc24437dd5fbaedd5fc7254
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>ICLRDataTarget3::GetExceptionContextRecord – metoda
Voláno rozhraním běžné jazyk služby modulu runtime (CLR) data přístup k načtení kontextu záznam přidružený tento cílový proces. Například pro výpis cíl, by to bylo ekvivalentní předaný prostřednictvím záznam kontextu `ExceptionParam` argument [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) funkce v knihovně k Windows ladění pomoci (DbgHelp).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `bufferSize`  
 [v] Vstupní vyrovnávací paměť velikost v bajtech. Toto musí být dostatečně velký na to, aby dokázala pojmout záznamu kontextu.  
  
 `bufferUsed`  
 [out] Ukazatel `ULONG32` typ, který obdrží počet bajtů ve skutečnosti zapsat do vyrovnávací paměti.  
  
 `buffer`  
 [out] Ukazatel na vyrovnávací paměť, která obdrží kopii záznamu kontextu. Výjimka záznam se vrátí jako [kontextu](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) typu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrácená hodnota je `S_OK` na úspěch nebo neúspěch `HRESULT` kód při selhání. `HRESULT` Kódy může zahrnovat, avšak nejsou omezeny na následující:  
  
|Návratový kód|Popis|  
|-----------------|-----------------|  
|`S_OK`|Metoda byla úspěšná. Záznam kontext byl zkopírován do výstupní vyrovnávací paměť.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Žádný záznam kontextu je přidružený k cíli.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Velikost vstupní vyrovnávací paměť není dostatečně velký na to, aby dokázala pojmout záznamu kontextu.|  
  
## <a name="remarks"></a>Poznámky  
 [KONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) je definován v záhlaví poskytované Windows SDK struktura specifické pro platformu.  
  
 Tato metoda je implementována zapisovačem ladění aplikace.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** ClrData.idl, ClrData.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ICLRDataTarget3 – rozhraní](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [GetExceptionRecord – metoda](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [GetExceptionThreadID – metoda](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
