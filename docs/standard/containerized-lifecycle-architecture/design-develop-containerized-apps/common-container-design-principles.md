---
title: "Běžné zásady designu kontejneru"
description: "Kontejnerizované Docker životního cyklu aplikací s Microsoft platforma a nástroje"
keywords: "Docker, Mikroslužeb, ASP.NET, kontejneru"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a9cd569a931824c4fab060b99265ea9e3ca75129
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="common-container-design-principles"></a>Běžné zásady designu kontejneru

Článek získání do procesu vývoje existuje pár základních konceptech důležité zmínit, s ohledem na tom, jak používáte kontejnery.

## <a name="container-equals-a-process"></a>Kontejner se rovná proces

V kontejneru modelu kontejner představuje jeden proces. Definováním kontejner jako hranice procesu začnete vytvářet primitiv umožňuje škálování, nebo batch – vypnuté, procesy. Když spustíte kontejner Docker, uvidíte [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definice. Definuje proces a dobu života kontejneru. Po dokončení procesu životní cyklus kontejneru se ukončí. Existují dlouho běžící procesy, jako jsou webové servery a krátkodobou procesy, jako je třeba dávkové úlohy, které může je implementovaná jako Microsoft Azure [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/). Pokud proces selže, elementy end kontejneru a orchestrator má. Pokud orchestrator dostal pokyny pro udržování pět instancí spuštěných a jeden server selže, vytvoří orchestrator jiný kontejner nahradit selhal proces. V rámci úlohy batch je proces spuštěn s parametry. Po dokončení procesu, práce je dokončena.

Můžete se setkat scénář, ve kterém má více procesů spuštěných ve jediný kontejner. V dokumentu architektury, se nikdy "nikdy," ani je k dispozici vždy na "vždy". Pro scénáře, které vyžadují více procesů, je použít běžný vzor [nadřízeného](http://supervisord.org/).


>[!div class="step-by-step"]
[Předchozí] (návrhu docker-applications.md) [Další] (monolitický applications.md)
