---
title: "Postupy: Explicitní generování výjimek"
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
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c3fce332263dac3f9906d33fe3bd2590050b86f8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="3c9a3-102">Postupy: explicitní generování výjimek</span><span class="sxs-lookup"><span data-stu-id="3c9a3-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="3c9a3-103">Můžete explicitně vyvolat výjimku pomocí `throw` příkaz.</span><span class="sxs-lookup"><span data-stu-id="3c9a3-103">You can explicitly throw an exception using the `throw` statement.</span></span> <span data-ttu-id="3c9a3-104">Můžete také vyvolat Zachycenou výjimku znovu s použitím `throw` příkaz.</span><span class="sxs-lookup"><span data-stu-id="3c9a3-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="3c9a3-105">Je dobrým zvykem přidat informace o výjimku, která je znovu vyvolána při ladění poskytnout další informace.</span><span class="sxs-lookup"><span data-stu-id="3c9a3-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="3c9a3-106">Následující příklad kódu používá `try` / `catch` blok k zachycení možné <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="3c9a3-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="3c9a3-107">Následující `try` blok je `catch` blok, který zachytí <xref:System.IO.FileNotFoundException> a zapíše zprávu do konzoly, pokud nebyl nalezen datový soubor.</span><span class="sxs-lookup"><span data-stu-id="3c9a3-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="3c9a3-108">Další je `throw` příkaz, který vyvolá novou <xref:System.IO.FileNotFoundException> a přidá textových informací k výjimce.</span><span class="sxs-lookup"><span data-stu-id="3c9a3-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="3c9a3-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="3c9a3-109">See Also</span></span>  
[<span data-ttu-id="3c9a3-110">Výjimky</span><span class="sxs-lookup"><span data-stu-id="3c9a3-110">Exceptions</span></span>](index.md)