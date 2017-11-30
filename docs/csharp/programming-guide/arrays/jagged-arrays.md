---
title: "Vícenásobná pole (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f74eaf5334e8e2198f7a058717a4eb2ff0c1e775
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="0e355-102">Vícenásobná pole (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="0e355-102">Jagged Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="0e355-103">Vícenásobné pole je pole, jehož prvky jsou pole.</span><span class="sxs-lookup"><span data-stu-id="0e355-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="0e355-104">Prvky Vícenásobná pole může být různými dimenzemi a velikosti.</span><span class="sxs-lookup"><span data-stu-id="0e355-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="0e355-105">Vícenásobná pole se někdy označuje jako "pole polí."</span><span class="sxs-lookup"><span data-stu-id="0e355-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="0e355-106">Následující příklady ukazují, jak deklarovat, inicializovat a přístup Vícenásobná pole.</span><span class="sxs-lookup"><span data-stu-id="0e355-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="0e355-107">Toto je deklaraci jednorozměrná pole, která má tři prvky, z nichž každý se jednorozměrná pole celých čísel:</span><span class="sxs-lookup"><span data-stu-id="0e355-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 [!code-csharp[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 <span data-ttu-id="0e355-108">Než budete moci použít `jaggedArray`, jeho elementy musí být inicializován.</span><span class="sxs-lookup"><span data-stu-id="0e355-108">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="0e355-109">Můžete inicializovat elementy takto:</span><span class="sxs-lookup"><span data-stu-id="0e355-109">You can initialize the elements like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 <span data-ttu-id="0e355-110">Jednotlivých prvků je jednorozměrná pole celých čísel.</span><span class="sxs-lookup"><span data-stu-id="0e355-110">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="0e355-111">Je první prvek pole 5 celých čísel, druhý je pole 4 celých čísel a třetí je pole 2 celých čísel.</span><span class="sxs-lookup"><span data-stu-id="0e355-111">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="0e355-112">Je také možné použít k vyplnění pole prvky hodnotami inicializátory, v takovém případě nepotřebujete velikost pole.</span><span class="sxs-lookup"><span data-stu-id="0e355-112">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="0e355-113">Příklad:</span><span class="sxs-lookup"><span data-stu-id="0e355-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 <span data-ttu-id="0e355-114">Můžete také inicializovat pole po deklaraci takto:</span><span class="sxs-lookup"><span data-stu-id="0e355-114">You can also initialize the array upon declaration like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 <span data-ttu-id="0e355-115">Můžete použít následující sdružená formuláře.</span><span class="sxs-lookup"><span data-stu-id="0e355-115">You can use the following shorthand form.</span></span> <span data-ttu-id="0e355-116">Všimněte si, že nemůžete vynechat `new` operátor z elementů inicializace protože neexistuje žádný výchozí inicializace pro elementy:</span><span class="sxs-lookup"><span data-stu-id="0e355-116">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 [!code-csharp[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 <span data-ttu-id="0e355-117">Vícenásobná pole je pole polí, a proto jeho prvky jsou odkazové typy a jsou inicializována tak, aby `null`.</span><span class="sxs-lookup"><span data-stu-id="0e355-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="0e355-118">Elementy jednotlivá pole jako těchto příkladech se můžete dostat:</span><span class="sxs-lookup"><span data-stu-id="0e355-118">You can access individual array elements like these examples:</span></span>  
  
 [!code-csharp[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 <span data-ttu-id="0e355-119">Je možné kombinovat vícenásobná a multidimenzionální pole.</span><span class="sxs-lookup"><span data-stu-id="0e355-119">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="0e355-120">Zde je deklarace a inicializace jednorozměrná Vícenásobná pole, která obsahuje tři prvky dvourozměrná pole různých velikostí.</span><span class="sxs-lookup"><span data-stu-id="0e355-120">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="0e355-121">Další informace o dvourozměrná polích najdete v tématu [vícerozměrná pole](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="0e355-121">For more information about two-dimensional arrays, see [Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span></span>  
  
 [!code-csharp[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 <span data-ttu-id="0e355-122">Jak je znázorněno v tomto příkladu se zobrazí hodnota elementu dostanete jednotlivé elementy `[1,0]` první pole (hodnota `5`):</span><span class="sxs-lookup"><span data-stu-id="0e355-122">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 [!code-csharp[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 <span data-ttu-id="0e355-123">Metoda `Length` vrátí počet polí obsažených v Vícenásobná pole.</span><span class="sxs-lookup"><span data-stu-id="0e355-123">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="0e355-124">Například, za předpokladu, že deklarujete předchozí pole, tento řádek:</span><span class="sxs-lookup"><span data-stu-id="0e355-124">For example, assuming you have declared the previous array, this line:</span></span>  
  
 [!code-csharp[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 <span data-ttu-id="0e355-125">Vrátí hodnotu 3.</span><span class="sxs-lookup"><span data-stu-id="0e355-125">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e355-126">Příklad</span><span class="sxs-lookup"><span data-stu-id="0e355-126">Example</span></span>  
 <span data-ttu-id="0e355-127">Tento příklad vytvoří pole jehož elementy jsou sami pole.</span><span class="sxs-lookup"><span data-stu-id="0e355-127">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="0e355-128">Každé z nich prvků pole má různou velikost.</span><span class="sxs-lookup"><span data-stu-id="0e355-128">Each one of the array elements has a different size.</span></span>  
  
 [!code-csharp[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0e355-129">Viz také</span><span class="sxs-lookup"><span data-stu-id="0e355-129">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="0e355-130">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="0e355-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0e355-131">Pole</span><span class="sxs-lookup"><span data-stu-id="0e355-131">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="0e355-132">Jednorozměrná pole</span><span class="sxs-lookup"><span data-stu-id="0e355-132">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="0e355-133">Vícerozměrná pole</span><span class="sxs-lookup"><span data-stu-id="0e355-133">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)