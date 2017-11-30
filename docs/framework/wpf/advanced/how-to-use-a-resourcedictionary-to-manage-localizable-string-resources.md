---
title: "Postupy: Správa zdrojů lokalizovatelných řetězců pomocí ResourceDictionary"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 38cfd687eadf31cc94dfdd2cbbf082bf80424cba
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="6fbe1-102">Postupy: Správa zdrojů lokalizovatelných řetězců pomocí ResourceDictionary</span><span class="sxs-lookup"><span data-stu-id="6fbe1-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="6fbe1-103">Tento příklad ukazuje, jak používat <xref:System.Windows.ResourceDictionary> k balíčku lokalizovatelný řetězcové prostředky pro [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="6fbe1-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="6fbe1-104">Použít ResourceDictionary ke správě prostředků lokalizovatelný řetězec</span><span class="sxs-lookup"><span data-stu-id="6fbe1-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1.  <span data-ttu-id="6fbe1-105">Vytvoření <xref:System.Windows.ResourceDictionary> obsahující řetězce, které byste chtěli lokalizaci.</span><span class="sxs-lookup"><span data-stu-id="6fbe1-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="6fbe1-106">Následující kód ukazuje příklad.</span><span class="sxs-lookup"><span data-stu-id="6fbe1-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="6fbe1-107">Tento kód definuje prostředek řetězce `localizedMessage`, typu <xref:System.String>, z <xref:System> oboru názvů v mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="6fbe1-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2.  <span data-ttu-id="6fbe1-108">Přidat <xref:System.Windows.ResourceDictionary> k vaší aplikaci, pomocí následujícího kódu.</span><span class="sxs-lookup"><span data-stu-id="6fbe1-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  <span data-ttu-id="6fbe1-109">Použít řetězec prostředku z kódu, pomocí [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] podobně jako následující.</span><span class="sxs-lookup"><span data-stu-id="6fbe1-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  <span data-ttu-id="6fbe1-110">Pomocí řetězce prostředků z kódu, pomocí kódu podobně jako tento.</span><span class="sxs-lookup"><span data-stu-id="6fbe1-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  <span data-ttu-id="6fbe1-111">Lokalizace aplikace.</span><span class="sxs-lookup"><span data-stu-id="6fbe1-111">Localize the application.</span></span> <span data-ttu-id="6fbe1-112">Další informace najdete v tématu [lokalizaci aplikace](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="6fbe1-112">For more information, see [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span></span>