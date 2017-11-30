---
title: "Postupy: Vytváření souborů nebo složek (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f7eb2c6386a8433c025a9f2abea4b03f6ab271d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="ad216-102">Postupy: Vytváření souborů nebo složek (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="ad216-102">How to: Create a File or Folder (C# Programming Guide)</span></span>
<span data-ttu-id="ad216-103">Můžete prostřednictvím kódu programu vytvořte složku v počítači, vytvořit podsložky, vytvořte soubor v podsložce a zapisovat data do souboru.</span><span class="sxs-lookup"><span data-stu-id="ad216-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad216-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="ad216-104">Example</span></span>  
 [!code-csharp[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 <span data-ttu-id="ad216-105">Pokud daná složka již existuje, <xref:System.IO.Directory.CreateDirectory%2A> nemá, je vyvolána nic a žádná výjimka.</span><span class="sxs-lookup"><span data-stu-id="ad216-105">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="ad216-106">Ale <xref:System.IO.File.Create%2A?displayProperty=nameWithType> nahradí existující soubor nový soubor.</span><span class="sxs-lookup"><span data-stu-id="ad216-106">However, <xref:System.IO.File.Create%2A?displayProperty=nameWithType> replaces an existing file with a new file.</span></span> <span data-ttu-id="ad216-107">V příkladu se používá `if` - `else` příkaz zabránit nahrazují existující soubor.</span><span class="sxs-lookup"><span data-stu-id="ad216-107">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="ad216-108">Tím, že provedete následující změny v příkladu, můžete zadat různé výsledky podle toho, zda je soubor s určitým názvem již existuje.</span><span class="sxs-lookup"><span data-stu-id="ad216-108">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="ad216-109">Pokud takový soubor neexistuje, kód vytvoří.</span><span class="sxs-lookup"><span data-stu-id="ad216-109">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="ad216-110">Pokud takový soubor neexistuje, kód připojí data k souboru.</span><span class="sxs-lookup"><span data-stu-id="ad216-110">If such a file exists, the code appends data to that file.</span></span>  
  
-   <span data-ttu-id="ad216-111">Zadejte název souboru bez náhodné.</span><span class="sxs-lookup"><span data-stu-id="ad216-111">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
-   <span data-ttu-id="ad216-112">Nahraďte `if` - `else` příkaz s `using` příkaz v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="ad216-112">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="ad216-113">V příkladu spustit několikrát ověření dat se přidá do souboru pokaždé, když.</span><span class="sxs-lookup"><span data-stu-id="ad216-113">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="ad216-114">Další informace `FileMode` hodnoty, které můžete vyzkoušet, najdete v části <xref:System.IO.FileMode>.</span><span class="sxs-lookup"><span data-stu-id="ad216-114">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="ad216-115">Následující podmínky mohou způsobit výjimku:</span><span class="sxs-lookup"><span data-stu-id="ad216-115">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="ad216-116">Název složky není správně vytvořen.</span><span class="sxs-lookup"><span data-stu-id="ad216-116">The folder name is malformed.</span></span> <span data-ttu-id="ad216-117">Například obsahuje neplatné znaky nebo je pouze mezera (<xref:System.ArgumentException> třídy).</span><span class="sxs-lookup"><span data-stu-id="ad216-117">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="ad216-118">Použití <xref:System.IO.Path> třídy za účelem vytvoření názvy platnou cestu.</span><span class="sxs-lookup"><span data-stu-id="ad216-118">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
-   <span data-ttu-id="ad216-119">Nadřazená složka vytvořit složku je jen pro čtení (<xref:System.IO.IOException> třídy).</span><span class="sxs-lookup"><span data-stu-id="ad216-119">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="ad216-120">Je název složky `null` (<xref:System.ArgumentNullException> třídy).</span><span class="sxs-lookup"><span data-stu-id="ad216-120">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="ad216-121">Název složky je příliš dlouhý (<xref:System.IO.PathTooLongException> třídy).</span><span class="sxs-lookup"><span data-stu-id="ad216-121">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="ad216-122">Pouze dvojtečku, je název složky ":" (<xref:System.IO.PathTooLongException> třídy).</span><span class="sxs-lookup"><span data-stu-id="ad216-122">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ad216-123">Zabezpečení rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ad216-123">.NET Framework Security</span></span>  
 <span data-ttu-id="ad216-124">Instance <xref:System.Security.SecurityException> třída může být vyvolána v situacích s částečným vztahem důvěryhodnosti.</span><span class="sxs-lookup"><span data-stu-id="ad216-124">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="ad216-125">Pokud nemáte oprávnění vytvořit složku, v příkladu vyvolá instanci <xref:System.UnauthorizedAccessException> třídy.</span><span class="sxs-lookup"><span data-stu-id="ad216-125">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad216-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="ad216-126">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="ad216-127">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="ad216-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ad216-128">Systém souborů a registr (C# Průvodce programováním)</span><span class="sxs-lookup"><span data-stu-id="ad216-128">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)