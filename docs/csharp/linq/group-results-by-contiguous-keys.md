---
title: "Seskupení výsledků podle sousedních klíčů"
description: "Jak seskupení výsledků podle sousedních klíčů."
keywords: "Rozhraní .NET, rozhraní .NET core, C#"
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: cdd06a6fad037291bbc5aa011b47bb668fa2f062
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="6af37-104">Seskupení výsledků podle sousedních klíčů</span><span class="sxs-lookup"><span data-stu-id="6af37-104">Group results by contiguous keys</span></span>

<span data-ttu-id="6af37-105">Následující příklad ukazuje, jak k seskupení prvků do bloků, které představují dílčích sekvencí sousedních klíčů.</span><span class="sxs-lookup"><span data-stu-id="6af37-105">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="6af37-106">Předpokládejme například, že budete mít k následujícímu pořadí páry klíč hodnota:</span><span class="sxs-lookup"><span data-stu-id="6af37-106">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="6af37-107">Key</span><span class="sxs-lookup"><span data-stu-id="6af37-107">Key</span></span>|<span data-ttu-id="6af37-108">Hodnota</span><span class="sxs-lookup"><span data-stu-id="6af37-108">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="6af37-109">OBJEKT</span><span class="sxs-lookup"><span data-stu-id="6af37-109">A</span></span>|<span data-ttu-id="6af37-110">Jsme</span><span class="sxs-lookup"><span data-stu-id="6af37-110">We</span></span>|  
|<span data-ttu-id="6af37-111">OBJEKT</span><span class="sxs-lookup"><span data-stu-id="6af37-111">A</span></span>|<span data-ttu-id="6af37-112">Vezměte v úvahu</span><span class="sxs-lookup"><span data-stu-id="6af37-112">think</span></span>|  
|<span data-ttu-id="6af37-113">OBJEKT</span><span class="sxs-lookup"><span data-stu-id="6af37-113">A</span></span>|<span data-ttu-id="6af37-114">který</span><span class="sxs-lookup"><span data-stu-id="6af37-114">that</span></span>|  
|<span data-ttu-id="6af37-115">B</span><span class="sxs-lookup"><span data-stu-id="6af37-115">B</span></span>|<span data-ttu-id="6af37-116">LINQ</span><span class="sxs-lookup"><span data-stu-id="6af37-116">Linq</span></span>|  
|<span data-ttu-id="6af37-117">C</span><span class="sxs-lookup"><span data-stu-id="6af37-117">C</span></span>|<span data-ttu-id="6af37-118">is</span><span class="sxs-lookup"><span data-stu-id="6af37-118">is</span></span>|  
|<span data-ttu-id="6af37-119">OBJEKT</span><span class="sxs-lookup"><span data-stu-id="6af37-119">A</span></span>|<span data-ttu-id="6af37-120">Vážně</span><span class="sxs-lookup"><span data-stu-id="6af37-120">really</span></span>|  
|<span data-ttu-id="6af37-121">B</span><span class="sxs-lookup"><span data-stu-id="6af37-121">B</span></span>|<span data-ttu-id="6af37-122">Cool</span><span class="sxs-lookup"><span data-stu-id="6af37-122">cool</span></span>|  
|<span data-ttu-id="6af37-123">B</span><span class="sxs-lookup"><span data-stu-id="6af37-123">B</span></span>|<span data-ttu-id="6af37-124">!</span><span class="sxs-lookup"><span data-stu-id="6af37-124">!</span></span>|  
  
 <span data-ttu-id="6af37-125">Tyto skupiny se vytvoří v tomto pořadí:</span><span class="sxs-lookup"><span data-stu-id="6af37-125">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="6af37-126">Myslíme, který</span><span class="sxs-lookup"><span data-stu-id="6af37-126">We, think, that</span></span>  
  
2.  <span data-ttu-id="6af37-127">LINQ</span><span class="sxs-lookup"><span data-stu-id="6af37-127">Linq</span></span>  
  
3.  <span data-ttu-id="6af37-128">is</span><span class="sxs-lookup"><span data-stu-id="6af37-128">is</span></span>  
  
4.  <span data-ttu-id="6af37-129">Vážně</span><span class="sxs-lookup"><span data-stu-id="6af37-129">really</span></span>  
  
5.  <span data-ttu-id="6af37-130">nástrojů!</span><span class="sxs-lookup"><span data-stu-id="6af37-130">cool, !</span></span>  
  
 <span data-ttu-id="6af37-131">Řešení je implementovaný jako metody rozšíření, který je bezpečný pro přístup z více vláken a která vrací své výsledky streamování způsobem.</span><span class="sxs-lookup"><span data-stu-id="6af37-131">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="6af37-132">Jinými slovy jeho skupiny vyvolá při jejich přesunu prostřednictvím zdrojové sekvence.</span><span class="sxs-lookup"><span data-stu-id="6af37-132">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="6af37-133">Na rozdíl od `group` nebo `orderby` operátory, ho můžete začít vracet skupiny volajícímu před všechny pořadí byl načten.</span><span class="sxs-lookup"><span data-stu-id="6af37-133">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="6af37-134">Zabezpečení vlákna dosahuje tím, že kopii každého bloku nebo skupiny je vstupní zdroj pořadí, jak je popsáno v komentáře zdrojového kódu.</span><span class="sxs-lookup"><span data-stu-id="6af37-134">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="6af37-135">Pokud zdrojové sekvence velké posloupnost souvislý položek, může vyvolat modul common language runtime <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="6af37-135">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6af37-136">Příklad</span><span class="sxs-lookup"><span data-stu-id="6af37-136">Example</span></span>  
 <span data-ttu-id="6af37-137">Následující příklad ukazuje metodu rozšíření a kód klienta, která jej používá.</span><span class="sxs-lookup"><span data-stu-id="6af37-137">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 <span data-ttu-id="6af37-138">Chcete-li použít metodu rozšíření v projektu, zkopírujte `MyExtensions` statická třída pro nové nebo existující zdrojový kód soubor a pokud je vyžadována, přidejte `using` direktivy pro obor názvů, kde se nachází.</span><span class="sxs-lookup"><span data-stu-id="6af37-138">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af37-139">Viz také</span><span class="sxs-lookup"><span data-stu-id="6af37-139">See also</span></span>  
 [<span data-ttu-id="6af37-140">LINQ – výrazy dotazů</span><span class="sxs-lookup"><span data-stu-id="6af37-140">LINQ Query Expressions</span></span>](index.md)  
 