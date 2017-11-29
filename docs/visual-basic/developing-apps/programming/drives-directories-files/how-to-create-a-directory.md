---
title: "Postupy: Vytvoření adresáře v jazyce Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2e4cd94113d77b2f4ff8127c80174107966ef360
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="b997d-102">Postupy: Vytvoření adresáře v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b997d-102">How to: Create a Directory in Visual Basic</span></span>
<span data-ttu-id="b997d-103">Použití `CreateDirectory` metodu `My.Computer.FileSystem` objekt k vytvoření adresáře.</span><span class="sxs-lookup"><span data-stu-id="b997d-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="b997d-104">Pokud adresář již existuje, je vyvolána žádná výjimka.</span><span class="sxs-lookup"><span data-stu-id="b997d-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="b997d-105">K vytvoření adresáře</span><span class="sxs-lookup"><span data-stu-id="b997d-105">To create a directory</span></span>  
  
-   <span data-ttu-id="b997d-106">Použití `CreateDirectory` metoda zadáním úplnou cestu k umístění, kde se vytvořit adresář.</span><span class="sxs-lookup"><span data-stu-id="b997d-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="b997d-107">Tento příklad vytvoří adresář `NewDirectory` v `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="b997d-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b997d-108">Robustní programování</span><span class="sxs-lookup"><span data-stu-id="b997d-108">Robust Programming</span></span>  
 <span data-ttu-id="b997d-109">Následující podmínky mohou způsobit výjimku:</span><span class="sxs-lookup"><span data-stu-id="b997d-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b997d-110">Název adresáře je poškozený.</span><span class="sxs-lookup"><span data-stu-id="b997d-110">The directory name is malformed.</span></span> <span data-ttu-id="b997d-111">Například obsahuje neplatné znaky nebo je pouze mezera (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b997d-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="b997d-112">Nadřazeném adresáři vytvořen adresář je jen pro čtení (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b997d-112">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="b997d-113">Název adresáře je `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="b997d-113">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="b997d-114">Název adresáře je příliš dlouhý (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b997d-114">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="b997d-115">Název adresáře je dvojtečkou ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="b997d-115">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="b997d-116">Uživatel nemá oprávnění vytvořit adresář (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="b997d-116">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="b997d-117">Uživatel nemá oprávnění v situaci, částečným vztahem důvěryhodnosti (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="b997d-117">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b997d-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="b997d-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>  
 [<span data-ttu-id="b997d-119">Vytváření, odstraňování a přesouvání souborů a adresářů</span><span class="sxs-lookup"><span data-stu-id="b997d-119">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)