---
title: "Ukázka třída SchemaImporterExtension technologie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f5eb78f-0ef6-433a-b095-3a63b1ce0bc9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 68e89053d1d4a36a0f015ed4e0082ae88e1de6a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="schemaimporterextension-technology-sample"></a><span data-ttu-id="59be6-102">Ukázka třída SchemaImporterExtension technologie</span><span class="sxs-lookup"><span data-stu-id="59be6-102">SchemaImporterExtension Technology Sample</span></span>
[<span data-ttu-id="59be6-103">Stažení ukázky</span><span class="sxs-lookup"><span data-stu-id="59be6-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/SchemaImporterExtension.zip.exe)  
  
 <span data-ttu-id="59be6-104">Tento příklad znázorňuje vlastní <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> , který umožňuje přesné řízení generování kódu, když je importován schématu XML.</span><span class="sxs-lookup"><span data-stu-id="59be6-104">This sample demonstrates a custom <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> that allows fine control over code generation when an XML schema is imported.</span></span> <span data-ttu-id="59be6-105">Aplikace ukazuje, jak vytvářet, registrace a vyvolání tohoto rozšíření.</span><span class="sxs-lookup"><span data-stu-id="59be6-105">The application shows how to build, register and invoke this extension.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="59be6-106">K vytvoření vzorku pomocí příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="59be6-106">To build the sample using the command prompt</span></span>  
  
1.  <span data-ttu-id="59be6-107">Otevřete okno příkazového řádku a přejděte do jednoho podadresáře konkrétní jazyk pro vzorku.</span><span class="sxs-lookup"><span data-stu-id="59be6-107">Open a Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="59be6-108">Typ **msbuild.exe OrderSchemaImporterExtension.sln** na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="59be6-108">Type **msbuild.exe OrderSchemaImporterExtension.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="59be6-109">K vytvoření vzorku pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="59be6-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="59be6-110">Otevřít [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] a přejděte do jednoho podadresáře konkrétní jazyk pro vzorku.</span><span class="sxs-lookup"><span data-stu-id="59be6-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="59be6-111">Poklepejte na ikonu OrderSchemaImporterExtension.sln k otevření souboru v sadě Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="59be6-111">Double-click the icon for OrderSchemaImporterExtension.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="59be6-112">Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.</span><span class="sxs-lookup"><span data-stu-id="59be6-112">On the **Build** menu, click **Build Solution**.</span></span>  
  
 <span data-ttu-id="59be6-113">Aplikace bude vytvořen v adresáři \bin nebo \bin\Debug výchozí.</span><span class="sxs-lookup"><span data-stu-id="59be6-113">The application will be built in the default \bin or \bin\Debug directory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="59be6-114">Chcete-li spustit ukázku</span><span class="sxs-lookup"><span data-stu-id="59be6-114">To run the sample</span></span>  
  
1.  <span data-ttu-id="59be6-115">Přejděte do adresáře, který obsahuje novou spustitelný soubor, pomocí příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="59be6-115">Navigate to the directory containing the new executable, using the command prompt.</span></span>  
  
2.  <span data-ttu-id="59be6-116">Typ **[název souboru exe]** na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="59be6-116">Type **[exe name]** at the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59be6-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="59be6-117">Remarks</span></span>  
 <span data-ttu-id="59be6-118">Další informace o vytváření binární ukázky a registraci kroky naleznete v tématu komentáře v souborech zdrojového kódu a build.proj.</span><span class="sxs-lookup"><span data-stu-id="59be6-118">For more information about sample binary creation and registration steps, see the comments in the source code and build.proj files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59be6-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="59be6-119">See Also</span></span>  
 <xref:System.CodeDom.CodeCompileUnit>  
 <xref:System.CodeDom.CodeNamespace>  
 <xref:System.CodeDom.CodeNamespaceImport>  
 <xref:Microsoft.CSharp.CSharpCodeProvider>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>  
 <xref:System.CodeDom>  
 <xref:System.CodeDom.Compiler>  
 <xref:System.Web.Services.Description>  
 <xref:System.Web.Services.Discovery>  
 <xref:System.Xml.Serialization>  
 <xref:System.Uri>  
 <xref:Microsoft.VisualBasic.VBCodeProvider>  
 <xref:System.Web.Services.Description.WebReference>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>