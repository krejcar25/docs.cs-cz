---
title: "Vývoj pro proces pro Azure."
description: "Architektury moderních webových aplikací pomocí ASP.NET Core a Azure | Vývoj pro proces pro Azure."
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 576a717cbdcb8cf465e8cb7b4898df1df7447aa7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="development-process-for-azure"></a>Vývoj pro proces pro Azure.

> _"S cloudem, jednotlivce a malé firmy můžete snap jejich prsty a okamžitě nastavit služby rozsáhlých."_  
> _-Royi Stephan_

 ## <a name="vision"></a>Vize

> *Vývoj aplikací dobře navrženou ASP .NET Core způsob, jakým chcete, pomocí sady Visual Studio nebo dotnet rozhraní příkazového řádku a Visual Studio Code nebo vaše editoru výběru.*

## <a name="development-environment-for-aspnet-core-apps"></a>Vývojové prostředí pro aplikace ASP.NET Core

### <a name="development-tools-choices-ide-or-editor"></a>Vývojových nástrojů volby: IDE nebo editoru

Zda dáváte přednost, úplné a výkonné IDE nebo jednoduchý a agilní editoru, společnost Microsoft nemá můžete zahrnutých při vývoji aplikace ASP.NET Core.

**Visual Studio 2017.** Pokud používáte *Visual Studio 2017* můžete vytvořit ASP.NET Core aplikace tak dlouho, dokud máte *vývoj pro různé platformy .NET Core* zatížení nainstalována. V dialogovém okně Visual Studio 2017 nastavení znázorněný na obrázku 10-1 požadované úlohy.

![](./media/image10-1.png)

**Obrázek 10-1.** Instalace .NET Core zatížení v Visual Studio 2017.

[Stažení sady Visual Studio 2017](https://www.visualstudio.com/downloads/)

**Visual Studio Code a dotnet rozhraní příkazového řádku** (nástroje a platformy pro Mac, Linux a Windows). Pokud dáváte přednost jednoduchý a napříč platformami editor podpora žádný jazyk vývoj, můžete použít Microsoft Visual Studio Code a dotnet rozhraní příkazového řádku. Tyto produkty poskytuje jednoduché, ale robustní prostředí, který zjednodušuje vývojáře pracovního postupu. Kromě toho Visual Studio Code podporuje rozšíření pro jazyk C\# a vývoj webů, poskytuje funkce intellisense a zástupce úloh v editoru.

[Stáhnout .NET Core SDK](https://www.microsoft.com/net/download/core)

[Stáhněte si Visual Studio Code](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Pracovní postup vývoje pro aplikace ASP.NET Core hostovaných v Azure

Spustí se z počítače každý vývojář, kódování aplikaci pomocí jejich upřednostňovaný jazyk a místní testování životního cyklu aplikace. Vývojáři rozhodnout jejich upřednostňovaný zdroj ovládacího prvku systému a nakonfigurovat nepřetržité integrace (CI) nebo průběžné doručování a nasazení (CD) pomocí serveru sestavení nebo na základě předdefinovaných funkcí Azure.

Pokud chcete začít s vývojem aplikace ASP.NET Core pomocí CI/CD, můžete použít Visual Studio Team Services nebo vaše organizace vlastní Team Foundation Server (TFS).

### <a name="initial-setup"></a>Počáteční nastavení

K vytvoření kanálu verze pro vaši aplikaci, musíte mít ve správě zdrojového kódu aplikace. Nastavení místního úložiště a připojte ho do vzdáleného úložiště v týmového projektu. Postupujte podle těchto pokynů:

-   [Sdílet kódu s Git a Visual Studio](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs) nebo

-   [Sdílet kódu s TFVC a Visual Studio](https://www.visualstudio.com/docs/tfvc/share-your-code-in-tfvc-vs)

Vytvoření Azure App Service, kde nasadíte aplikaci. Vytvoření webové aplikace tak, že přejdete do okna aplikační služby na portálu Azure. Klikněte na tlačítko + Přidat, vyberte šablonu webové aplikace, klikněte na tlačítko Vytvořit a zadejte název a další podrobnosti. Webové aplikace budou přístupné ze {name}. azurewebsites.net.

![AzureWebApp](./media/image10-2.png)

**Obrázek 10-2.** Vytvoření nové aplikace webové aplikace služby Azure na portálu Azure.

Vaše procesu sestavení CI provede automatizované sestavení vždy, když nový kód se zaměřuje na úložiště správy zdrojového kódu projektu. To vám dává okamžitou zpětnou vazbu, která používá kód (a v ideálním případě předá automatizovaných testů) a potenciálně mohou být nasazeny. Toto sestavení CI vytvoří webového nasazení balíčku artefaktů a publikovat pro používání procesem vašeho disku CD.

[Zadejte vaše CI procesu sestavení](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#ci)

Je nutné povolit průběžnou integraci, systém bude fronty sestavení vždy, když někdo ve vašem týmu potvrdí nový kód. Testování sestavení a ověřte, že ho je vytvoření webového nasazení balíčku jako jeden z jeho artefakty.

Pokud je sestavení úspěšná, váš proces CD nasadí výsledky buildu CI na vaší webové aplikace Azure. To můžete nakonfigurovat, můžete vytvořit a nakonfigurovat *verze*, který bude nasazení do Azure App Service.

[Definovat proces verze vašeho disku CD](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#cd)

Po nakonfigurování svůj CI/CD kanál provést aktualizace webové aplikace a potvrďte je do správy zdrojového kódu k jejich nasazení.

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>Pracovní postup pro vývoj aplikací Azure hostovaná ASP.NET Core

Po nakonfigurování účtu Azure a svůj CI/CD proces vývoje aplikací v Azure hostovaná ASP.NET Core je jednoduché. Následují základní kroky, které obvykle provést při vytváření aplikace ASP.NET Core hostované v Azure App Service jako webovou aplikaci, jak ukazuje obrázek 10-3.

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**Obrázek 10-3.** Krok za krokem pracovního postupu pro vytváření aplikací ASP.NET Core a jejich hostování v Azure

#### <a name="step-1-local-dev-environment-inner-loop"></a>Krok 1. Vnitřní smyčky prostředí místní vývojářů

Vývoj aplikace ASP.NET Core pro nasazení do Azure se neliší od jinak vývoj aplikace. Použijte místní vývojové prostředí, které vám vyhovuje, zda se Visual Studio 2017 nebo dotnet rozhraní příkazového řádku a Visual Studio Code nebo ve svém upřednostňované editoru. Můžete napsat kód, spuštění a ladění změny, spouštění automatizovaných testů a provádět místní potvrzení zdrojového kódu, dokud jste připraveni odešlete své změny se svým úložištěm řízení sdílené zdroje.

#### <a name="step-2-application-code-repository"></a>Krok 2. Úložiště kódu aplikace

Vždy, když budete chtít sdílet kódu se svým týmem, z místního zdroje úložiště by měl odešlete své změny do úložiště sdíleného zdroje vašeho týmu. Pokud pracujete v vlastní firemní pobočky, tento krok obvykle zahrnuje, slučování kódu do sdílené větve (třeba pomocí Řešitele z [žádosti o přijetí změn](https://www.visualstudio.com/docs/git/pull-requests)).

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>Krok 3. Server sestavení: Nepřetržité integrace. Sestavení, Test balíčku

Nové sestavení se aktivuje na buildovacím serveru vždy, když nové potvrzení přišla úložiště kódu sdílené aplikaci. Jako součást procesu CI by měl tento build plně kompilace aplikace a spuštění automatizovaných testů a ověřte, zda že vše funguje podle očekávání. Konečný výsledek procesu položek konfigurace musí být zabalené verze webové aplikace připravené pro nasazení.

#### <a name="step-4-build-server-continuous-delivery"></a>Krok 4. Sestavení serveru: Nastavené průběžné doručování

Po sestavení, protože byla úspěšná, proces CD vyzvedne, až bude sestavení artefaktů vytváří. To bude zahrnovat webového nasazení balíčku. Sestavení serveru bude nasazení tohoto balíčku do služby Azure App Service, nahraďte všechny existující služby se nově vytvořená. Obvykle tento krok cílem pracovní prostředí, ale některé aplikace nasadit přímo do produkčního prostředí prostřednictvím procesu disku CD.

#### <a name="step-5-azure-app-service-web-app"></a>Krok 5. Aplikační služba Azure. Webové aplikace.

Po nasazení aplikace ASP.NET Core běží v kontextu webové aplikace Azure App Service. Tato webová aplikace je možné monitorovat a nakonfigurované pomocí portálu Azure.

#### <a name="step-6-production-monitoring-and-diagnostics"></a>Krok 6. Produkční monitorování a Diagnostika

Když webové aplikace běží, můžete monitorovat stav aplikace a shromažďovat data o chování uživatelů a diagnostiku. Application Insights je zahrnutá v sadě Visual Studio a nabízí automatické instrumentace pro aplikace ASP.NET. Vám může poskytnout s informacemi o využití, výjimky, požadavků, výkonu a protokoly.

## <a name="references"></a>Odkazy

**Sestavení a nasazení vaší aplikace ASP.NET Core do Azure**  
<https://www.VisualStudio.com/docs/Build/Apps/ASPNET/aspnetcore-to-Azure>


>[!div class="step-by-step"]
[Předchozí] (test-asp-net-core-mvc-apps.md) [Další] (azure-hosting-recommendations-for-asp-net-web-apps.md)
