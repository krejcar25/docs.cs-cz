---
title: "Ukázka technologie serializace verze"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a183664-bfbf-4ff0-96f6-c836284ea916
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e518d9c4477377e6d0d7e569a29efcf4801101fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="version-tolerant-serialization-technology-sample"></a><span data-ttu-id="b841f-102">Ukázka technologie serializace verze</span><span class="sxs-lookup"><span data-stu-id="b841f-102">Version Tolerant Serialization Technology Sample</span></span>
[<span data-ttu-id="b841f-103">Stažení ukázky</span><span class="sxs-lookup"><span data-stu-id="b841f-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/VTS.zip.exe)  
  
 <span data-ttu-id="b841f-104">Tento příklad znázorňuje verze funkce tolerance serializace rozhraní .NET.</span><span class="sxs-lookup"><span data-stu-id="b841f-104">This sample demonstrates the version tolerance features of .NET Serialization.</span></span> <span data-ttu-id="b841f-105">Ukázka sestavení aplikace, které používají různé verze <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> k serializaci a deserializaci data.</span><span class="sxs-lookup"><span data-stu-id="b841f-105">The sample builds applications that use different versions of a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> to serialize and deserialize data.</span></span> <span data-ttu-id="b841f-106">Bez ohledu na přítomnost jiný typ verze aplikace komunikovat bez problémů.</span><span class="sxs-lookup"><span data-stu-id="b841f-106">Despite the presence of different type versions, the applications communicate seamlessly.</span></span> <span data-ttu-id="b841f-107">Další informace najdete v tématu [verze serializace](../../../docs/standard/serialization/version-tolerant-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="b841f-107">For more information, see [Version Tolerant Serialization](../../../docs/standard/serialization/version-tolerant-serialization.md).</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="b841f-108">K vytvoření vzorku pomocí příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="b841f-108">To build the sample using the command prompt</span></span>  
  
1.  <span data-ttu-id="b841f-109">Otevřete okno příkazového řádku a přejděte do jednoho podadresáře konkrétní jazyk (v rámci aplikace V1 nebo V2 aplikace) pro vzorku.</span><span class="sxs-lookup"><span data-stu-id="b841f-109">Open a Command Prompt window and navigate to one of the language-specific subdirectories (under V1 Application or V2 Application) for the sample.</span></span>  
  
2.  <span data-ttu-id="b841f-110">Typ **msbuild.exe \<ver > application.sln** na příkazovém řádku (kde \<ver > je v1 nebo v2).</span><span class="sxs-lookup"><span data-stu-id="b841f-110">Type **msbuild.exe \<ver> application.sln** at the command line (where \<ver> is either v1 or v2).</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="b841f-111">K vytvoření vzorku pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b841f-111">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="b841f-112">Otevřít [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] a přejděte do jednoho podadresáře konkrétní jazyk pro vzorku.</span><span class="sxs-lookup"><span data-stu-id="b841f-112">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="b841f-113">Přejděte do aplikace V1 podadresáře adresáře, který jste vybrali v předchozím kroku.</span><span class="sxs-lookup"><span data-stu-id="b841f-113">Navigate to the V1 Application subdirectory of the directory you selected in the previous step.</span></span>  
  
3.  <span data-ttu-id="b841f-114">Poklepejte na ikonu V1 Application.sln k otevření souboru v sadě Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b841f-114">Double-click the icon for V1 Application.sln to open the file in Visual Studio.</span></span>  
  
4.  <span data-ttu-id="b841f-115">Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.</span><span class="sxs-lookup"><span data-stu-id="b841f-115">On the **Build** menu, click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="b841f-116">Přejděte do podadresáře V2 aplikace a opakujte předchozí dva kroky pro vytvoření aplikace V2.</span><span class="sxs-lookup"><span data-stu-id="b841f-116">Navigate to the V2 Application subdirectory and repeat the two previous steps to build the V2 Application.</span></span>  
  
 <span data-ttu-id="b841f-117">Aplikace bude vytvořen v výchozí \bin nebo \bin\Debug podadresářích adresáře jejich příslušného projektu.</span><span class="sxs-lookup"><span data-stu-id="b841f-117">The applications will be built in the default \bin or \bin\Debug subdirectories of their respective project directories.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="b841f-118">Chcete-li spustit ukázku</span><span class="sxs-lookup"><span data-stu-id="b841f-118">To run the sample</span></span>  
  
1.  <span data-ttu-id="b841f-119">V okně příkazového řádku přejděte na konkrétní jazyk podadresář, který jste vybrali, když jste vytvořili ukázkové aplikace.</span><span class="sxs-lookup"><span data-stu-id="b841f-119">In the Command Prompt window, navigate to the language-specific subdirectory that you selected when you built the sample applications.</span></span>  
  
2.  <span data-ttu-id="b841f-120">Typ **runme.cmd** na příkazovém řádku příkaz ke spuštění obou aplikací najednou.</span><span class="sxs-lookup"><span data-stu-id="b841f-120">Type **runme.cmd** at the command line to run both applications at once.</span></span>  
  
 <span data-ttu-id="b841f-121">Alternativně přejděte do adresáře, které obsahují nové spustitelné soubory a spustit je postupně.</span><span class="sxs-lookup"><span data-stu-id="b841f-121">Alternatively, navigate to the directories that contain the new executables and run them sequentially.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b841f-122">Ukázka sestavení aplikace konzoly.</span><span class="sxs-lookup"><span data-stu-id="b841f-122">The sample builds console applications.</span></span> <span data-ttu-id="b841f-123">Je nutné spustit a spustit v okně příkazového řádku, chcete-li zobrazit jejich výstup.</span><span class="sxs-lookup"><span data-stu-id="b841f-123">You must launch and run them in a Command Prompt window to view their output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b841f-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="b841f-124">See Also</span></span>  
 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
 <xref:System.IO.FileStream>