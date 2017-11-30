---
title: "Typy metod manipulace s řetězci v jazyce Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b437be4a6f4a0cc9d5a4d21291a80c9cb8fffcd3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="4307d-102">Typy metod manipulace s řetězci v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4307d-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="4307d-103">K analýze a manipulaci s vaší řetězce několika různými způsoby.</span><span class="sxs-lookup"><span data-stu-id="4307d-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="4307d-104">Některé metody jsou součástí [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] jazyk a jiné jsou vyplývajících z `String` třídy.</span><span class="sxs-lookup"><span data-stu-id="4307d-104">Some of the methods are a part of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="4307d-105">Jazyk Visual Basic a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4307d-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="4307d-106">metody se používají jako vyplývajících funkce jazyka.</span><span class="sxs-lookup"><span data-stu-id="4307d-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="4307d-107">Mohou být použity bez kvalifikace ve vašem kódu.</span><span class="sxs-lookup"><span data-stu-id="4307d-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="4307d-108">Následující příklad ukazuje typické použití [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zacházení s řetězci příkaz:</span><span class="sxs-lookup"><span data-stu-id="4307d-108">The following example shows typical use of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="4307d-109">V tomto příkladu `Mid` funkce přímé operaci provádí `aString` a přiřadí hodnota, která má `bString`.</span><span class="sxs-lookup"><span data-stu-id="4307d-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="4307d-110">Seznam metod manipulace s řetězci jazyka Visual Basic, naleznete v části [souhrn manipulace s řetězci](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="4307d-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="4307d-111">Sdílené metody a Instance metody</span><span class="sxs-lookup"><span data-stu-id="4307d-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="4307d-112">Můžete také upravit řetězců pomocí metod `String` třídy.</span><span class="sxs-lookup"><span data-stu-id="4307d-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="4307d-113">Existují dva typy metod v `String`: *sdílené* metody a *instance* metody.</span><span class="sxs-lookup"><span data-stu-id="4307d-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="4307d-114">Sdílené metody</span><span class="sxs-lookup"><span data-stu-id="4307d-114">Shared Methods</span></span>  
 <span data-ttu-id="4307d-115">Sdílené metody je metoda, která byl vyvolán `String` třídy sám a nevyžaduje instance této třídy pro práci.</span><span class="sxs-lookup"><span data-stu-id="4307d-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="4307d-116">Tyto metody mohou být kvalifikovaný pomocí názvu třídy (`String`) a nikoli s instancí `String` třídy.</span><span class="sxs-lookup"><span data-stu-id="4307d-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="4307d-117">Příklad:</span><span class="sxs-lookup"><span data-stu-id="4307d-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="4307d-118">V předchozím příkladu <xref:System.String.Copy%2A?displayProperty=nameWithType> metoda je statickou metodu, který pracuje na výrazu ji dostane a přiřadí výsledná hodnota k `bString`.</span><span class="sxs-lookup"><span data-stu-id="4307d-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="4307d-119">Instance metody</span><span class="sxs-lookup"><span data-stu-id="4307d-119">Instance Methods</span></span>  
 <span data-ttu-id="4307d-120">Instance metody naopak kmen z konkrétní instanci `String` a musí být kvalifikovaný pomocí názvu instance.</span><span class="sxs-lookup"><span data-stu-id="4307d-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="4307d-121">Příklad:</span><span class="sxs-lookup"><span data-stu-id="4307d-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="4307d-122">V tomto příkladu <xref:System.String.Substring%2A?displayProperty=nameWithType> je metoda metodou instance `String` (tedy `aString`).</span><span class="sxs-lookup"><span data-stu-id="4307d-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="4307d-123">Provádí operace na `aString` a přiřadí tuto hodnotu na `bString`.</span><span class="sxs-lookup"><span data-stu-id="4307d-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="4307d-124">Další informace najdete v dokumentaci pro <xref:System.String> třídy.</span><span class="sxs-lookup"><span data-stu-id="4307d-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4307d-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="4307d-125">See Also</span></span>  
 [<span data-ttu-id="4307d-126">Představení řetězců v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4307d-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)