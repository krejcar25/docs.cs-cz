---
title: "Postupy: Čtení a zápis do nově vytvořeného datového souboru"
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
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b547f2c85495a497e5fc384f9a2ea44de7bf861c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="832d5-102">Postupy: Čtení a zápis do nově vytvořeného datového souboru</span><span class="sxs-lookup"><span data-stu-id="832d5-102">How to: Read and Write to a Newly Created Data File</span></span>
<span data-ttu-id="832d5-103">Třídy <xref:System.IO.BinaryWriter> a <xref:System.IO.BinaryReader?displayProperty=nameWithType> se používají spíše pro zápis a čtení dat než řetězců znaků.</span><span class="sxs-lookup"><span data-stu-id="832d5-103">The <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data rather than character strings.</span></span> <span data-ttu-id="832d5-104">Následující příklad znázorňuje, jakým způsobem lze zapisovat a číst data z nového prázdného datového proudu souboru nazvaného `Test.data`.</span><span class="sxs-lookup"><span data-stu-id="832d5-104">The following example demonstrates how to write data to, and read data from, a new, empty file stream called `Test.data`.</span></span> <span data-ttu-id="832d5-105">Po vytvoření datového souboru v aktuálním adresáři jsou vytvořeny přidružené objekty <xref:System.IO.BinaryWriter> a <xref:System.IO.BinaryReader> a objekt <xref:System.IO.BinaryWriter> se používá k zápisu celých čísel 0 až 10 do `Test.data`, čímž je ukazatel souboru ponechán na konci souboru.</span><span class="sxs-lookup"><span data-stu-id="832d5-105">After creating the data file in the current directory, the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects are created, and the <xref:System.IO.BinaryWriter> object is used to write the integers 0 through 10 to `Test.data`, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="832d5-106">Po nastavení ukazatele souboru zpět na začátek přečte objekt <xref:System.IO.BinaryReader> zadaný obsah.</span><span class="sxs-lookup"><span data-stu-id="832d5-106">After setting the file pointer back to the origin, the <xref:System.IO.BinaryReader> object reads out the specified content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="832d5-107">Příklad</span><span class="sxs-lookup"><span data-stu-id="832d5-107">Example</span></span>  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a><span data-ttu-id="832d5-108">Robustní programování</span><span class="sxs-lookup"><span data-stu-id="832d5-108">Robust Programming</span></span>  
 <span data-ttu-id="832d5-109">Pokud data `Test.data` již v aktuálním adresáři existují, je vyvolána výjimka <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="832d5-109">If `Test.data` already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="832d5-110">Chcete-li vytvořit nový soubor bez vyvolání výjimky, je třeba při inicializaci datového proudu souboru použít vždy volbu režimu souboru <xref:System.IO.FileMode.Create?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="832d5-110">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> when you initialize the file stream to always create a new file without throwing an  exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832d5-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="832d5-111">See Also</span></span>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryWriter>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
 <xref:System.IO.SeekOrigin>  
 [<span data-ttu-id="832d5-112">Postupy: vytvoření výčtu adresářů a souborů</span><span class="sxs-lookup"><span data-stu-id="832d5-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="832d5-113">Postupy: otevření a připojení k souboru protokolu</span><span class="sxs-lookup"><span data-stu-id="832d5-113">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="832d5-114">Postupy: čtení textu ze souboru</span><span class="sxs-lookup"><span data-stu-id="832d5-114">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="832d5-115">Postupy: zápis textu do souboru</span><span class="sxs-lookup"><span data-stu-id="832d5-115">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="832d5-116">Postupy: čtení znaků z řetězce</span><span class="sxs-lookup"><span data-stu-id="832d5-116">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="832d5-117">Postupy: zápis znaků do řetězce</span><span class="sxs-lookup"><span data-stu-id="832d5-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="832d5-118">Souborová služba a datový proud I-O</span><span class="sxs-lookup"><span data-stu-id="832d5-118">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)