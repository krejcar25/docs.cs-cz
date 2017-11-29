---
title: "Chráněné členy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c3aacd0f08641c01200f0b1791a78413a306590
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="protected-members"></a><span data-ttu-id="46b08-102">Chráněné členy</span><span class="sxs-lookup"><span data-stu-id="46b08-102">Protected Members</span></span>
<span data-ttu-id="46b08-103">Chráněné členy samy o sobě neposkytují žádné rozšíření, ale mohli provádět rozšiřitelnost prostřednictvím vytváření podtříd účinnější.</span><span class="sxs-lookup"><span data-stu-id="46b08-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="46b08-104">Můžete být používají k vystavení rozšířené možnosti vlastního nastavení bez zbytečně komplikují hlavní veřejné rozhraní.</span><span class="sxs-lookup"><span data-stu-id="46b08-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="46b08-105">Návrháři Framework muset buďte opatrní s chráněné členy, protože název "chráněné" může poskytnout false představu o zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="46b08-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="46b08-106">Každý, kdo je možné podtřídami třídu nezapečetěné a přístupu k chráněným členy, a proto všechny stejné Obranným kódování postupům používaným pro veřejné členy týkají chráněné členy.</span><span class="sxs-lookup"><span data-stu-id="46b08-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="46b08-107">**✓ ZVAŽTE** pomocí chráněné členy pro vlastní nastavení.</span><span class="sxs-lookup"><span data-stu-id="46b08-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="46b08-108">**PROVEĎTE ✓** považovat chráněné členy v nezapečetěných třídy jako veřejné pro účely analýzy zabezpečení, dokumentace a kompatibility.</span><span class="sxs-lookup"><span data-stu-id="46b08-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="46b08-109">Každý, kdo může dědí z třídy a přístup k chráněné členy.</span><span class="sxs-lookup"><span data-stu-id="46b08-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="46b08-110">*Části © 2005, 2009 Microsoft Corporation. Všechna práva vyhrazena.*</span><span class="sxs-lookup"><span data-stu-id="46b08-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="46b08-111">*Provedení podle oprávnění Pearson Education, Inc. z [pokynů pro návrh Framework: konvence, Idioms a vzory pro jedno použití knihovny .NET, 2. vydání](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina a Abrams Brada publikovaná 22 Oct 2008 pomocí Designing Effective jako součást vývoj řady Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="46b08-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b08-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="46b08-112">See Also</span></span>  
 [<span data-ttu-id="46b08-113">Pokyny pro návrh Framework</span><span class="sxs-lookup"><span data-stu-id="46b08-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="46b08-114">Navrhování pro rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="46b08-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)