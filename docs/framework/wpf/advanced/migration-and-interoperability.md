---
title: Migrace a interoperabilita
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AutoGeneratedOrientationPage
helpviewer_keywords:
- Windows Presentation Foundation [WPF], interoperability
- WPF [WPF], migration
- Windows Forms controls [WPF interoperability]
- controls [WPF interoperability]
- Windows Presentation Foundation [WPF], migration
- interoperability [WPF]
- WPF [WPF], interoperability
- migration [WPF]
ms.assetid: d655de05-bf63-4814-bc64-6b3be01c70a2
caps.latest.revision: "41"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d469d5f53b97ec05e8714cff1ea663dda827a1a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="migration-and-interoperability"></a><span data-ttu-id="e9762-102">Migrace a interoperabilita</span><span class="sxs-lookup"><span data-stu-id="e9762-102">Migration and Interoperability</span></span>
<span data-ttu-id="e9762-103">Tato stránka obsahuje odkazy na dokumenty, které popisují, jak implementovat vzájemná spolupráce mezi [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplikací a dalších typů [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="e9762-103">This page contains links to documents that discuss how to implement interoperation between [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications and other types of [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9762-104">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="e9762-104">In This Section</span></span>  
 [<span data-ttu-id="e9762-105">WPF a vzájemná spolupráce Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9762-105">WPF and Windows Forms Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)  
 [<span data-ttu-id="e9762-106">WPF a vzájemná spolupráce Win32</span><span class="sxs-lookup"><span data-stu-id="e9762-106">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [<span data-ttu-id="e9762-107">WPF a vzájemná spolupráce procesu Direct3D9</span><span class="sxs-lookup"><span data-stu-id="e9762-107">WPF and Direct3D9 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)  
  
## <a name="reference"></a><span data-ttu-id="e9762-108">Odkaz</span><span class="sxs-lookup"><span data-stu-id="e9762-108">Reference</span></span>  
  
|<span data-ttu-id="e9762-109">Termín</span><span class="sxs-lookup"><span data-stu-id="e9762-109">Term</span></span>|<span data-ttu-id="e9762-110">Definice</span><span class="sxs-lookup"><span data-stu-id="e9762-110">Definition</span></span>|  
|----------|----------------|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<span data-ttu-id="e9762-111">Element, který můžete použít k hostiteli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ovládací prvek jako prvek [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stránky.</span><span class="sxs-lookup"><span data-stu-id="e9762-111">An element that you can use to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control as an element of a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<span data-ttu-id="e9762-112">A [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ovládací prvek, který můžete použít k hostiteli [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="e9762-112">A [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that you can use to host a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] control.</span></span>|  
|<xref:System.Windows.Interop.HwndSource>|<span data-ttu-id="e9762-113">Hostitelé [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oblast v rámci [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="e9762-113">Hosts a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] region within a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application.</span></span>|  
|<xref:System.Windows.Interop.HwndHost>|<span data-ttu-id="e9762-114">Základní třída pro <xref:System.Windows.Forms.Integration.WindowsFormsHost>, definuje některé základní funkce, které všechny na základě HWND technologie použijte, pokud hostované [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="e9762-114">Base class for <xref:System.Windows.Forms.Integration.WindowsFormsHost>, defines some basic functionality that all HWND-based technologies use when hosted by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="e9762-115">Podtřída to k hostování [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] okně v rámci [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="e9762-115">Subclass this to host a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window within a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>|  
|<xref:System.Windows.Interop.BrowserInteropHelper>|<span data-ttu-id="e9762-116">Pomocná třída pro podmínky prohlížeče prostředí pro vytváření sestav [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikace, která je hostovaná v prohlížeči.</span><span class="sxs-lookup"><span data-stu-id="e9762-116">A helper class for reporting conditions of the browser environment for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that is hosted by a browser.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="e9762-117">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="e9762-117">Related Sections</span></span>