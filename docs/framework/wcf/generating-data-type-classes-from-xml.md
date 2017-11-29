---
title: "Generování tříd datových typů z XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e0362673ebb7d686822fae594b3a41435ceb9a4d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="c9c66-102">Generování tříd datových typů z XML</span><span class="sxs-lookup"><span data-stu-id="c9c66-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="c9c66-103">zahrnuje nové funkce, která negeneruje třídy datového typu XML.</span><span class="sxs-lookup"><span data-stu-id="c9c66-103"> includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="c9c66-104">Toto téma popisuje, jak automaticky generovat datové typy pro informačního kanálu RSS blogu .NET.</span><span class="sxs-lookup"><span data-stu-id="c9c66-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="c9c66-105">Získání XML z RSS blogu .NET kanálu</span><span class="sxs-lookup"><span data-stu-id="c9c66-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1.  <span data-ttu-id="c9c66-106">V Internet Exploreru přejděte na [informačního kanálu RSS blogu .NET](https://blogs.msdn.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="c9c66-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://blogs.msdn.microsoft.com/dotnet/feed/).</span></span>  
  
2.  <span data-ttu-id="c9c66-107">Pravým tlačítkem myši a vyberte **zobrazit zdroj**.</span><span class="sxs-lookup"><span data-stu-id="c9c66-107">Right-click the page and select **View Source**.</span></span>  
  
3.  <span data-ttu-id="c9c66-108">Zkopírujte text informačního kanálu stisknutím **Ctrl + A** vyberte veškerý text a **Ctrl + C** ke kopírování.</span><span class="sxs-lookup"><span data-stu-id="c9c66-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="c9c66-109">Vytvoření datové typy</span><span class="sxs-lookup"><span data-stu-id="c9c66-109">Creating the data types</span></span>  
  
1.  <span data-ttu-id="c9c66-110">Otevřete soubor kódu, kde má být použita k proxy serveru.</span><span class="sxs-lookup"><span data-stu-id="c9c66-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="c9c66-111">Tento soubor musí být součástí [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] projektu.</span><span class="sxs-lookup"><span data-stu-id="c9c66-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="c9c66-112">Umístěte kurzor na místo v souboru mimo všech existujících tříd.</span><span class="sxs-lookup"><span data-stu-id="c9c66-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3.  <span data-ttu-id="c9c66-113">Vyberte **upravit**, **Vložit jinak**, **vložit XML jako třídy**.</span><span class="sxs-lookup"><span data-stu-id="c9c66-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4.  <span data-ttu-id="c9c66-114">Třídy názvem `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` a `rssChannelItemGuid` vytvářejí se členy potřebné pro přístup k elementů v informačního kanálu RSS.</span><span class="sxs-lookup"><span data-stu-id="c9c66-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="c9c66-115">Pomocí vygenerované třídy</span><span class="sxs-lookup"><span data-stu-id="c9c66-115">Using the generated classes</span></span>  
  
1.  <span data-ttu-id="c9c66-116">Jakmile se generují třídy, použitím v kódu jako ostatní třídy.</span><span class="sxs-lookup"><span data-stu-id="c9c66-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="c9c66-117">Následující příklad kódu vrátí novou instanci třídy `rssChannelImage` třídy.</span><span class="sxs-lookup"><span data-stu-id="c9c66-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```