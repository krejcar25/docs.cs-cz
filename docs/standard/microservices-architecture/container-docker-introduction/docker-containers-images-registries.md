---
title: Docker kontejnery, Image a registry
description: "Architektura Mikroslužeb .NET pro aplikace .NET Kontejnerizované | Docker kontejnery, Image a registry"
keywords: "Docker, Mikroslužeb, ASP.NET, kontejneru"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 79dccadfba066c673e8ef7ea5eaf1051a434ff3a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="docker-containers-images-and-registries"></a>Docker kontejnery, Image a registry

Při použití Docker, vytvoří vývojář aplikace nebo služby a balíčky ho a jeho závislosti do bitové kopie kontejneru. Obrázek je statický reprezentace aplikace nebo služby a jeho konfigurace a závislostí.

Ke spuštění aplikace nebo služby, je vytvořit vytvořit kontejner, který bude spuštěn na hostiteli Docker instance image aplikace. Kontejnery jsou původně testovány v prostředí pro vývoj nebo počítači.

Vývojáři měli uložit bitové kopie v registru, který funguje jako knihovny obrázků a je potřeba při nasazení v produkčním orchestrators. Docker udržuje veřejné registru prostřednictvím [úložiště Docker Hub](https://hub.docker.com/); jiných dodavatelů registrech poskytovat pro různé kolekce obrázků. Alternativně můžete podniků má privátní registru on-premises pro své vlastní imagí Dockeru.

Obrázek 2 – 4 ukazuje, jak bitové kopie a registrech v Docker vztahují k ostatní součásti. Také ukazuje několik registru nabídky od dodavatelů.

![](./media/image5.PNG)

**Obrázek 2 – 4**. Taxonomii Docker podmínky a koncepty

Vložení obrázků v registru umožňuje uložit bitů statické a neměnné aplikace, včetně jejich závislosti na úrovni framework. Tyto bitové kopie můžete poté by se verzí a nasazené v několika prostředích a proto zadejte jednotky konzistentní nasazení.

Privátní image registrech buď hostované místně nebo v cloudu, se doporučuje při:

-   Bitové kopie nesmí veřejně sdílené z důvodu utajení.

-   Chcete mít minimální latenci mezi vaší bitové kopie a prostředí pro vybrané nasazení. Například pokud produkční prostředí cloudu Azure, pravděpodobně chcete ukládat obrázků v registru kontejner Azure tak, aby latence sítě bude minimální. Podobným způsobem Pokud provozním prostředí je na místě, můžete chtít mít místní Docker důvěryhodné registru k dispozici v rámci stejné místní síti.

>[!div class="step-by-step"]
[Předchozí] (docker-terminology.md) [Další] (.. /NET-Core-NET-Framework-Containers/index.MD)
