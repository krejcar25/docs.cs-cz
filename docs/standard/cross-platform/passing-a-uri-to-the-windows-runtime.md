---
title: "Předávání identifikátorů URI do prostředí Windows Runtime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4ef77fb9e196abf046e0d4648a49b5d4d3fad47e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="3aeca-102">Předávání identifikátorů URI do prostředí Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="3aeca-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="3aeca-103">Prostředí Windows Runtime metody přijímají pouze absolutní identifikátory URI.</span><span class="sxs-lookup"><span data-stu-id="3aeca-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="3aeca-104">Pokud předáte relativní identifikátor URI k [!INCLUDE[wrt](../../../includes/wrt-md.md)] metody <xref:System.ArgumentException> je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="3aeca-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="3aeca-105">Tady je důvod, proč: při použití [!INCLUDE[wrt](../../../includes/wrt-md.md)] v rozhraní .NET Framework kódu [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) třídy se zobrazí jako <xref:System.Uri?displayProperty=nameWithType> v Intellisense.</span><span class="sxs-lookup"><span data-stu-id="3aeca-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="3aeca-106"><xref:System.Uri?displayProperty=nameWithType> Třída umožňuje relativní identifikátory URI, ale [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) třída neexistuje.</span><span class="sxs-lookup"><span data-stu-id="3aeca-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) class does not.</span></span> <span data-ttu-id="3aeca-107">To platí také pro metody vystavit v [!INCLUDE[wrt](../../../includes/wrt-md.md)] součásti.</span><span class="sxs-lookup"><span data-stu-id="3aeca-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="3aeca-108">Pokud příslušné součásti zpřístupní metodu, která přebírá identifikátor URI, zahrnuje podpis ve vašem kódu <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3aeca-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3aeca-109">Ale uživatelům vaší součásti, obsahuje podpis [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376).</span><span class="sxs-lookup"><span data-stu-id="3aeca-109">However, to users of your component, the signature includes [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376).</span></span> <span data-ttu-id="3aeca-110">Identifikátor URI, který je předán do příslušné součásti musí být absolutní identifikátor URI.</span><span class="sxs-lookup"><span data-stu-id="3aeca-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
 <span data-ttu-id="3aeca-111">Toto téma ukazuje, jak zjistit absolutní identifikátor URI a jak ho vytvořit ve vztahu k prostředku v balíčku aplikace.</span><span class="sxs-lookup"><span data-stu-id="3aeca-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="3aeca-112">Zjišťování a používání absolutní identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="3aeca-112">Detecting and using an absolute URI</span></span>  
 <span data-ttu-id="3aeca-113">Použití <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> vlastnost zajistěte, aby byl identifikátor URI absolutní před předáním na [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3aeca-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="3aeca-114">Pomocí této vlastnosti je efektivnější než zachytávání a zpracování <xref:System.ArgumentException> výjimka.</span><span class="sxs-lookup"><span data-stu-id="3aeca-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="3aeca-115">Pomocí absolutní identifikátor URI pro prostředek v balíčku aplikace</span><span class="sxs-lookup"><span data-stu-id="3aeca-115">Using an absolute URI for a resource in the app package</span></span>  
 <span data-ttu-id="3aeca-116">Pokud chcete určit identifikátor URI pro prostředek, který obsahuje váš balíček aplikace, můžete použít `ms-appx` nebo `ms-appx-web` schéma vytvořit absolutní identifikátor URI.</span><span class="sxs-lookup"><span data-stu-id="3aeca-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
 <span data-ttu-id="3aeca-117">Následující příklad ukazuje, jak nastavit [zdroj](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) vlastnost pro [webové zobrazení](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) řízení a [zdroj](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) vlastnost pro [Image](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) ovládací prvek na prostředky, které jsou obsaženy ve složce s názvem stránek pomocí XAML a kódu.</span><span class="sxs-lookup"><span data-stu-id="3aeca-117">The following example shows how to set the [Source](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) property for a [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) control and the [Source](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) property for an [Image](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 <span data-ttu-id="3aeca-118">Další informace o těchto režimů najdete v tématu [schémata identifikátoru URI](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) ve službě Windows Dev Center.</span><span class="sxs-lookup"><span data-stu-id="3aeca-118">For more information about these schemes, see [URI schemes](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aeca-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="3aeca-119">See Also</span></span>  
 [<span data-ttu-id="3aeca-120">Podpora v rozhraní .NET framework pro aplikace pro Windows Store a prostředí Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="3aeca-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)