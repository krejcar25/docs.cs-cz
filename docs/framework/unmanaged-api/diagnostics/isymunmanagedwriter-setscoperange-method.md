---
title: "ISymUnmanagedWriter::SetScopeRange – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetScopeRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9afb0038adc4273033fb9f1db1ebc57f43eae779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetscoperange-method"></a>ISymUnmanagedWriter::SetScopeRange – metoda
Definuje rozsah pro zadaný obor lexikální posunu. Obor se stane nový aktuální obor a se posune do zásobníku oborů. Obory musí tvořit hierarchie. Položky na stejné úrovni nemohou překrývat.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a>Parametry  
 `scopeId`  
 [v] Identifikátor oboru pro obor.  
  
 `startOffset`  
 [v] Posun v bajtech je první instrukce v oboru lexikální od začátku metody.  
  
 `endOffset`  
 [v] Posun v bajtech je poslední instrukce v oboru lexikální od začátku metody.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK, pokud metoda úspěšně. v opačném E_FAIL nebo jiný kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [Isymunmanagedwriter::openscope –](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) vrátí identifikátor neprůhledného obor, který lze použít s `ISymUnmanagedWriter::SetScopeRange` k definování oboru je počáteční a koncové posunutí později. V takovém případě posunutí předaný `ISymUnmanagedWriter::OpenScope` a [isymunmanagedwriter::closescope –](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) jsou ignorovány. Identifikátory obor platí pouze v aktuální metoda.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Viz také  
 [ISymUnmanagedWriter – rozhraní](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
