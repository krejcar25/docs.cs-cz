---
title: "IMetaDataImport::EnumPermissionSets – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumPermissionSets
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f31d35f21a16983b6ab9c23f1f65c3916b5138d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumpermissionsets-method"></a>IMetaDataImport::EnumPermissionSets – metoda
Vytvoří výčet oprávnění pro objekty v oboru Zadaná metadata.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `phEnum`  
 [ve out] Ukazatel na enumerátor. Toto musí mít hodnotu NULL pro první volání této metody.  
  
 `tk`  
 [v] Metadata token, který omezuje obor vyhledávání, nebo hodnota NULL pro vyhledávání možné nejširší rozsahu vyhledávání.  
  
 `dwActions`  
 [v] Flags – představující <xref:System.Security.Permissions.SecurityAction> hodnoty, které chcete zahrnout do `rPermission`, nebo nula, která vrátí všechny akce.  
  
 `rPermission`  
 [out] Pole používá k ukládání tokenů oprávnění.  
  
 `cMax`  
 [v] Maximální velikost `rPermission` pole.  
  
 `pcTokens`  
 [out] Číslo, vrátí se v tokenů oprávnění `rPermission`.  
  
## <a name="return-value"></a>Návratová hodnota  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets`úspěšně vrácena.|  
|`S_FALSE`|Neexistují žádné tokenů pro zobrazení výčtu. V takovém případě `pcTokens` je nulová.|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Cor.h  
  
 **Knihovna:** zahrnuty jako prostředek v MsCorEE.dll  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [IMetaDataImport – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
