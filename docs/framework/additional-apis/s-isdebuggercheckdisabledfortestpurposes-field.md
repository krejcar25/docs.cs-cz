---
title: s_isDebuggerCheckDisabledForTestPurposes pole
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
api_name: System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location: PresentationCore.dll
api_type: Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
robots: noindex,nofollow
ms.openlocfilehash: 97e5d32bff3e3150b56e8d9492aacc40f09f2afe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="517f1-102">s_isDebuggerCheckDisabledForTestPurposes pole</span><span class="sxs-lookup"><span data-stu-id="517f1-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="517f1-103">Toto pole privátní v `System.Windows.Diagnostics.VisualDiagnostics` třída se používá Visual Studio k určení, zda se provede interní kontrola pro aktivní ladicí program.</span><span class="sxs-lookup"><span data-stu-id="517f1-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="517f1-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="517f1-104">Syntax</span></span>
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  <span data-ttu-id="517f1-105">Rozhraní API v `System.Windows.Diagnostics.VisualDiagnostics` třídy jsou dostupné, jenom když aplikace běží pod ladicí program.</span><span class="sxs-lookup"><span data-stu-id="517f1-105">API's in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="517f1-106">Nastavit `s_isDebuggerCheckDisabledForTestPurposes` k `true` pro přístup k rozhraní API mimo ladicí program.</span><span class="sxs-lookup"><span data-stu-id="517f1-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>  
>   
>  <span data-ttu-id="517f1-107">Společnost Microsoft nepodporuje použití tohoto pole v produkční aplikace za žádných okolností.</span><span class="sxs-lookup"><span data-stu-id="517f1-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>  

## <a name="requirements"></a><span data-ttu-id="517f1-108">Požadavky</span><span class="sxs-lookup"><span data-stu-id="517f1-108">Requirements</span></span>

<span data-ttu-id="517f1-109">**Namespace:**<xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="517f1-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="517f1-110">**Sestavení:** PresentationCore (v knihovně PresentationCore.dll)</span><span class="sxs-lookup"><span data-stu-id="517f1-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="517f1-111">**Verze rozhraní .NET framework:** dostupné od verze 4.6.</span><span class="sxs-lookup"><span data-stu-id="517f1-111">**.NET Framework versions:** Available since 4.6.</span></span>