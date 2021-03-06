---
title: "ISymUnmanagedDocument::GetSourceRange – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dcddebbca74bb94bd2411038a02b900b2f64f2d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>ISymUnmanagedDocument::GetSourceRange – metoda
Vrátí zadaný rozsah embedded zdroje do dané vyrovnávací paměti. Vyrovnávací paměti musí být dostatečně velký pro uložení zdroje.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a>Parametry  
 `startLine`  
 [v] Počáteční řádek v aktuálním dokumentu.  
  
 `startColumn`  
 [v] Počáteční sloupec v aktuálním dokumentu.  
  
 `endLine`  
 [v] Poslední řádek v aktuálním dokumentu.  
  
 `endColumn`  
 [v] Poslední sloupec v aktuálním dokumentu.  
  
 `cSourceBytes`  
 [v] Velikost zdroje v bajtech.  
  
 `pcSourceBytes`  
 [out] Ukazatel na proměnnou, která přijímá velikost zdroje.  
  
 `source`  
 [out] Velikost a délku zadaný rozsah zdrojový dokument v bajtech.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK, pokud metoda bude úspěšná.  
  
## <a name="see-also"></a>Viz také  
 [ISymUnmanagedDocument – rozhraní](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
