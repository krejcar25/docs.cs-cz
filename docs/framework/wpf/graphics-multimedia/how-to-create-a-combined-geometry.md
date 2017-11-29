---
title: "Postupy: Vytvoření kombinované geometrie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2be0471f27d26b145cc29847a08bf3bc3b1d51ff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="cad02-102">Postupy: Vytvoření kombinované geometrie</span><span class="sxs-lookup"><span data-stu-id="cad02-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="cad02-103">Tento příklad ukazuje, jak kombinovat geometrie.</span><span class="sxs-lookup"><span data-stu-id="cad02-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="cad02-104">Spojí dva geometrie, použijte <xref:System.Windows.Media.CombinedGeometry> objektu.</span><span class="sxs-lookup"><span data-stu-id="cad02-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="cad02-105">Nastavit jeho <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> a <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> vlastnosti s dvě geometrie kombinovat a nastavit <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> vlastnosti, která určuje, jak geometrie se spojí dohromady, k `Union`, `Intersect`, `Exclude`, nebo `Xor`.</span><span class="sxs-lookup"><span data-stu-id="cad02-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="cad02-106">K vytvoření složeného geometrie ze dvou nebo více geometrie, použijte <xref:System.Windows.Media.GeometryGroup>.</span><span class="sxs-lookup"><span data-stu-id="cad02-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cad02-107">Příklad</span><span class="sxs-lookup"><span data-stu-id="cad02-107">Example</span></span>  
 <span data-ttu-id="cad02-108">V následujícím příkladu <xref:System.Windows.Media.CombinedGeometry> je definovaná pomocí režim geometrie zkombinujte `Exclude`.</span><span class="sxs-lookup"><span data-stu-id="cad02-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="cad02-109">Obě <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> a <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> jsou definovány jako kroužky stejné radius, ale s posunem centrech 50.</span><span class="sxs-lookup"><span data-stu-id="cad02-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="cad02-110">![Výsledky vyřadit kombinování režimu](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="cad02-110">![Results of the Exclude combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="cad02-111">Kombinovaná geometrie vyloučení</span><span class="sxs-lookup"><span data-stu-id="cad02-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="cad02-112">V následující kód <xref:System.Windows.Media.CombinedGeometry> je definován s kombinační režim `Intersect`.</span><span class="sxs-lookup"><span data-stu-id="cad02-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="cad02-113">Obě <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> a <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> jsou definovány jako kroužky stejné radius, ale s posunem centrech 50.</span><span class="sxs-lookup"><span data-stu-id="cad02-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="cad02-114">![Výsledky Intersect kombinování režimu](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="cad02-114">![Results of the Intersect combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="cad02-115">Kombinovaná geometrie Intersect</span><span class="sxs-lookup"><span data-stu-id="cad02-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="cad02-116">V následující kód <xref:System.Windows.Media.CombinedGeometry> je definován s kombinační režim `Union`.</span><span class="sxs-lookup"><span data-stu-id="cad02-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="cad02-117">Obě <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> a <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> jsou definovány jako kroužky stejné radius, ale s posunem centrech 50.</span><span class="sxs-lookup"><span data-stu-id="cad02-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="cad02-118">![Výsledky sjednocení kombinování režimu](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="cad02-118">![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="cad02-119">Kombinovaná geometrie sjednocení</span><span class="sxs-lookup"><span data-stu-id="cad02-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="cad02-120">V následující kód <xref:System.Windows.Media.CombinedGeometry> je definován s kombinační režim `Xor`.</span><span class="sxs-lookup"><span data-stu-id="cad02-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="cad02-121">Obě <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> a <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> jsou definovány jako kroužky stejné radius, ale s posunem centrech 50.</span><span class="sxs-lookup"><span data-stu-id="cad02-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="cad02-122">![Výsledky Xor kombinování režimu](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="cad02-122">![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="cad02-123">Kombinovaná geometrie Xor</span><span class="sxs-lookup"><span data-stu-id="cad02-123">Combined Geometry Xor</span></span>