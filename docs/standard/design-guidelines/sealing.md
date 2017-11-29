---
title: "Zapečetění"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8caa253a3f17c58f542317de579c4f7832c4efac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="sealing"></a><span data-ttu-id="41403-102">Zapečetění</span><span class="sxs-lookup"><span data-stu-id="41403-102">Sealing</span></span>
<span data-ttu-id="41403-103">Jedna z funkcí objektově orientované rozhraní se vývojáři můžou rozšířit a přizpůsobit způsoby neočekávané návrháři framework.</span><span class="sxs-lookup"><span data-stu-id="41403-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="41403-104">Toto je napájení i nebezpečí extensible návrhu.</span><span class="sxs-lookup"><span data-stu-id="41403-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="41403-105">Při návrhu vaší framework je, proto velmi důležité pečlivě návrh pro rozšíření, pokud se požaduje a omezit rozšiřitelnosti, když je nebezpečné.</span><span class="sxs-lookup"><span data-stu-id="41403-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="41403-106">Zapečetění je výkonný mechanismus, který brání rozšíření.</span><span class="sxs-lookup"><span data-stu-id="41403-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="41403-107">Můžete ji třídu nebo jednotlivé členy.</span><span class="sxs-lookup"><span data-stu-id="41403-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="41403-108">Zapečetění třídu zabraňuje uživatelům v dědění ze třídy.</span><span class="sxs-lookup"><span data-stu-id="41403-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="41403-109">Zapečetění členem zabraňuje uživatelům v přepsání konkrétní člena.</span><span class="sxs-lookup"><span data-stu-id="41403-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="41403-110">**X nesmí** zapečetit třídy bez nutnosti důvodem k tomu.</span><span class="sxs-lookup"><span data-stu-id="41403-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="41403-111">Zapečetění třídu, protože nelze úvahách o scénářem rozšíření není dobrý důvod.</span><span class="sxs-lookup"><span data-stu-id="41403-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="41403-112">Uživatelé Framework jako dědění ze třídy z různých důvodů nonobvious, například přidávání členů pohodlí.</span><span class="sxs-lookup"><span data-stu-id="41403-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="41403-113">V tématu [Nezapečetěné třídy](../../../docs/standard/design-guidelines/unsealed-classes.md) příklady nonobvious důvodů uživatelé chtějí dědit z typu.</span><span class="sxs-lookup"><span data-stu-id="41403-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="41403-114">Dobré důvody pro zapouzdření třídy zahrnují následující:</span><span class="sxs-lookup"><span data-stu-id="41403-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="41403-115">Třída je statická třída.</span><span class="sxs-lookup"><span data-stu-id="41403-115">The class is a static class.</span></span> <span data-ttu-id="41403-116">V tématu [statická třída návrhu](../../../docs/standard/design-guidelines/static-class.md).</span><span class="sxs-lookup"><span data-stu-id="41403-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="41403-117">Třída ukládá tajné klíče citlivé na zabezpečení v zděděné chráněné členy.</span><span class="sxs-lookup"><span data-stu-id="41403-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="41403-118">Třídy dědí mnoho členů virtuální a náklady na jejich jednotlivě zapečetění by převažují nad přínosy ponechání třídy nezapečetěné.</span><span class="sxs-lookup"><span data-stu-id="41403-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="41403-119">Třída je atribut, který vyžaduje modul runtime velmi rychlé hledání.</span><span class="sxs-lookup"><span data-stu-id="41403-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="41403-120">Zapečetěné atributů mají mírně vyšší úrovně výkonu než ty, které jsou nezapečetěné.</span><span class="sxs-lookup"><span data-stu-id="41403-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="41403-121">v tématu [atributy](../../../docs/standard/design-guidelines/attributes.md).</span><span class="sxs-lookup"><span data-stu-id="41403-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="41403-122">**X nesmí** deklarovat chráněný nebo virtuální členy v zapečetěných typech.</span><span class="sxs-lookup"><span data-stu-id="41403-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="41403-123">Podle definice nemůžou být zděděny zapečetěných typech.</span><span class="sxs-lookup"><span data-stu-id="41403-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="41403-124">To znamená, že chráněné členy v zapečetěných typech nelze volat v zapečetěných typech virtuální metody nelze přepsat.</span><span class="sxs-lookup"><span data-stu-id="41403-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="41403-125">**✓ ZVAŽTE** zapečetění členů, které můžete přepsat.</span><span class="sxs-lookup"><span data-stu-id="41403-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="41403-126">Problémy, které může být důsledkem představení virtuální členové (popsané v [virtuální členové](../../../docs/standard/design-guidelines/virtual-members.md)) použít k přepsání i, i když mírně menší míře.</span><span class="sxs-lookup"><span data-stu-id="41403-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="41403-127">Zapečetění přepsání chrání před tyto problémy od tohoto bodu v hierarchii dědičnosti.</span><span class="sxs-lookup"><span data-stu-id="41403-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="41403-128">*Části © 2005, 2009 Microsoft Corporation. Všechna práva vyhrazena.*</span><span class="sxs-lookup"><span data-stu-id="41403-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="41403-129">*Provedení podle oprávnění Pearson Education, Inc. z [pokynů pro návrh Framework: konvence, Idioms a vzory pro jedno použití knihovny .NET, 2. vydání](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina a Abrams Brada publikovaná 22 Oct 2008 pomocí Designing Effective jako součást vývoj řady Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="41403-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41403-130">Viz také</span><span class="sxs-lookup"><span data-stu-id="41403-130">See Also</span></span>  
 [<span data-ttu-id="41403-131">Pokyny pro návrh Framework</span><span class="sxs-lookup"><span data-stu-id="41403-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="41403-132">Navrhování pro rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="41403-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="41403-133">Nezapečetěné třídy</span><span class="sxs-lookup"><span data-stu-id="41403-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)