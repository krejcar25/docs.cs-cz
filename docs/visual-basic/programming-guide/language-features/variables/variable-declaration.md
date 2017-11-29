---
title: "Deklarace proměnné v jazyce Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7f7b924aed1da7db816aa5c11239e301428770b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="07030-102">Deklarace proměnné v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07030-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="07030-103">Je deklarovat proměnnou a určit její název a vlastností.</span><span class="sxs-lookup"><span data-stu-id="07030-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="07030-104">Příkaz deklarace pro proměnné [Dim – příkaz](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="07030-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="07030-105">Její umístění a obsah zadat vlastnosti proměnnou.</span><span class="sxs-lookup"><span data-stu-id="07030-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="07030-106">Proměnné pravidla pojmenování a požadavky najdete v tématu [deklarované názvy elementů](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="07030-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="07030-107">Deklarace úrovně</span><span class="sxs-lookup"><span data-stu-id="07030-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="07030-108">Místní a členské proměnné</span><span class="sxs-lookup"><span data-stu-id="07030-108">Local and Member Variables</span></span>  
 <span data-ttu-id="07030-109">A *místní proměnné* je ten, který je deklarován v rámci procedury.</span><span class="sxs-lookup"><span data-stu-id="07030-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="07030-110">A *členské proměnné* je členem skupiny [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zadejte; je deklarovaný na úrovni modulu, uvnitř třídy, struktury nebo modul, ale není v rámci žádné procedury interní třídy, struktury nebo modul.</span><span class="sxs-lookup"><span data-stu-id="07030-110">A *member variable* is a member of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="07030-111">Sdílené a instanci proměnné</span><span class="sxs-lookup"><span data-stu-id="07030-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="07030-112">Ve třídě nebo struktuře kategorii členské proměnné závisí na tom, jestli je sdílené.</span><span class="sxs-lookup"><span data-stu-id="07030-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="07030-113">Pokud je deklarovaný s [sdílené](../../../../visual-basic/language-reference/modifiers/shared.md) – klíčové slovo, je *sdílené proměnné*, a existuje v jedné kopie sdílí všechny instance třídu nebo strukturu.</span><span class="sxs-lookup"><span data-stu-id="07030-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="07030-114">V opačném případě je *proměnnou instance*, a samostatnou kopii se vytvoří pro každou instanci třídu nebo strukturu.</span><span class="sxs-lookup"><span data-stu-id="07030-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="07030-115">Kopii proměnnou instance dané je k dispozici pouze pro instanci třídu nebo strukturu, ve kterém byla vytvořena.</span><span class="sxs-lookup"><span data-stu-id="07030-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="07030-116">Je nezávislé na kopii této instance proměnné v jeho ostatní instance třídu nebo strukturu.</span><span class="sxs-lookup"><span data-stu-id="07030-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="07030-117">Deklarující typ dat</span><span class="sxs-lookup"><span data-stu-id="07030-117">Declaring Data Type</span></span>  
 <span data-ttu-id="07030-118">[Jako](../../../../visual-basic/language-reference/statements/as-clause.md) klauzule příkazu deklarace umožňuje definovat datový typ nebo typ objektu proměnné jsou deklarace.</span><span class="sxs-lookup"><span data-stu-id="07030-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="07030-119">Můžete zadat jakýkoli z následujících typů proměnné:</span><span class="sxs-lookup"><span data-stu-id="07030-119">You can specify any of the following types for a variable:</span></span>  
  
-   <span data-ttu-id="07030-120">Základní datový typ, jako například `Boolean`, `Long`, nebo`Decimal`</span><span class="sxs-lookup"><span data-stu-id="07030-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
-   <span data-ttu-id="07030-121">Složené datové typu, například pole nebo struktura</span><span class="sxs-lookup"><span data-stu-id="07030-121">A composite data type, such as an array or structure</span></span>  
  
-   <span data-ttu-id="07030-122">Typ objektu nebo třída definovaná v aplikaci nebo v jiné aplikaci</span><span class="sxs-lookup"><span data-stu-id="07030-122">An object type, or class, defined either in your application or in another application</span></span>  
  
-   <span data-ttu-id="07030-123">A [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] třídy, jako například <xref:System.Windows.Forms.Label> nebo<xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="07030-123">A [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
-   <span data-ttu-id="07030-124">Typ rozhraní, jako například <xref:System.IComparable> nebo<xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="07030-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="07030-125">Bez nutnosti opakování datový typ je možné deklarovat několik proměnné v jednom příkazu.</span><span class="sxs-lookup"><span data-stu-id="07030-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="07030-126">V následující příkazy, proměnné `i`, `j`, a `k` je deklarován jako typ `Integer`, `l` a `m` jako `Long`, a `x` a `y` jako `Single`:</span><span class="sxs-lookup"><span data-stu-id="07030-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="07030-127">Další informace o typech dat najdete v tématu [datové typy](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="07030-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="07030-128">Další informace o objektech, najdete v části [objekty a třídy](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) a [programování s komponentami](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span><span class="sxs-lookup"><span data-stu-id="07030-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="07030-129">Odvození místního typu</span><span class="sxs-lookup"><span data-stu-id="07030-129">Local Type Inference</span></span>  
 <span data-ttu-id="07030-130">*Odvození typu* slouží k určení datové typy lokální proměnné deklarované bez `As` klauzule.</span><span class="sxs-lookup"><span data-stu-id="07030-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="07030-131">Kompilátor odvodí typ proměnné z typu inicializace výrazu.</span><span class="sxs-lookup"><span data-stu-id="07030-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="07030-132">To umožňuje deklarujte proměnné bez explicitně s uvedením typu.</span><span class="sxs-lookup"><span data-stu-id="07030-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="07030-133">V následujícím příkladu obě `num1` a `num2` jsou silného typu jako celá čísla.</span><span class="sxs-lookup"><span data-stu-id="07030-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 <span data-ttu-id="07030-134">Pokud chcete použít odvození místního typu `Option Infer` musí být nastavena na `On`.</span><span class="sxs-lookup"><span data-stu-id="07030-134">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="07030-135">Další informace najdete v tématu [odvození místního typu](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) a [Option Infer – příkaz](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="07030-135">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="07030-136">Vlastnosti deklarované proměnných</span><span class="sxs-lookup"><span data-stu-id="07030-136">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="07030-137">*Životnost* proměnné je doba, během které it je k dispozici pro použití.</span><span class="sxs-lookup"><span data-stu-id="07030-137">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="07030-138">Obecně platí existuje proměnná tak dlouho, dokud elementu, který deklaruje (například postup nebo třída) i nadále existovat.</span><span class="sxs-lookup"><span data-stu-id="07030-138">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="07030-139">Pokud proměnnou nemusíte pokračovat, existující mimo dobu životnosti obsaženého prvku, není potřeba provádět žádné zvláštní v deklaraci.</span><span class="sxs-lookup"><span data-stu-id="07030-139">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="07030-140">Pokud proměnná musí pokračovat déle, než jeho obsahující element existovat, můžete zahrnout `Static` nebo `Shared` – klíčové slovo v jeho `Dim` příkaz.</span><span class="sxs-lookup"><span data-stu-id="07030-140">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="07030-141">Další informace najdete v tématu [doba platnosti v jazyce Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span><span class="sxs-lookup"><span data-stu-id="07030-141">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="07030-142">*Oboru* proměnné je sada všechen kód, který může na ni odkazuje bez určení názvu.</span><span class="sxs-lookup"><span data-stu-id="07030-142">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="07030-143">Proměnnou rozsahu je určen podle kde je deklarován.</span><span class="sxs-lookup"><span data-stu-id="07030-143">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="07030-144">Kód umístěný v dané oblasti, můžete použít proměnné definované v této oblasti bez nutnosti kvalifikaci jejich názvy.</span><span class="sxs-lookup"><span data-stu-id="07030-144">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="07030-145">Další informace najdete v tématu [oboru v jazyce Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="07030-145">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="07030-146">Proměnnou *úroveň přístupu* je rozsah kód, který má oprávnění k přístupu.</span><span class="sxs-lookup"><span data-stu-id="07030-146">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="07030-147">To je dáno – modifikátor přístupu (například [veřejné](../../../../visual-basic/language-reference/modifiers/public.md) nebo [privátní](../../../../visual-basic/language-reference/modifiers/private.md)) použitý v `Dim` příkaz.</span><span class="sxs-lookup"><span data-stu-id="07030-147">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="07030-148">Další informace najdete v tématu [úrovně v jazyce Visual Basic přístupu](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="07030-148">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07030-149">Viz také</span><span class="sxs-lookup"><span data-stu-id="07030-149">See Also</span></span>  
 [<span data-ttu-id="07030-150">Postupy: vytvoření nové proměnné</span><span class="sxs-lookup"><span data-stu-id="07030-150">How to: Create a New Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)  
 [<span data-ttu-id="07030-151">Postupy: Přesun dat do a z proměnné</span><span class="sxs-lookup"><span data-stu-id="07030-151">How to: Move Data Into and Out of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [<span data-ttu-id="07030-152">Datové typy</span><span class="sxs-lookup"><span data-stu-id="07030-152">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="07030-153">Chráněný</span><span class="sxs-lookup"><span data-stu-id="07030-153">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="07030-154">Friend</span><span class="sxs-lookup"><span data-stu-id="07030-154">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="07030-155">Statické</span><span class="sxs-lookup"><span data-stu-id="07030-155">Static</span></span>](../../../../visual-basic/language-reference/modifiers/static.md)  
 [<span data-ttu-id="07030-156">Deklarované charakteristiky elementu</span><span class="sxs-lookup"><span data-stu-id="07030-156">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="07030-157">Odvození místního typu</span><span class="sxs-lookup"><span data-stu-id="07030-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="07030-158">Option Infer – příkaz</span><span class="sxs-lookup"><span data-stu-id="07030-158">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)