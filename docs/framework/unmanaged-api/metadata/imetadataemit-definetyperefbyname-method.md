---
title: "IMetaDataEmit::DefineTypeRefByName – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46b9fe83a5beb031d4ac21deb903060e2f788e1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName – metoda
Získá token metadat pro typ, který je definován v zadaném oboru, který není v aktuálním oboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `tkResolutionScope`  
 [v] Token zadání oboru rozlišení. Platné jsou následující typy tokenů:  
  
-   `mdModuleRef`, pokud typ je definovaná ve stejném sestavení, ve kterém je definovaný volající.  
  
-   `mdAssemblyRef`, pokud typ je definována v sestavení než ten, ve kterém je definovaný volající.  
  
-   `mdTypeRef`, pokud je typ vnořeného typu.  
  
-   `mdModule`, pokud typ je definovaná ve stejném modulu, ve kterém je definovaný volající.  
  
-   Hodnota Null, pokud typ je definována globálně.  
  
 `szName`  
 [v] Název cílového typu ve formátu Unicode.  
  
 `ptr`  
 [out] Ukazatel `mdTypeRef` token, který je přiřazen k typu.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Cor.h  
  
 **Knihovna:** používat jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [IMetaDataEmit – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
