---
title: "IMetaDataEmit::DefineParam – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineParam
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4bf36edfad504f2858a45d5e34891042d8850bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineparam-method"></a>IMetaDataEmit::DefineParam – metoda
Vytvoří definici parametru podpisem zadaný pro metodu odkazuje zadaný token a získá token pro tuto definici parametru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `md`  
 [v] Token pro metodu, jejichž parametr je definovaný.  
  
 `ulParamSeq`  
 [v] Pořadové číslo parametru.  
  
 `szName`  
 [v] Název parametru v kódování Unicode.  
  
 `dwParamFlags`  
 [v] Příznaky pro parametr. Toto je bitová maska s `CorParamAttr` hodnoty.  
  
 `dwCPlusTypeFlag`  
 [v] `ELEMENT_TYPE_`  *\**  pro konstantní hodnotu.  
  
 `pValue`  
 [v] Konstantní hodnota pro parametr.  
  
 `cchValue`  
 [v] Velikost v znaky Unicode z `pValue`.  
  
 `ppd`  
 [out] `mdParamDef` Token přiřazený.  
  
## <a name="remarks"></a>Poznámky  
 Pořadí hodnot v `ulParamSeq` začínat 1 pro parametry. Vrácená hodnota má pořadové číslo 0.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Cor.h  
  
 **Knihovna:** používat jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [IMetaDataEmit – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
