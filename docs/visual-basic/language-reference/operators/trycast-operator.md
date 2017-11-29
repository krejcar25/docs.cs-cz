---
title: "TryCast – operátor (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords: TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6be11b49eb3b9d98e3bf147e9b1026d4ffc860c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="52458-102">TryCast – operátor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52458-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="52458-103">Představuje operaci převodu typu, který nevyvolá výjimku.</span><span class="sxs-lookup"><span data-stu-id="52458-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52458-104">Poznámky</span><span class="sxs-lookup"><span data-stu-id="52458-104">Remarks</span></span>  
 <span data-ttu-id="52458-105">Pokud se nezdaří pokus o převodu, `CType` a `DirectCast` obě throw <xref:System.InvalidCastException> chyby.</span><span class="sxs-lookup"><span data-stu-id="52458-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="52458-106">To může nepříznivě ovlivnit výkon aplikace.</span><span class="sxs-lookup"><span data-stu-id="52458-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="52458-107">`TryCast`Vrátí [nic](../../../visual-basic/language-reference/nothing.md)tak, aby místo nutnosti zpracování možnou výjimkou, potřebovat pouze zkušební vrácených výsledků proti `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="52458-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="52458-108">Můžete použít `TryCast` – klíčové slovo stejným způsobem jako použijete [CType – funkce](../../../visual-basic/language-reference/functions/ctype-function.md) a [DirectCast – operátor](../../../visual-basic/language-reference/operators/directcast-operator.md) – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="52458-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="52458-109">Můžete zadat jako první argument a zadejte ji do převést jako druhý argument výrazu.</span><span class="sxs-lookup"><span data-stu-id="52458-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="52458-110">`TryCast`funguje pouze na odkazových typech, jako jsou třídy a rozhraní.</span><span class="sxs-lookup"><span data-stu-id="52458-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="52458-111">To vyžaduje relaci dědičnosti nebo implementace mezi těmito dvěma typy.</span><span class="sxs-lookup"><span data-stu-id="52458-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="52458-112">To znamená, že jeden typ musí dědit z nebo implementovat dalších.</span><span class="sxs-lookup"><span data-stu-id="52458-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="52458-113">Chyby a selhání</span><span class="sxs-lookup"><span data-stu-id="52458-113">Errors and Failures</span></span>  
 <span data-ttu-id="52458-114">`TryCast`Chyba kompilátoru generuje, pokud zjistí, že neexistuje žádný vztah dědičnosti nebo implementace.</span><span class="sxs-lookup"><span data-stu-id="52458-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="52458-115">Ale nedostatek Chyba kompilátoru nezaručuje úspěšné převod.</span><span class="sxs-lookup"><span data-stu-id="52458-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="52458-116">Pokud je zužující převod požadované, pravděpodobně nezdaří za běhu.</span><span class="sxs-lookup"><span data-stu-id="52458-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="52458-117">V takovém případě `TryCast` vrátí [nic](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="52458-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="52458-118">Klíčová slova převodu</span><span class="sxs-lookup"><span data-stu-id="52458-118">Conversion Keywords</span></span>  
 <span data-ttu-id="52458-119">Porovnání klíčová slova převodu typu je následující.</span><span class="sxs-lookup"><span data-stu-id="52458-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="52458-120">– Klíčové slovo</span><span class="sxs-lookup"><span data-stu-id="52458-120">Keyword</span></span>|<span data-ttu-id="52458-121">Typy dat</span><span class="sxs-lookup"><span data-stu-id="52458-121">Data types</span></span>|<span data-ttu-id="52458-122">Argument relace</span><span class="sxs-lookup"><span data-stu-id="52458-122">Argument relationship</span></span>|<span data-ttu-id="52458-123">Běhové chyby</span><span class="sxs-lookup"><span data-stu-id="52458-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="52458-124">CType – funkce</span><span class="sxs-lookup"><span data-stu-id="52458-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="52458-125">Žádné datové typy</span><span class="sxs-lookup"><span data-stu-id="52458-125">Any data types</span></span>|<span data-ttu-id="52458-126">Je nutné definovat rozšiřující nebo zužující převod mezi dvěma datovými typy</span><span class="sxs-lookup"><span data-stu-id="52458-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="52458-127">Vyvolá<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="52458-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="52458-128">DirectCast – operátor</span><span class="sxs-lookup"><span data-stu-id="52458-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="52458-129">Žádné datové typy</span><span class="sxs-lookup"><span data-stu-id="52458-129">Any data types</span></span>|<span data-ttu-id="52458-130">Jeden typ musí dědit z nebo provádět další typ.</span><span class="sxs-lookup"><span data-stu-id="52458-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="52458-131">Vyvolá<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="52458-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="52458-132">Odkazové typy pouze</span><span class="sxs-lookup"><span data-stu-id="52458-132">Reference types only</span></span>|<span data-ttu-id="52458-133">Jeden typ musí dědit z nebo provádět další typ.</span><span class="sxs-lookup"><span data-stu-id="52458-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="52458-134">Vrátí [nic](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="52458-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="52458-135">Příklad</span><span class="sxs-lookup"><span data-stu-id="52458-135">Example</span></span>  
 <span data-ttu-id="52458-136">Následující příklad ukazuje, jak používat `TryCast`.</span><span class="sxs-lookup"><span data-stu-id="52458-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="52458-137">Viz také</span><span class="sxs-lookup"><span data-stu-id="52458-137">See Also</span></span>  
 [<span data-ttu-id="52458-138">Rozšíření a zúžení převodů</span><span class="sxs-lookup"><span data-stu-id="52458-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="52458-139">Implicitní a explicitní převody</span><span class="sxs-lookup"><span data-stu-id="52458-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)