---
title: "x:Members – direktiva"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 230c6359c59b9f00738de9ce7ceeccd69899135f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="xmembers-directive"></a><span data-ttu-id="07538-102">x:Members – direktiva</span><span class="sxs-lookup"><span data-stu-id="07538-102">x:Members Directive</span></span>
<span data-ttu-id="07538-103">Obsahuje sadu členů, které jsou definovány v značek, které se vztahují na x: Class – nadřazeného elementu.</span><span class="sxs-lookup"><span data-stu-id="07538-103">Holds a set of members that are defined in markup, which apply to the x:Class of the parent element.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="07538-104">Použití atributu XAML</span><span class="sxs-lookup"><span data-stu-id="07538-104">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="07538-105">Hodnoty XAML</span><span class="sxs-lookup"><span data-stu-id="07538-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="07538-106">Název základní třídy nebo částečné třídy pro produkční XAML.</span><span class="sxs-lookup"><span data-stu-id="07538-106">Name of the backing class or partial class for the XAML production.</span></span> <span data-ttu-id="07538-107">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="07538-107">See Remarks.</span></span>|  
|`oneOrMoreMembers`|<span data-ttu-id="07538-108">Jeden či více elementů objektu, které představují definice člen.</span><span class="sxs-lookup"><span data-stu-id="07538-108">One or more object elements that represent member definitions.</span></span> <span data-ttu-id="07538-109">Obvykle jde o `x:Property` objektu elementy.</span><span class="sxs-lookup"><span data-stu-id="07538-109">Typically, these are `x:Property` object elements.</span></span> <span data-ttu-id="07538-110">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="07538-110">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07538-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="07538-111">Remarks</span></span>  
 <span data-ttu-id="07538-112">Implementace rozhraní .NET Framework XAML Services není žádná základní třídu nebo základní člen implementaci pro `x:Members`.</span><span class="sxs-lookup"><span data-stu-id="07538-112">In the .NET Framework XAML Services implementation, there is no backing class or underlying member implementation for `x:Members`.</span></span> <span data-ttu-id="07538-113">`x:Members`je speciální XAML člena, který může existovat jako člena na libovolného typu.</span><span class="sxs-lookup"><span data-stu-id="07538-113">`x:Members` is a special XAML member that can exist as a member on any type.</span></span> <span data-ttu-id="07538-114">V datový proud uzlu XAML `x:Members` je reprezentován jako člen s názvem `Members`, z oboru názvů jazyka XAML jazyka XAML.</span><span class="sxs-lookup"><span data-stu-id="07538-114">In a XAML node stream, `x:Members` is represented as a member named `Members`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="07538-115">Člen `Members` obsahuje jen pro čtení obecné seznam `Member` objekty.</span><span class="sxs-lookup"><span data-stu-id="07538-115">The member `Members` contains a read-only generic list of `Member` objects.</span></span> <span data-ttu-id="07538-116">V typické značek jsou jednotlivé členy zadané jako `x:Property` vlastnost elementy.</span><span class="sxs-lookup"><span data-stu-id="07538-116">In typical markup the individual members are specified as `x:Property` property elements.</span></span> <span data-ttu-id="07538-117">`x:Property`je typu přesnější speciálně pro vlastnosti typů a přiřadit k `x:Member`.</span><span class="sxs-lookup"><span data-stu-id="07538-117">`x:Property` is a more precise type specifically for properties of types and is assignable to `x:Member`.</span></span> <span data-ttu-id="07538-118">Další informace najdete v tématu [x: Property – direktiva](../../../docs/framework/xaml-services/x-property-directive.md).</span><span class="sxs-lookup"><span data-stu-id="07538-118">For more information, see [x:Property Directive](../../../docs/framework/xaml-services/x-property-directive.md).</span></span>  
  
 <span data-ttu-id="07538-119">Pro podporu praktické využití `x:Members` jako prostředek k zadávání definice člen v kódu, musí být přidružen třídu, která je možné upravit členy.</span><span class="sxs-lookup"><span data-stu-id="07538-119">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="07538-120">Je určený model, který `x:Members` existuje jako člena typu, který určuje `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="07538-120">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="07538-121">Tento mechanismus pro přidružení typy a členy nebo pro vytvoření definice dynamického člena však není podporován na úrovni rozhraní .NET Framework XAML Services.</span><span class="sxs-lookup"><span data-stu-id="07538-121">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="07538-122">To je zleva jednotlivé rozhraní, které mají modelů aplikace, které podporují definice člena z XAML.</span><span class="sxs-lookup"><span data-stu-id="07538-122">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="07538-123">Obvykle MSBUILD sestavení akce, které kompilace kódu XAML a buď ji integrovat s nástrojem kódu nebo produktu čistě z XAML sestavení jsou potřeba k podpoře této funkce.</span><span class="sxs-lookup"><span data-stu-id="07538-123">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xmembers-for-windows-workflow-foundation"></a><span data-ttu-id="07538-124">x: Members pro Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="07538-124">x:Members for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="07538-125">Pro Windows Workflow Foundation `x:Members` obsahuje členy vlastní aktivita tvoří zcela v jazyce XAML, nebo XAML – definované dynamické členy pro Návrhář aktivity s kódem v pozadí.</span><span class="sxs-lookup"><span data-stu-id="07538-125">For Windows Workflow Foundation, `x:Members` contains the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="07538-126">`x:Class`musí být zadaná také v kořenovém elementu provozních XAML.</span><span class="sxs-lookup"><span data-stu-id="07538-126">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="07538-127">To není požadavek na úrovni rozhraní .NET Framework XAML Services, ale při načtení provozní XAML akcemi MSBUILD sestavení, které podporují vlastní aktivity a Windows Workflow Foundation XAML obecně se změní na požadavek.</span><span class="sxs-lookup"><span data-stu-id="07538-127">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="07538-128">`x:Members`musí být první podřízený prvek ve značce elementu objekt, který deklaruje `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="07538-128">`x:Members` must be the first child element in markup of the object element that declares the `x:Class`.</span></span>