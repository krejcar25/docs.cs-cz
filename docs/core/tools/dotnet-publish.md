---
title: "příkaz - .NET Core rozhraní příkazového řádku publikování DotNet."
description: "Příkaz Publikovat dotnet publikuje do adresáře projektu .NET Core."
author: mairaw
ms.author: mairaw
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: e29d5269ab5e9e2c9fd08811552c09ec1c95363d
ms.sourcegitcommit: 3fd4e718d1bac9769fe0c1dd08ca1b2323ae272b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/11/2018
---
# <a name="dotnet-publish"></a>publikování DotNet.

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Název

`dotnet publish`-Pack aplikace a jeho závislosti do složky pro nasazení k hostování systému.

## <a name="synopsis"></a>Stručný obsah

# <a name="net-core-2xtabnetcore2x"></a>[.NET pro základní 2.x](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET pro základní 1.x](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a>Popis

`dotnet publish`zkompiluje aplikace, čte prostřednictvím jeho závislé součásti, zadaný v souboru projektu a publikuje výslednou sadu soubory do adresáře. Výstup bude obsahovat následující:

* Kód jazyka (IL) v sestavení s mezilehlé *dll* rozšíření.
* *. deps.json* soubor, který obsahuje všechny závislosti projektu.
* *. runtime.config.json* soubor, který určuje sdílený modul runtime, který aplikace očekává a také další možnosti konfigurace pro modul runtime (například uvolňování paměti – typ kolekce).
* Závislosti aplikace. Tyto jsou kopírovány z mezipaměti NuGet do výstupní složky.

`dotnet publish` Výstup příkazu je připraven k nasazení k hostování systému (například server, PC, Mac, přenosných počítačů) pro spuštění a je jediným oficiálně podporované způsob, jak připravit aplikaci pro nasazení. V závislosti na typu nasazení, který určuje projekt hostitelský systém může nebo nemusí mít .NET Core sdílené na něm nainstalován modul runtime. Další informace najdete v tématu [nasazení aplikace .NET Core](../deploying/index.md). Struktura adresářů publikované aplikace, najdete v části [adresářovou strukturu](/aspnet/core/hosting/directory-structure).

## <a name="arguments"></a>Arguments

`PROJECT`

Projekt k publikování, výchozí nastavení k aktuálnímu adresáři, není-li zadána.

## <a name="options"></a>Možnosti

# <a name="net-core-2xtabnetcore2x"></a>[.NET pro základní 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Definuje konfiguraci sestavení. Výchozí hodnota je `Debug`.

`-f|--framework <FRAMEWORK>`

Publikuje aplikace pro zadaný [cílové rozhraní](../../standard/frameworks.md). Musíte zadat cílové rozhraní v souboru projektu.

`--force`

Vynutí všechny závislosti pro přeloženy i v případě, že poslední obnovení bylo úspěšné. Jde o ekvivalent odstraňování *project.assets.json* souboru.

`-h|--help`

Vytiskne krátké nápovědy pro příkaz.

`--manifest <PATH_TO_MANIFEST_FILE>`

Určuje jeden nebo několik [cíle manifesty](../deploying/runtime-store.md) sloužící k uvolnění dočasné paměti sadu balíčků, které jsou publikovány v aplikaci. Soubor manifestu je součástí výstup [ `dotnet store` příkaz](dotnet-store.md). Chcete-li zadat více manifesty, přidejte `--manifest` možnost pro každý manifest. Tato možnost je dostupná od verze rozhraní .NET Core 2.0 SDK.

`--no-dependencies`

Ignoruje odkazy na projekt na projekt a obnoví pouze kořenové projektu.

`--no-restore`

Neprovede implicitní obnovení, při spuštění příkazu.

`-o|--output <OUTPUT_DIRECTORY>`

Určuje cestu k výstupnímu adresáři. Pokud není zadáno, je standardně *./bin/[configuration]/[framework]/* pro nasazení závislé na framework nebo *./bin/[configuration]/[framework]/[runtime]* samostatná nasazení.
Pokud je zadaný na relativní cestu, výstupní adresář generované je relativní k umístění souboru projektu, není pro aktuální pracovní adresář.

`--self-contained`

Publikuje na .NET Core runtime s vaší aplikací, takže modul runtime nemusí být nainstalován v cílovém počítači. Pokud je zadán identifikátor runtime, výchozí hodnota je `true`. Další informace o různých typů najdete v tématu [nasazení aplikace .NET Core](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publikuje aplikace pro daný modulu runtime. Používá se při vytváření [samostatná nasazení (SCD)](../deploying/index.md#self-contained-deployments-scd). Seznam Runtime identifikátorů (RID), najdete v článku [identifikátorů RID katalogu](../rid-catalog.md). Výchozí hodnota je publikování [nasazení závislé na framework (disketové jednotky)](../deploying/index.md#framework-dependent-deployments-fdd).

`-v|--verbosity <LEVEL>`

Nastaví úroveň podrobností příkazu. Povolené hodnoty jsou `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, a `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definuje příponu verze, která má nahradit hvězdičku (`*`) v poli verze souboru projektu.

# <a name="net-core-1xtabnetcore1x"></a>[.NET pro základní 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Definuje konfiguraci sestavení. Výchozí hodnota je `Debug`.

`-f|--framework <FRAMEWORK>`

Publikuje aplikace pro zadaný [cílové rozhraní](../../standard/frameworks.md). Musíte zadat cílové rozhraní v souboru projektu.

`-h|--help`

Vytiskne krátké nápovědy pro příkaz.

`--manifest <PATH_TO_MANIFEST_FILE>`

Určuje jeden nebo několik [cíle manifesty](../deploying/runtime-store.md) sloužící k uvolnění dočasné paměti sadu balíčků, které jsou publikovány v aplikaci. Soubor manifestu je součástí výstup [ `dotnet store` příkaz](dotnet-store.md). Chcete-li zadat více manifesty, přidejte `--manifest` možnost pro každý manifest. Tato možnost je dostupná od verze rozhraní .NET Core 2.0 SDK.

`-o|--output <OUTPUT_DIRECTORY>`

Určuje cestu k výstupnímu adresáři. Pokud není zadáno, je standardně *./bin/[configuration]/[framework]/* pro nasazení závislé na framework nebo *./bin/[configuration]/[framework]/[runtime]* samostatná nasazení.
Pokud je zadaný na relativní cestu, výstupní adresář generované je relativní k umístění souboru projektu, není pro aktuální pracovní adresář.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publikuje aplikace pro daný modulu runtime. Používá se při vytváření [samostatná nasazení (SCD)](../deploying/index.md#self-contained-deployments-scd). Seznam Runtime identifikátorů (RID), najdete v článku [identifikátorů RID katalogu](../rid-catalog.md). Výchozí hodnota je publikování [nasazení závislé na framework (disketové jednotky)](../deploying/index.md#framework-dependent-deployments-fdd).

`-v|--verbosity <LEVEL>`

Nastaví úroveň podrobností příkazu. Povolené hodnoty jsou `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, a `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definuje příponu verze, která má nahradit hvězdičku (`*`) v poli verze souboru projektu.

---

## <a name="examples"></a>Příklady

Publikování tohoto projektu v aktuálním adresáři:

`dotnet publish`

Publikování aplikace pomocí souboru zadaného projektu:

`dotnet publish ~/projects/app1/app1.csproj`
    
Publikování tohoto projektu v aktuálním adresáři pomocí `netcoreapp1.1` framework:

`dotnet publish --framework netcoreapp1.1`
    
Publikování aktuální aplikace pomocí `netcoreapp1.1` framework a prostředí runtime pro `OS X 10.10` (musí seznam tento identifikátorů RID v souboru projektu).

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>Viz také

* [Cílové rozhraní](../../standard/frameworks.md)
* [Katalog identifikátor runtime (RID)](../rid-catalog.md)
