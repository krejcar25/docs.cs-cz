---
title: "Nepodporované funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6dd8ccebd278fdc36c536c49f7f1d4262b2de8c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="unsupported-functionality"></a><span data-ttu-id="4ead0-102">Nepodporované funkce</span><span class="sxs-lookup"><span data-stu-id="4ead0-102">Unsupported Functionality</span></span>
<span data-ttu-id="4ead0-103">V technologii LINQ to SQL nelze tyto funkce SQL uvádět na překlad existující common language runtime (CLR) a vytvoří rozhraní .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4ead0-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="4ead0-104">I když `LIKE` nepodporuje prostřednictvím přímé překlad podobné funkce v existuje <xref:System.Data.Linq.SqlClient.SqlMethods> třídy.</span><span class="sxs-lookup"><span data-stu-id="4ead0-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="4ead0-105">Další informace naleznete v tématu <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ead0-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="4ead0-106">Technologie LINQ to SQL má omezenou podporu pro `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="4ead0-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="4ead0-107">Podobné funkce v existuje <xref:System.Data.Linq.SqlClient.SqlMethods> třídy.</span><span class="sxs-lookup"><span data-stu-id="4ead0-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="4ead0-108">Technologie LINQ to SQL má omezenou podporu pro `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="4ead0-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="4ead0-109">Další informace najdete v tématu [System.Math metody](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4ead0-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ead0-110">Viz také</span><span class="sxs-lookup"><span data-stu-id="4ead0-110">See Also</span></span>  
 [<span data-ttu-id="4ead0-111">Datové typy a funkce</span><span class="sxs-lookup"><span data-stu-id="4ead0-111">Data Types and Functions</span></span>](data-types-and-functions.md)