---
title: "Implementace opakování s exponenciálního omezení rychlosti"
description: "Architektura Mikroslužeb .NET pro aplikace .NET Kontejnerizované | Implementace opakování s exponenciálního omezení rychlosti"
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
ms.openlocfilehash: 7ed97b750d6e3f2aa5def72e90e070a49a7c0e63
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-retries-with-exponential-backoff"></a>Implementace opakování s exponenciálního omezení rychlosti

[*Opakuje se exponenciálního omezení rychlosti* ](https://docs.microsoft.com/azure/architecture/patterns/retry) je technika, který se pokouší opakovat operace, exponenciálně roste doba čekání, dokud nedosáhne maximální počet opakování ( [exponenciálního omezení rychlosti](https://en.wikipedia.org/wiki/Exponential_backoff)). Tento postup zahrnuje fakt, že cloudové prostředky občas je pravděpodobně není k dispozici více než několik sekund z jakéhokoli důvodu. Například orchestrator může být přesunutí kontejner do jiného uzlu v clusteru s podporou pro vyrovnávání zatížení. Během této doby může selhat některé požadavky. Dalším příkladem může být databáze jako SQL Azure, kde databáze můžete přesunout na jiný server pro zatížení vyrovnávání, což databáze má k dispozici pro několik sekund.

Existuje mnoho přístupů implementovat logiku opakovaných pokusů s exponenciálního omezení rychlosti.


>[!div class="step-by-step"]
[Předchozí] (partial selhání strategies.md) [Další] (implement-resilient-entity-framework-core-sql-connections.md)
