---
title: "příkaz odkaz DotNet seznamu - .NET Core rozhraní příkazového řádku"
description: "Příkaz dotnet seznamu odkaz poskytuje vhodnou možnost do seznamu odkazy na projekt na projekt."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: a4ceadb6d070d7997e75b472624bbe2c1650396d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-list-reference"></a>referenční seznam DotNet.

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Název

`dotnet list reference`-Obsahuje seznam odkazů projektu do projektu.

## <a name="synopsis"></a>Stručný obsah

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Popis

`dotnet list reference` Příkaz poskytuje vhodnou možnost do seznamu odkazy na projekt pro daný projekt.

## <a name="arguments"></a>Arguments

`PROJECT`

Určuje soubor projektu pro výpis odkazy. Pokud není zadáno, bude příkaz Hledat aktuální adresář pro soubor projektu.

## <a name="options"></a>Možnosti

`-h|--help`

Vytiskne krátké nápovědy pro příkaz.

## <a name="examples"></a>Příklady

Seznam odkazy na projekt pro zadaného projektu:

`dotnet list app/app.csproj reference`

Seznam odkazů projektu pro projekt v aktuálním adresáři:

`dotnet list reference`
