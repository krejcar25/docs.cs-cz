---
title: "ICeeGen::TruncateSection – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.TruncateSection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e7deaaab58f1ee51bd3675faec892db5228c787
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="iceegentruncatesection-method"></a>ICeeGen::TruncateSection – metoda
Zkrátí části zadaný kód pomocí zadané délky.  
  
 Tato metoda je zastaralá a by se neměla používat.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `section`  
 [v] V části zkrátit.  
  
 `len`  
 [v] Délka v bajtech, podle kterého zkrátit části.  
  
## <a name="remarks"></a>Poznámky  
 Volání `TruncateSection` pouze v případě, že máte speciální části požadavky, které nejsou zpracovány jinými metodami.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Cor.h  
  
 **Knihovna:** používat jako prostředek v MsCorEE.dll  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ICeeGen – rozhraní](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
