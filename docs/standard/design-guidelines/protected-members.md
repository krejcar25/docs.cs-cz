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
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 03d9eac41e693568da2d057bc1394c426df4c736
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="protected-members"></a>Chráněné členy
Chráněné členy samy o sobě neposkytují žádné rozšíření, ale mohli provádět rozšiřitelnost prostřednictvím vytváření podtříd účinnější. Můžete být používají k vystavení rozšířené možnosti vlastního nastavení bez zbytečně komplikují hlavní veřejné rozhraní.  
  
 Návrháři Framework muset buďte opatrní s chráněné členy, protože název "chráněné" může poskytnout false představu o zabezpečení. Každý, kdo je možné podtřídami třídu nezapečetěné a přístupu k chráněným členy, a proto všechny stejné Obranným kódování postupům používaným pro veřejné členy týkají chráněné členy.  
  
 **✓ ZVAŽTE** pomocí chráněné členy pro vlastní nastavení.  
  
 **PROVEĎTE ✓** považovat chráněné členy v nezapečetěných třídy jako veřejné pro účely analýzy zabezpečení, dokumentace a kompatibility.  
  
 Každý, kdo může dědí z třídy a přístup k chráněné členy.  
  
 *Části © 2005, 2009 Microsoft Corporation. Všechna práva vyhrazena.*  
  
 *Provedení podle oprávnění Pearson Education, Inc. z [pokynů pro návrh Framework: konvence, Idioms a vzory pro jedno použití knihovny .NET, 2. vydání](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina a Abrams Brada publikovaná 22 Oct 2008 pomocí Designing Effective jako součást vývoj řady Microsoft Windows.*  
  
## <a name="see-also"></a>Viz také  
 [Pokyny k návrhu architektury](../../../docs/standard/design-guidelines/index.md)  
 [Navrhování pro rozšiřitelnost](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
