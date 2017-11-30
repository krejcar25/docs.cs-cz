---
title: "const (Referenční dokumentace jazyka C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords: const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f54b686b170622ca1ead736a9f614c9bbef52dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="const-c-reference"></a><span data-ttu-id="0351e-102">const (Referenční dokumentace jazyka C#)</span><span class="sxs-lookup"><span data-stu-id="0351e-102">const (C# Reference)</span></span>
<span data-ttu-id="0351e-103">Můžete použít `const` – klíčové slovo deklarace konstantní pole nebo konstantní místní.</span><span class="sxs-lookup"><span data-stu-id="0351e-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="0351e-104">Konstantní pole a místní hodnoty nejsou proměnné a nejde ho upravit.</span><span class="sxs-lookup"><span data-stu-id="0351e-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="0351e-105">Konstanty mohou obsahovat čísla, logické hodnoty, řetězce nebo odkaz s hodnotou null.</span><span class="sxs-lookup"><span data-stu-id="0351e-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="0351e-106">Nevytvářejte konstanta představují informace, které byste měli kdykoli změnit.</span><span class="sxs-lookup"><span data-stu-id="0351e-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="0351e-107">Například nepoužívejte konstantní pole k uložení ceny služby, číslo verze produktu nebo název značky společnosti.</span><span class="sxs-lookup"><span data-stu-id="0351e-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="0351e-108">Tyto hodnoty můžete změnit v čase, a protože kompilátory rozšířit konstanty, jiný kód, kompilovat s vaší knihovny bude muset být překompilovat, aby se změny projevily.</span><span class="sxs-lookup"><span data-stu-id="0351e-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="0351e-109">Viz také [jen pro čtení](../../../csharp/language-reference/keywords/readonly.md) – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="0351e-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="0351e-110">Příklad:</span><span class="sxs-lookup"><span data-stu-id="0351e-110">For example:</span></span>  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a><span data-ttu-id="0351e-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0351e-111">Remarks</span></span>  
 <span data-ttu-id="0351e-112">Typ deklarace konstanty Určuje typ členy, kteří zavádí deklaraci.</span><span class="sxs-lookup"><span data-stu-id="0351e-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="0351e-113">Inicializátor konstanta místní nebo konstantní pole musí být konstantní výraz, který lze implicitně převést na typ cíle.</span><span class="sxs-lookup"><span data-stu-id="0351e-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>  
  
 <span data-ttu-id="0351e-114">Konstantní výraz je výraz, který může být plně vyhodnocen v době kompilace.</span><span class="sxs-lookup"><span data-stu-id="0351e-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="0351e-115">Proto možné pouze hodnoty pro konstanty odkazové typy jsou `string` a odkaz s hodnotou null.</span><span class="sxs-lookup"><span data-stu-id="0351e-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>  
  
 <span data-ttu-id="0351e-116">Deklarace konstanty můžou deklarovat několik konstanty, jako například:</span><span class="sxs-lookup"><span data-stu-id="0351e-116">The constant declaration can declare multiple constants, such as:</span></span>  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 <span data-ttu-id="0351e-117">`static` Modifikátor není povolen v deklaraci konstantní.</span><span class="sxs-lookup"><span data-stu-id="0351e-117">The `static` modifier is not allowed in a constant declaration.</span></span>  
  
 <span data-ttu-id="0351e-118">Konstanta mohl účastnit konstantní výraz, následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="0351e-118">A constant can participate in a constant expression, as follows:</span></span>  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  <span data-ttu-id="0351e-119">[Jen pro čtení](../../../csharp/language-reference/keywords/readonly.md) – klíčové slovo se liší od `const` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="0351e-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="0351e-120">A `const` pole lze inicializovat pouze na deklaraci pole.</span><span class="sxs-lookup"><span data-stu-id="0351e-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="0351e-121">A `readonly` pole jde inicializovat na deklaraci nebo v konstruktoru.</span><span class="sxs-lookup"><span data-stu-id="0351e-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="0351e-122">Proto `readonly` pole může mít různé hodnoty v závislosti na konstruktoru použít.</span><span class="sxs-lookup"><span data-stu-id="0351e-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="0351e-123">Také i když `const` pole je argumentem konstanta kompilaci `readonly` pole lze použít pro spuštění konstanty, stejně jako tento řádek:`public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="0351e-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>  
  
## <a name="example"></a><span data-ttu-id="0351e-124">Příklad</span><span class="sxs-lookup"><span data-stu-id="0351e-124">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="0351e-125">Příklad</span><span class="sxs-lookup"><span data-stu-id="0351e-125">Example</span></span>  
 <span data-ttu-id="0351e-126">Tento příklad ukazuje, jak používat konstanty jako místní proměnné.</span><span class="sxs-lookup"><span data-stu-id="0351e-126">This example demonstrates how to use constants as local variables.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0351e-127">Specifikace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="0351e-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0351e-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="0351e-128">See Also</span></span>  
 [<span data-ttu-id="0351e-129">Referenční dokumentace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="0351e-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0351e-130">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="0351e-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0351e-131">Klíčová slova jazyka C#</span><span class="sxs-lookup"><span data-stu-id="0351e-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0351e-132">Modifikátory</span><span class="sxs-lookup"><span data-stu-id="0351e-132">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="0351e-133">jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="0351e-133">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)