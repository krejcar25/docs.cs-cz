---
title: "Struktury a třídy (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08e31481feac7a6184c6b29269d193c749f440ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="structures-and-classes-visual-basic"></a><span data-ttu-id="123c7-102">Struktury a třídy (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="123c7-102">Structures and Classes (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="123c7-103">kombinuje syntaxe struktury a třídy, s tím výsledkem, že obě entity podporují většinu stejné funkce.</span><span class="sxs-lookup"><span data-stu-id="123c7-103"> unifies the syntax for structures and classes, with the result that both entities support most of the same features.</span></span> <span data-ttu-id="123c7-104">Existují však také důležité rozdíly mezi struktury a třídy.</span><span class="sxs-lookup"><span data-stu-id="123c7-104">However, there are also important differences between structures and classes.</span></span>  
  
 <span data-ttu-id="123c7-105">Výhodou se odkazové typy jsou třídy – předáním odkazu na je efektivnější než předávání proměnná struktura s jeho data.</span><span class="sxs-lookup"><span data-stu-id="123c7-105">Classes have the advantage of being reference types — passing a reference is more efficient than passing a structure variable with all its data.</span></span> <span data-ttu-id="123c7-106">Na druhé straně struktury nevyžadují přidělení paměti v haldě globální.</span><span class="sxs-lookup"><span data-stu-id="123c7-106">On the other hand, structures do not require allocation of memory on the global heap.</span></span>  
  
 <span data-ttu-id="123c7-107">Protože nelze dědí strukturou, struktury slouží pouze pro objekty, které není potřeba rozšířit.</span><span class="sxs-lookup"><span data-stu-id="123c7-107">Because you cannot inherit from a structure, structures should be used only for objects that do not need to be extended.</span></span> <span data-ttu-id="123c7-108">Struktury použijte, pokud má velikost malých instance objektu, který chcete vytvořit a vezměte v úvahu charakteristiky výkonu už třídy a struktury.</span><span class="sxs-lookup"><span data-stu-id="123c7-108">Use structures when the object you wish to create has a small instance size, and take into account the performance characteristics of classes versus structures.</span></span>  
  
## <a name="similarities"></a><span data-ttu-id="123c7-109">Podobnosti</span><span class="sxs-lookup"><span data-stu-id="123c7-109">Similarities</span></span>  
 <span data-ttu-id="123c7-110">Struktury a třídy jsou podobné v těchto ohledech:</span><span class="sxs-lookup"><span data-stu-id="123c7-110">Structures and classes are similar in the following respects:</span></span>  
  
-   <span data-ttu-id="123c7-111">Jsou obě *kontejneru* typy, což znamená, že obsahují jiné typy jako členy.</span><span class="sxs-lookup"><span data-stu-id="123c7-111">Both are *container* types, meaning that they contain other types as members.</span></span>  
  
-   <span data-ttu-id="123c7-112">Mají obě členy, které mohou zahrnovat konstruktory, metody, vlastnosti, pole, konstanty, výčty, události a obslužné rutiny událostí.</span><span class="sxs-lookup"><span data-stu-id="123c7-112">Both have members, which can include constructors, methods, properties, fields, constants, enumerations, events, and event handlers.</span></span> <span data-ttu-id="123c7-113">Nezaměňujte však tito členové s deklarovaný *elementy* struktury.</span><span class="sxs-lookup"><span data-stu-id="123c7-113">However, do not confuse these members with the declared *elements* of a structure.</span></span>  
  
-   <span data-ttu-id="123c7-114">Členové těchto dvou možností můžete své úrovně přístupu.</span><span class="sxs-lookup"><span data-stu-id="123c7-114">Members of both can have individualized access levels.</span></span> <span data-ttu-id="123c7-115">Například lze deklarovat jednoho člena `Public` a jiné `Private`.</span><span class="sxs-lookup"><span data-stu-id="123c7-115">For example, one member can be declared `Public` and another `Private`.</span></span>  
  
-   <span data-ttu-id="123c7-116">Jak můžete implementovat rozhraní.</span><span class="sxs-lookup"><span data-stu-id="123c7-116">Both can implement interfaces.</span></span>  
  
-   <span data-ttu-id="123c7-117">Jak může mít sdílené konstruktory, s nebo bez parametrů.</span><span class="sxs-lookup"><span data-stu-id="123c7-117">Both can have shared constructors, with or without parameters.</span></span>  
  
-   <span data-ttu-id="123c7-118">Jak můžou zpřístupnit *výchozí vlastnost*, za předpokladu, že má vlastnost minimálně jeden parametr.</span><span class="sxs-lookup"><span data-stu-id="123c7-118">Both can expose a *default property*, provided that property takes at least one parameter.</span></span>  
  
-   <span data-ttu-id="123c7-119">Obě deklarace a vyvolávání událostí a obě můžou deklarovat delegáti.</span><span class="sxs-lookup"><span data-stu-id="123c7-119">Both can declare and raise events, and both can declare delegates.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="123c7-120">Rozdíly</span><span class="sxs-lookup"><span data-stu-id="123c7-120">Differences</span></span>  
 <span data-ttu-id="123c7-121">Struktury a třídy se liší v tyto údaje:</span><span class="sxs-lookup"><span data-stu-id="123c7-121">Structures and classes differ in the following particulars:</span></span>  
  
-   <span data-ttu-id="123c7-122">Struktury jsou *typů hodnot*; třídy jsou *odkazové typy*.</span><span class="sxs-lookup"><span data-stu-id="123c7-122">Structures are *value types*; classes are *reference types*.</span></span> <span data-ttu-id="123c7-123">Proměnné typu struktura obsahuje data struktura, nikoli obsahující odkaz na data jako typ třídy nemá.</span><span class="sxs-lookup"><span data-stu-id="123c7-123">A variable of a structure type contains the structure's data, rather than containing a reference to the data as a class type does.</span></span>  
  
-   <span data-ttu-id="123c7-124">Struktury použijte přidělení zásobníku; třídy pomocí přidělení haldy.</span><span class="sxs-lookup"><span data-stu-id="123c7-124">Structures use stack allocation; classes use heap allocation.</span></span>  
  
-   <span data-ttu-id="123c7-125">Všechny prvky struktura jsou `Public` ve výchozím nastavení; třídy proměnných a konstant jsou `Private` ve výchozím nastavení jsou členy jiné třídy `Public` ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="123c7-125">All structure elements are `Public` by default; class variables and constants are `Private` by default, while other class members are `Public` by default.</span></span> <span data-ttu-id="123c7-126">Toto chování pro členy třídy zajišťuje kompatibilitu s Visual Basic 6.0 systému výchozí hodnoty.</span><span class="sxs-lookup"><span data-stu-id="123c7-126">This behavior for class members provides compatibility with the Visual Basic 6.0 system of defaults.</span></span>  
  
-   <span data-ttu-id="123c7-127">Struktury musí mít alespoň jeden sdíleném proměnnou nebo sdíleném, noncustom event element; Třída může být zcela prázdný.</span><span class="sxs-lookup"><span data-stu-id="123c7-127">A structure must have at least one nonshared variable or nonshared, noncustom event element; a class can be completely empty.</span></span>  
  
-   <span data-ttu-id="123c7-128">Elementy struktury nelze deklarovat jako `Protected`; můžete členy třídy.</span><span class="sxs-lookup"><span data-stu-id="123c7-128">Structure elements cannot be declared as `Protected`; class members can.</span></span>  
  
-   <span data-ttu-id="123c7-129">Struktura postupu můžete zpracování událostí, pouze pokud je [sdílené](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` postupu a pouze pomocí Řešitele [AddHandler – příkaz](../../../../visual-basic/language-reference/statements/addhandler-statement.md); všechny třídy postupu dokáže zpracovat události, s použitím buď [ Zpracovává](../../../../visual-basic/language-reference/statements/handles-clause.md) – klíčové slovo nebo `AddHandler` příkaz.</span><span class="sxs-lookup"><span data-stu-id="123c7-129">A structure procedure can handle events only if it is a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure, and only by means of the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md); any class procedure can handle events, using either the [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) keyword or the `AddHandler` statement.</span></span> <span data-ttu-id="123c7-130">Další informace najdete v tématu [události](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="123c7-130">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
-   <span data-ttu-id="123c7-131">Deklarace proměnných struktura nelze zadat inicializátory nebo počáteční velikosti pole; deklarace proměnných třídy můžete.</span><span class="sxs-lookup"><span data-stu-id="123c7-131">Structure variable declarations cannot specify initializers or initial sizes for arrays; class variable declarations can.</span></span>  
  
-   <span data-ttu-id="123c7-132">Struktury implicitně dědí <xref:System.ValueType?displayProperty=nameWithType> třídy a nemůže Zdědit z libovolného typu; třídy můžete dědí všechny třídy nebo třídy jiné než <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="123c7-132">Structures implicitly inherit from the <xref:System.ValueType?displayProperty=nameWithType> class and cannot inherit from any other type; classes can inherit from any class or classes other than <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="123c7-133">Struktury nejsou zděditelné; třídy jsou.</span><span class="sxs-lookup"><span data-stu-id="123c7-133">Structures are not inheritable; classes are.</span></span>  
  
-   <span data-ttu-id="123c7-134">Struktury se nikdy ukončeno, takže modul CLR (CLR) nikdy nevolá <xref:System.Object.Finalize%2A> metodu na všechny struktura; třídy jsou ukončena modulem garbage collector (GC), který volá <xref:System.Object.Finalize%2A> na třídu, když zjistí neexistují žádné aktivní odkazy Zbývající.</span><span class="sxs-lookup"><span data-stu-id="123c7-134">Structures are never terminated, so the common language runtime (CLR) never calls the <xref:System.Object.Finalize%2A> method on any structure; classes are terminated by the garbage collector (GC), which calls <xref:System.Object.Finalize%2A> on a class when it detects there are no active references remaining.</span></span>  
  
-   <span data-ttu-id="123c7-135">Struktury nevyžaduje konstruktor; Třída nepodporuje.</span><span class="sxs-lookup"><span data-stu-id="123c7-135">A structure does not require a constructor; a class does.</span></span>  
  
-   <span data-ttu-id="123c7-136">Může mít struktury sdíleném konstruktory pouze v případě, že jejich trvat parametry; třídy lze nastavit s nebo bez parametrů.</span><span class="sxs-lookup"><span data-stu-id="123c7-136">Structures can have nonshared constructors only if they take parameters; classes can have them with or without parameters.</span></span>  
  
 <span data-ttu-id="123c7-137">Každý struktura má implicitní veřejný konstruktor bez parametrů.</span><span class="sxs-lookup"><span data-stu-id="123c7-137">Every structure has an implicit public constructor without parameters.</span></span> <span data-ttu-id="123c7-138">Tento konstruktor inicializuje všechna struktura datové prvky na výchozí hodnoty.</span><span class="sxs-lookup"><span data-stu-id="123c7-138">This constructor initializes all the structure's data elements to their default values.</span></span> <span data-ttu-id="123c7-139">Toto chování nelze znovu definovat.</span><span class="sxs-lookup"><span data-stu-id="123c7-139">You cannot redefine this behavior.</span></span>  
  
## <a name="instances-and-variables"></a><span data-ttu-id="123c7-140">Instance a proměnné</span><span class="sxs-lookup"><span data-stu-id="123c7-140">Instances and Variables</span></span>  
 <span data-ttu-id="123c7-141">Protože struktury jsou typy hodnot, každá proměnná struktura je trvale vázána instance jednotlivých struktura.</span><span class="sxs-lookup"><span data-stu-id="123c7-141">Because structures are value types, each structure variable is permanently bound to an individual structure instance.</span></span> <span data-ttu-id="123c7-142">Ale třídy jsou odkazové typy a proměnné objektu mohou odkazovat na různých instancí třídy v různých časech.</span><span class="sxs-lookup"><span data-stu-id="123c7-142">But classes are reference types, and an object variable can refer to various class instances at different times.</span></span> <span data-ttu-id="123c7-143">Tento rozdíl ovlivní vaše použití třídy a struktury následujícími způsoby:</span><span class="sxs-lookup"><span data-stu-id="123c7-143">This distinction affects your usage of structures and classes in the following ways:</span></span>  
  
-   <span data-ttu-id="123c7-144">**Inicializace.**</span><span class="sxs-lookup"><span data-stu-id="123c7-144">**Initialization.**</span></span> <span data-ttu-id="123c7-145">Proměnné struktury zahrnuje implicitně inicializaci elementů pomocí struktura konstruktor bez parametrů.</span><span class="sxs-lookup"><span data-stu-id="123c7-145">A structure variable implicitly includes an initialization of the elements using the structure's parameterless constructor.</span></span> <span data-ttu-id="123c7-146">Proto `Dim s As struct1` je ekvivalentní `Dim s As struct1 = New struct1()`.</span><span class="sxs-lookup"><span data-stu-id="123c7-146">Therefore, `Dim s As struct1` is equivalent to `Dim s As struct1 = New struct1()`.</span></span>  
  
-   <span data-ttu-id="123c7-147">**Přiřazení proměnné.**</span><span class="sxs-lookup"><span data-stu-id="123c7-147">**Assigning Variables.**</span></span> <span data-ttu-id="123c7-148">Pokud přiřadit jednu proměnnou struktura do jiné nebo struktura instance předat argumentu procedury, aktuálních hodnot všech proměnných elementů se zkopírují do nové struktury.</span><span class="sxs-lookup"><span data-stu-id="123c7-148">When you assign one structure variable to another, or pass a structure instance to a procedure argument, the current values of all the variable elements are copied to the new structure.</span></span> <span data-ttu-id="123c7-149">Když přiřadit jednu proměnnou objekt do jiné nebo předání proceduře proměnné objektu, se zkopírují pouze odkaz na ukazatel.</span><span class="sxs-lookup"><span data-stu-id="123c7-149">When you assign one object variable to another, or pass an object variable to a procedure, only the reference pointer is copied.</span></span>  
  
-   <span data-ttu-id="123c7-150">**Nic přiřazení.**</span><span class="sxs-lookup"><span data-stu-id="123c7-150">**Assigning Nothing.**</span></span> <span data-ttu-id="123c7-151">Můžete přiřadit hodnotu [nic](../../../../visual-basic/language-reference/nothing.md) pro strukturu proměnné, ale instance nadále přidružená k proměnné.</span><span class="sxs-lookup"><span data-stu-id="123c7-151">You can assign the value [Nothing](../../../../visual-basic/language-reference/nothing.md) to a structure variable, but the instance continues to be associated with the variable.</span></span> <span data-ttu-id="123c7-152">Můžete volat jeho metody a přístup k jeho datové prvky, i když proměnné elementy jsou opětovně inicializovány podle přiřazení.</span><span class="sxs-lookup"><span data-stu-id="123c7-152">You can still call its methods and access its data elements, although variable elements are reinitialized by the assignment.</span></span>  
  
     <span data-ttu-id="123c7-153">Pokud nastavíte proměnné objektu na oproti tomu `Nothing`, zrušíte přidružení z jakékoli instance třídy a prostřednictvím proměnnou nelze přístup žádné členy, dokud přiřadit jiná instance.</span><span class="sxs-lookup"><span data-stu-id="123c7-153">In contrast, if you set an object variable to `Nothing`, you dissociate it from any class instance, and you cannot access any members through the variable until you assign another instance to it.</span></span>  
  
-   <span data-ttu-id="123c7-154">**Více instancí.**</span><span class="sxs-lookup"><span data-stu-id="123c7-154">**Multiple Instances.**</span></span> <span data-ttu-id="123c7-155">Objektová proměnná může mít jinou třídu instance přiřazen v různou dobu a několik objektové proměnné mohou odkazovat na stejnou instanci třídy ve stejnou dobu.</span><span class="sxs-lookup"><span data-stu-id="123c7-155">An object variable can have different class instances assigned to it at different times, and several object variables can refer to the same class instance at the same time.</span></span> <span data-ttu-id="123c7-156">Změny provedené na hodnoty členů tříd ovlivňují těmto členům přistupováno pomocí jiné proměnné odkazující na stejnou instanci.</span><span class="sxs-lookup"><span data-stu-id="123c7-156">Changes you make to the values of class members affect those members when accessed through another variable pointing to the same instance.</span></span>  
  
     <span data-ttu-id="123c7-157">Elementy struktury, ale jsou izolovány. v rámci své vlastní instanci.</span><span class="sxs-lookup"><span data-stu-id="123c7-157">Structure elements, however, are isolated within their own instance.</span></span> <span data-ttu-id="123c7-158">Změny jejich hodnoty se neprojeví v žádné jiné proměnné struktury, i v jiných instance stejné `Structure` deklarace.</span><span class="sxs-lookup"><span data-stu-id="123c7-158">Changes to their values are not reflected in any other structure variables, even in other instances of the same `Structure` declaration.</span></span>  
  
-   <span data-ttu-id="123c7-159">**Rovnosti.**</span><span class="sxs-lookup"><span data-stu-id="123c7-159">**Equality.**</span></span> <span data-ttu-id="123c7-160">Testování rovnosti dvou struktur musí provést test pomocí elementu.</span><span class="sxs-lookup"><span data-stu-id="123c7-160">Equality testing of two structures must be performed with an element-by-element test.</span></span> <span data-ttu-id="123c7-161">Dvě proměnné objektu je možné porovnávat pomocí <xref:System.Object.Equals%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="123c7-161">Two object variables can be compared using the <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="123c7-162"><xref:System.Object.Equals%2A>Označuje, zda dvě proměnné, které bodu na stejnou instanci.</span><span class="sxs-lookup"><span data-stu-id="123c7-162"><xref:System.Object.Equals%2A> indicates whether the two variables point to the same instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123c7-163">Viz také</span><span class="sxs-lookup"><span data-stu-id="123c7-163">See Also</span></span>  
 [<span data-ttu-id="123c7-164">Datové typy</span><span class="sxs-lookup"><span data-stu-id="123c7-164">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="123c7-165">Složené datové typy</span><span class="sxs-lookup"><span data-stu-id="123c7-165">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="123c7-166">Typy hodnot a odkazové typy</span><span class="sxs-lookup"><span data-stu-id="123c7-166">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="123c7-167">Struktury</span><span class="sxs-lookup"><span data-stu-id="123c7-167">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="123c7-168">Řešení potíží s datové typy</span><span class="sxs-lookup"><span data-stu-id="123c7-168">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="123c7-169">Struktury a ostatní programovací elementy</span><span class="sxs-lookup"><span data-stu-id="123c7-169">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="123c7-170">Objekty a třídy</span><span class="sxs-lookup"><span data-stu-id="123c7-170">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)