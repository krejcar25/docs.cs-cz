---
title: "Vlastnost návrhu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 477b3b69ce1b8a3bb160e8e120885239e3d99e56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="property-design"></a><span data-ttu-id="8561d-102">Vlastnost návrhu</span><span class="sxs-lookup"><span data-stu-id="8561d-102">Property Design</span></span>
<span data-ttu-id="8561d-103">I když jsou vlastnosti technicky velmi podobné metody, se výrazně lišit podle toho scénáře jejich použití.</span><span class="sxs-lookup"><span data-stu-id="8561d-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="8561d-104">Měla by se zobrazit jako inteligentní pole.</span><span class="sxs-lookup"><span data-stu-id="8561d-104">They should be seen as smart fields.</span></span> <span data-ttu-id="8561d-105">Mají volání syntaxe polí a flexibilitu metod.</span><span class="sxs-lookup"><span data-stu-id="8561d-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="8561d-106">**PROVEĎTE ✓** vytvořit vlastnosti jen pro get, pokud má volající neměli mít možnost ke změně hodnoty vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="8561d-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="8561d-107">Mějte na paměti že pokud typ je typ Měnitelná odkazu vlastnost, hodnota vlastnosti lze změnit, i když je vlastnost pouze pro získání.</span><span class="sxs-lookup"><span data-stu-id="8561d-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="8561d-108">**X nesmí** poskytnout setter s širší usnadnění než metoda getter vlastnosti jen pro sadu nebo vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="8561d-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="8561d-109">Například nepoužívejte vlastnosti s veřejnou metodu setter a chráněné getter.</span><span class="sxs-lookup"><span data-stu-id="8561d-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="8561d-110">Pokud metoda getter vlastnosti nelze zadat, implementujte funkce jako metodu.</span><span class="sxs-lookup"><span data-stu-id="8561d-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="8561d-111">Vezměte v úvahu spouštění název metody s `Set` a postupujte podle pokynů s co jste by mít s názvem vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="8561d-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="8561d-112">Například <xref:System.AppDomain> má metodu s názvem `SetCachePath` místo nutnosti ryze sadu vlastnost s názvem `CachePath`.</span><span class="sxs-lookup"><span data-stu-id="8561d-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="8561d-113">**PROVEĎTE ✓** zadejte rozumný výchozí hodnoty pro všechny vlastnosti, zajistíte, že výchozí hodnoty nezpůsobovalo neustálé bezpečnostní riziko nebo terribly neefektivní kód.</span><span class="sxs-lookup"><span data-stu-id="8561d-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="8561d-114">**PROVEĎTE ✓** povolit vlastnosti nastavit v libovolném pořadí, i když to vede k dočasné neplatný stav objektu.</span><span class="sxs-lookup"><span data-stu-id="8561d-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="8561d-115">Je běžné, že dvě nebo více vlastností být vzájemně souvisejících do bodu, kde některé hodnoty jednu vlastnost může být neplatný zadané hodnotách jiných vlastností na stejný objekt.</span><span class="sxs-lookup"><span data-stu-id="8561d-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="8561d-116">V takových případech by výjimky vzniklé v neplatném stavu posunut, dokud vzájemně souvisejících vlastnosti jsou ve skutečnosti společně použít objekt.</span><span class="sxs-lookup"><span data-stu-id="8561d-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="8561d-117">**PROVEĎTE ✓** zachovat předchozí hodnotu, pokud metoda setter vlastnosti vyvolá výjimku.</span><span class="sxs-lookup"><span data-stu-id="8561d-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="8561d-118">**X nepoužívejte** vyvolání výjimky z metody vlastnost getter.</span><span class="sxs-lookup"><span data-stu-id="8561d-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="8561d-119">Mechanismy získání vlastnost by měla být jednoduché operace a nesmí mít žádné předpoklady.</span><span class="sxs-lookup"><span data-stu-id="8561d-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="8561d-120">Pokud příjemce může vyvolat výjimku, by pravděpodobně přepracovali metodu.</span><span class="sxs-lookup"><span data-stu-id="8561d-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="8561d-121">Všimněte si, že toto pravidlo se nevztahuje na indexery, kde Očekáváme, že výjimky v důsledku ověřování argumenty.</span><span class="sxs-lookup"><span data-stu-id="8561d-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="8561d-122">Indexované vlastnosti návrhu</span><span class="sxs-lookup"><span data-stu-id="8561d-122">Indexed Property Design</span></span>  
 <span data-ttu-id="8561d-123">Indexované vlastnosti je speciální vlastnost, která může mít parametry a může být volána s speciální syntaxe podobná indexu pole.</span><span class="sxs-lookup"><span data-stu-id="8561d-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="8561d-124">Indexované vlastnosti se běžně označují jako indexery.</span><span class="sxs-lookup"><span data-stu-id="8561d-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="8561d-125">Indexery by měl použít pouze v rozhraní API, které poskytují přístup k položkám v logické kolekce.</span><span class="sxs-lookup"><span data-stu-id="8561d-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="8561d-126">Například řetězec je kolekce znaky a indexeru na <xref:System.String?displayProperty=nameWithType> byl přidán k jeho znaků.</span><span class="sxs-lookup"><span data-stu-id="8561d-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="8561d-127">**✓ ZVAŽTE** použití indexery pro poskytnutí přístupu k datům uloženým v interní pole.</span><span class="sxs-lookup"><span data-stu-id="8561d-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="8561d-128">**✓ ZVAŽTE** poskytuje indexery na typy reprezentující kolekce položek.</span><span class="sxs-lookup"><span data-stu-id="8561d-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="8561d-129">**X nepoužívejte** použití indexovaných vlastností s více než jeden parametr.</span><span class="sxs-lookup"><span data-stu-id="8561d-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="8561d-130">Pokud návrh vyžaduje několik parametrů, znovu zda přistupující objekt vlastnosti skutečně představuje logické kolekce.</span><span class="sxs-lookup"><span data-stu-id="8561d-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="8561d-131">Pokud ne, používejte metody.</span><span class="sxs-lookup"><span data-stu-id="8561d-131">If it does not, use methods instead.</span></span> <span data-ttu-id="8561d-132">Vezměte v úvahu spouštění název metody s `Get` nebo `Set`.</span><span class="sxs-lookup"><span data-stu-id="8561d-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="8561d-133">**X nepoužívejte** indexery s typy parametrů jinak než <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, nebo výčet.</span><span class="sxs-lookup"><span data-stu-id="8561d-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="8561d-134">Pokud návrh vyžaduje jiné typy parametrů, důrazně přehodnocovat zda rozhraní API skutečně představuje přistupující objekt logické kolekce.</span><span class="sxs-lookup"><span data-stu-id="8561d-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="8561d-135">Pokud ne, použijte metodu.</span><span class="sxs-lookup"><span data-stu-id="8561d-135">If it does not, use a method.</span></span> <span data-ttu-id="8561d-136">Vezměte v úvahu spouštění název metody s `Get` nebo `Set`.</span><span class="sxs-lookup"><span data-stu-id="8561d-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="8561d-137">**PROVEĎTE ✓** použijte název `Item` pro indexovaných vlastností, pokud je samozřejmě lepší název (například najdete v článku <xref:System.String.Chars%2A> vlastnost na `System.String`).</span><span class="sxs-lookup"><span data-stu-id="8561d-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="8561d-138">V jazyce C# indexery jsou ve výchozím nastavení s názvem položky.</span><span class="sxs-lookup"><span data-stu-id="8561d-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="8561d-139"><xref:System.Runtime.CompilerServices.IndexerNameAttribute> Můžete použít k přizpůsobení tento název.</span><span class="sxs-lookup"><span data-stu-id="8561d-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="8561d-140">**X nesmí** zadejte indexer a metody, které jsou sémanticky ekvivalentní.</span><span class="sxs-lookup"><span data-stu-id="8561d-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="8561d-141">**X nesmí** zadat více než jednu řadu přetížené indexery jednomu typu.</span><span class="sxs-lookup"><span data-stu-id="8561d-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="8561d-142">Tato velikost je vyžadována kompilátorem C#.</span><span class="sxs-lookup"><span data-stu-id="8561d-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="8561d-143">**X nesmí** nevýchozí použití indexovaných vlastností.</span><span class="sxs-lookup"><span data-stu-id="8561d-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="8561d-144">Tato velikost je vyžadována kompilátorem C#.</span><span class="sxs-lookup"><span data-stu-id="8561d-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="8561d-145">Vlastnosti události oznámení změny</span><span class="sxs-lookup"><span data-stu-id="8561d-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="8561d-146">Někdy je užitečné k poskytování událost upozornění uživatele o změnách v hodnotě vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="8561d-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="8561d-147">Například `System.Windows.Forms.Control` vyvolá `TextChanged` události po hodnotu jeho `Text` došlo ke změně vlastností.</span><span class="sxs-lookup"><span data-stu-id="8561d-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="8561d-148">**✓ ZVAŽTE** vyvolání změnit události oznámení při změně hodnoty vlastností v vysoké úrovně rozhraní API (obvykle návrháře komponenty).</span><span class="sxs-lookup"><span data-stu-id="8561d-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="8561d-149">Pokud je dobré scénář pro uživatele vědět, když je změna vlastnost objektu, objektu by měla vyvolat událost upozornění změnu pro vlastnost.</span><span class="sxs-lookup"><span data-stu-id="8561d-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="8561d-150">Je však pravděpodobně být vhodné režii vyvolat takové události pro nízké úrovně rozhraní API, například základní typy nebo kolekce.</span><span class="sxs-lookup"><span data-stu-id="8561d-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="8561d-151">Například <xref:System.Collections.Generic.List%601> nebude vyvolat tyto události při přidání nové položky do seznamu a `Count` změny vlastností.</span><span class="sxs-lookup"><span data-stu-id="8561d-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="8561d-152">**✓ ZVAŽTE** vyvolání události oznámení při změně hodnoty vlastnosti prostřednictvím externí vynutí změn.</span><span class="sxs-lookup"><span data-stu-id="8561d-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="8561d-153">Pokud se změní hodnotu vlastnosti prostřednictvím některé externí force (způsobem, jinak než pomocí volání metody u objektu), vyvolat události označují vývojář, že hodnota se mění a došlo ke změně.</span><span class="sxs-lookup"><span data-stu-id="8561d-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="8561d-154">Dobrým příkladem je `Text` vlastností ovládacího prvku textové pole.</span><span class="sxs-lookup"><span data-stu-id="8561d-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="8561d-155">Když uživatel zadá text v `TextBox`, hodnota vlastnosti automaticky změní.</span><span class="sxs-lookup"><span data-stu-id="8561d-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="8561d-156">*Části © 2005, 2009 Microsoft Corporation. Všechna práva vyhrazena.*</span><span class="sxs-lookup"><span data-stu-id="8561d-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8561d-157">*Provedení podle oprávnění Pearson Education, Inc. z [pokynů pro návrh Framework: konvence, Idioms a vzory pro jedno použití knihovny .NET, 2. vydání](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina a Abrams Brada publikovaná 22 Oct 2008 pomocí Designing Effective jako součást vývoj řady Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="8561d-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8561d-158">Viz také</span><span class="sxs-lookup"><span data-stu-id="8561d-158">See Also</span></span>  
 [<span data-ttu-id="8561d-159">Člen pokynů pro návrh</span><span class="sxs-lookup"><span data-stu-id="8561d-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="8561d-160">Pokyny pro návrh Framework</span><span class="sxs-lookup"><span data-stu-id="8561d-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)