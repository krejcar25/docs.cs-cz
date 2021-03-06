---
title: "ICLRDataTarget2::AllocVirtual – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2.AllocVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d869b350217903dda209699f94897b70bc57132
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget2allocvirtual-method"></a>ICLRDataTarget2::AllocVirtual – metoda
Voláno rozhraním běžné jazyk služby modulu runtime (CLR) data přístup přidělit paměť v adresním prostoru tento cílový proces.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `addr`  
 [v] A `CLRDATA_ADDRESS` hodnotu, která určuje požadovanou počáteční adresa paměti, která bude přidělena.  
  
 `size`  
 [v] Velikost v bajtech, paměti, která bude přidělena.  
  
 `typeFlags`  
 [v] Příznaky, které řídí přidělení paměti. V tématu Win32 `VirtualAlloc` funkce.  
  
 `protectFlags`  
 [v] Atributy ochrany přidělené paměti. V tématu Win32 `VirtualAlloc` funkce.  
  
 `virt`  
 [out] Ukazatel na `CLRDATA_ADDRESS` hodnotu, která určuje skutečné počáteční adresa přidělené paměti.  
  
## <a name="remarks"></a>Poznámky  
 `AllocVirtual` Metoda slouží jako logické obálku pro Win32 `VirtualAlloc` funkce.  
  
 Tato metoda je implementována zapisovačem ladění aplikace.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** ClrData.idl, ClrData.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ICLRDataTarget2 – rozhraní](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [FreeVirtual – metoda](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
