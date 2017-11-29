---
title: "ISymUnmanagedReader – rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader
helpviewer_keywords: ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56e0012ae1412c0fb5b434d3b4c0221831296c60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="32b55-102">ISymUnmanagedReader – rozhraní</span><span class="sxs-lookup"><span data-stu-id="32b55-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="32b55-103">Představuje čtečku symbol, který poskytuje přístup k dokumentům, metod a proměnné v rámci úložiště symbolů.</span><span class="sxs-lookup"><span data-stu-id="32b55-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="32b55-104">Metody</span><span class="sxs-lookup"><span data-stu-id="32b55-104">Methods</span></span>  
  
|<span data-ttu-id="32b55-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-105">Method</span></span>|<span data-ttu-id="32b55-106">Popis</span><span class="sxs-lookup"><span data-stu-id="32b55-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="32b55-107">GetDocument – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="32b55-108">Vyhledá dokumentu.</span><span class="sxs-lookup"><span data-stu-id="32b55-108">Finds a document.</span></span>|  
|[<span data-ttu-id="32b55-109">Getdocuments – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="32b55-110">Vrátí pole všech dokumentů, které jsou definované v úložišti symbol.</span><span class="sxs-lookup"><span data-stu-id="32b55-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="32b55-111">Getdocumentversion – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="32b55-112">Získá určenou verzi zadaný dokument.</span><span class="sxs-lookup"><span data-stu-id="32b55-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="32b55-113">GetGlobalVariables – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="32b55-114">Vrátí všechny globální proměnné.</span><span class="sxs-lookup"><span data-stu-id="32b55-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="32b55-115">Getmethod – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="32b55-116">Získá metody čtečky symbol, zadaný token metoda.</span><span class="sxs-lookup"><span data-stu-id="32b55-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="32b55-117">Getmethodbyversion – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="32b55-118">Získá metody čtečky symbol, zadaný token metoda a čísla verze úpravy a kopie.</span><span class="sxs-lookup"><span data-stu-id="32b55-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="32b55-119">Getmethodfromdocumentposition – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="32b55-120">Vrátí metodu, která obsahuje bod přerušení na dané pozici v dokumentu.</span><span class="sxs-lookup"><span data-stu-id="32b55-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="32b55-121">Getmethodsfromdocumentposition – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="32b55-122">Vrátí pole metod, z nichž každý obsahuje zarážek na dané pozici v dokumentu.</span><span class="sxs-lookup"><span data-stu-id="32b55-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="32b55-123">Getmethodversion – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="32b55-124">Získá verzi metoda.</span><span class="sxs-lookup"><span data-stu-id="32b55-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="32b55-125">Getnamespaces – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="32b55-126">Získá oborů názvů definovaných v globálním oboru v rámci úložiště tento symbol.</span><span class="sxs-lookup"><span data-stu-id="32b55-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="32b55-127">Getsymattribute – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="32b55-128">Získá vlastní atribut na základě jeho názvu.</span><span class="sxs-lookup"><span data-stu-id="32b55-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="32b55-129">Getsymbolstorefilename – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="32b55-130">Obsahuje název souboru na disku úložiště symbolů.</span><span class="sxs-lookup"><span data-stu-id="32b55-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="32b55-131">Getuserentrypoint – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="32b55-132">Vrátí metodu, která byla zadána jako vstupní bod uživatele modulu, pokud existuje.</span><span class="sxs-lookup"><span data-stu-id="32b55-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="32b55-133">Getvariables – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="32b55-134">Vrátí proměnnou jiné než místní, daného jeho nadřazený a název.</span><span class="sxs-lookup"><span data-stu-id="32b55-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="32b55-135">Initialize – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="32b55-136">Inicializuje čtečky symbol s rozhraním program pro import metadat, které bude tato čtečky spojený s, spolu s názvem souboru modulu.</span><span class="sxs-lookup"><span data-stu-id="32b55-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="32b55-137">Replacesymbolstore – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="32b55-138">Nahradí existující úložiště symbolů s úložištěm symbol delta.</span><span class="sxs-lookup"><span data-stu-id="32b55-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="32b55-139">Updatesymbolstore – metoda</span><span class="sxs-lookup"><span data-stu-id="32b55-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="32b55-140">Aktualizuje existující úložiště symbolů s úložištěm symbol delta.</span><span class="sxs-lookup"><span data-stu-id="32b55-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32b55-141">Požadavky</span><span class="sxs-lookup"><span data-stu-id="32b55-141">Requirements</span></span>  
 <span data-ttu-id="32b55-142">**Záhlaví:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="32b55-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b55-143">Viz také</span><span class="sxs-lookup"><span data-stu-id="32b55-143">See Also</span></span>  
 [<span data-ttu-id="32b55-144">Rozhraní úložiště symbolů diagnostiky</span><span class="sxs-lookup"><span data-stu-id="32b55-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="32b55-145">Isymunmanagedreader2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="32b55-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)