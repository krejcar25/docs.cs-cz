---
title: "Volba mezi tradiční webové aplikace a jednostránkové aplikace"
description: "Architekti moderních webových aplikací pomocí ASP.NET Core a Microsoft Azure"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 5bae77fc4e0df9d0bc7fecfad25adfcee2419084
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/21/2017
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a><span data-ttu-id="6a4ee-103">Volba mezi tradiční webové aplikace a jednostránkové aplikace (SPA)</span><span class="sxs-lookup"><span data-stu-id="6a4ee-103">Choose Between Traditional Web Apps and Single Page Apps (SPAs)</span></span>

> <span data-ttu-id="6a4ee-104">"Je Atwood zákonem: jakékoli aplikace, která může být napsán v jazyce JavaScript, zapíšou nakonec v jazyce JavaScript."</span><span class="sxs-lookup"><span data-stu-id="6a4ee-104">"Atwood's Law: Any application that can be written in JavaScript, will eventually be written in JavaScript."</span></span>  
> <span data-ttu-id="6a4ee-105">_\-Jeff Atwood_</span><span class="sxs-lookup"><span data-stu-id="6a4ee-105">_\- Jeff Atwood_</span></span>

## <a name="summary"></a><span data-ttu-id="6a4ee-106">Souhrn</span><span class="sxs-lookup"><span data-stu-id="6a4ee-106">Summary</span></span>

<span data-ttu-id="6a4ee-107">Existují dvě obecné metody vytvářet webové aplikace ještě dnes: tradiční webových aplikací, které provádějí většinu logiku aplikace na serveru a jednostránkové aplikace (SPA), které provádějí většinu logiku uživatelského rozhraní ve webovém prohlížeči, komunikuje s webovým serverem, především pomocí webového rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-107">There are two general approaches to building web applications today: traditional web applications that perform most of the application logic on the server, and single page applications (SPAs) that perform most of the user interface logic in a web browser, communicating with the web server primarily using web APIs.</span></span> <span data-ttu-id="6a4ee-108">Hybridní přístup je také možné, nejjednodušší se hostitele jednu nebo více bohaté SPA jako dílčí aplikací v rámci větší tradiční webové aplikace.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-108">A hybrid approach is also possible, the simplest being host one or more rich SPA-like sub-applications within a larger traditional web application.</span></span>

<span data-ttu-id="6a4ee-109">Měli byste použít tradiční webové aplikace při:</span><span class="sxs-lookup"><span data-stu-id="6a4ee-109">You should use traditional web applications when:</span></span>

-   <span data-ttu-id="6a4ee-110">Požadavky na straně klienta aplikace jsou jednoduchý nebo i jen pro čtení.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-110">Your application's client-side requirements are simple or even read-only.</span></span>

-   <span data-ttu-id="6a4ee-111">Aplikace musí fungovat v prohlížečích bez podpory jazyka JavaScript.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-111">Your application needs to function in browsers without JavaScript support.</span></span>

-   <span data-ttu-id="6a4ee-112">Váš tým je obeznámeni s JavaScript nebo TypeScript technik vývoje.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-112">Your team is unfamiliar with JavaScript or TypeScript development techniques.</span></span>

<span data-ttu-id="6a4ee-113">Měli byste použít SPA při:</span><span class="sxs-lookup"><span data-stu-id="6a4ee-113">You should use a SPA when:</span></span>

-   <span data-ttu-id="6a4ee-114">Aplikace musí vystavit bohaté uživatelské rozhraní s mnoha funkcemi.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-114">Your application must expose a rich user interface with many features.</span></span>

-   <span data-ttu-id="6a4ee-115">Váš tým je obeznámeni s vývojem pro JavaScript a TypeScript.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-115">Your team is familiar with JavaScript and/or TypeScript development.</span></span>

-   <span data-ttu-id="6a4ee-116">Aplikace musí již zveřejňují rozhraní API pro ostatní klienty (interní nebo veřejná).</span><span class="sxs-lookup"><span data-stu-id="6a4ee-116">Your application must already expose an API for other (internal or public) clients.</span></span>

<span data-ttu-id="6a4ee-117">Navíc vyžadují větší SPA architektury architektury a odborných znalosti zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-117">Additionally, SPA frameworks require greater architectural and security expertise.</span></span> <span data-ttu-id="6a4ee-118">Dojde k větší změn z důvodu časté aktualizace a nové rozhraní než tradiční webových aplikací.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-118">They experience greater churn due to frequent updates and new frameworks than traditional web applications.</span></span> <span data-ttu-id="6a4ee-119">Konfigurace automatizované procesy sestavení a nasazení a použití možnosti nasazení jako kontejnery jsou s aplikacemi SPA obtížnější než tradiční webové aplikace.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-119">Configuring automated build and deployment processes and utilizing deployment options like containers are more difficult with SPA applications than traditional web apps.</span></span>

<span data-ttu-id="6a4ee-120">Vylepšení v možné díky modelu SPA činnost koncového uživatele je nutné porovnat těchto aspektů.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-120">Improvements in user experience made possible by SPA model must be weighed against these considerations.</span></span>

## <a name="when-to-choose-traditional-web-apps"></a><span data-ttu-id="6a4ee-121">Kdy použít tradiční webové aplikace</span><span class="sxs-lookup"><span data-stu-id="6a4ee-121">When to choose traditional web apps</span></span>

<span data-ttu-id="6a4ee-122">Následuje podrobnější vysvětlení dříve uvádí důvody pro výběr tradiční webových aplikací.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-122">The following is a more detailed explanation of the previously-stated reasons for picking traditional web applications.</span></span>

<span data-ttu-id="6a4ee-123">**Aplikace má požadavky na jednoduchý, může být jen pro čtení, straně klienta**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-123">**Your application has simple, possibly read-only, client-side requirements**</span></span>

<span data-ttu-id="6a4ee-124">Mnoho webových aplikací jsou primárně spotřebovávána způsobem jen pro čtení valná většina uživatelů.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-124">Many web applications are primarily consumed in a read-only fashion by the vast majority of their users.</span></span> <span data-ttu-id="6a4ee-125">Jen pro čtení (nebo pro čtení – většinou) aplikace jsou obvykle mnohem jednodušší než ty, které udržují a manipulaci s značnou část stavu.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-125">Read-only (or read-mostly) applications tend to be much simpler than those that maintain and manipulate a great deal of state.</span></span> <span data-ttu-id="6a4ee-126">Vyhledávací může například obsahovat jeden vstupní bod se textové pole a druhá stránka pro zobrazení výsledků vyhledávání.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-126">For example, a search engine might consist of a single entry point with a textbox and a second page for displaying search results.</span></span> <span data-ttu-id="6a4ee-127">Anonymní uživatelé snadno provádět požadavky a je nutné pro logiku na straně klienta.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-127">Anonymous users can easily make requests, and there is little need for client-side logic.</span></span> <span data-ttu-id="6a4ee-128">Podobně blogu nebo obsah systém správy je veřejná aplikace obvykle obsahuje především obsah s malým množstvím chování klienta.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-128">Likewise, a blog or content management system's public-facing application usually consists mainly of content with little client-side behavior.</span></span> <span data-ttu-id="6a4ee-129">Jsou takové aplikace snadno vytvořené jako tradiční na serveru webové aplikace, které provádět logiku na webovém serveru a vykreslení HTML, který se má zobrazit v prohlížeči.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-129">Such applications are easily built as traditional server-based web applications which perform logic on the web server and render HTML to be displayed in the browser.</span></span> <span data-ttu-id="6a4ee-130">Vymazat výhodu v těchto scénářích má také skutečnost, že každý jedinečný stránce webu má svou vlastní adresu URL, která může být aktuálně přihlášeni a indexovaný vyhledávači (ve výchozím nastavení, aniž by bylo nutné přidat jako samostatný prvek aplikace).</span><span class="sxs-lookup"><span data-stu-id="6a4ee-130">The fact that each unique page of the site has its own URL that can be bookmarked and indexed by search engines (by default, without having to add this as a separate feature of the application) is also a clear benefit in such scenarios.</span></span>

<span data-ttu-id="6a4ee-131">**Aplikace musí fungovat v prohlížečích bez podpory jazyka JavaScript**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-131">**Your application needs to function in browsers without JavaScript support**</span></span>

<span data-ttu-id="6a4ee-132">Webové aplikace, které je potřeba fungovat v prohlížečích s omezeným nebo bez podpory jazyka JavaScript by měly být zapsány pomocí pracovních postupů tradiční webové aplikace (nebo alespoň moct vrátit zpět k takové chování).</span><span class="sxs-lookup"><span data-stu-id="6a4ee-132">Web applications that need to function in browsers with limited or no JavaScript support should be written using traditional web app workflows (or at least be able to fall back to such behavior).</span></span> <span data-ttu-id="6a4ee-133">SPA vyžadují JavaScript na straně klienta, chcete-li funkce; Pokud není k dispozici, nejsou SPA dobrou volbou.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-133">SPAs require client-side JavaScript in order to function; if it's not available, SPAs are not a good choice.</span></span>

<span data-ttu-id="6a4ee-134">**Je-li obeznámeni s JavaScript nebo TypeScript technik vývoje váš tým**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-134">**Your team is unfamiliar with JavaScript or TypeScript development techniques**</span></span>

<span data-ttu-id="6a4ee-135">Pokud váš tým obeznámeni s JavaScript nebo TypeScript, ale je obeznámeni s vývoj webové serverové aplikace, pravděpodobně budou moct rychleji než SPA poskytovat tradiční webové aplikace.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-135">If your team is unfamiliar with JavaScript or TypeScript, but is familiar with server-side web application development, then they will probably be able to deliver a traditional web app more quickly than a SPA.</span></span> <span data-ttu-id="6a4ee-136">Není-li learning k programu SPA cílem, nebo se vyžaduje uživatelské prostředí poskytované SPA, tradiční webové aplikace jsou vyšší produktivitu výběru týmům, kteří jsou již obeznámeni s jejich vytváření.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-136">Unless learning to program SPAs is a goal, or the user experience afforded by a SPA is required, traditional web apps are a more productive choice for teams who are already familiar with building them.</span></span>

## <a name="when-to-choose-spas"></a><span data-ttu-id="6a4ee-137">Když chcete-li zvolit SPA</span><span class="sxs-lookup"><span data-stu-id="6a4ee-137">When to choose SPAs</span></span>

<span data-ttu-id="6a4ee-138">Následuje podrobnější vysvětlení kdy zvolit styl jednostránkové aplikace vývoje pro vaši webovou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-138">The following is a more detailed explanation of when to choose a Single Page Applications style of development for your web app.</span></span>

<span data-ttu-id="6a4ee-139">**Aplikace musí vystavit bohaté uživatelské rozhraní s mnoha funkcemi**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-139">**Your application must expose a rich user interface with many features**</span></span>

<span data-ttu-id="6a4ee-140">SPA může podporovat bohaté funkce klienta, které nevyžaduje opětovné načtení stránky, když uživatelé provést akce nebo přejděte mezi oblastmi aplikace.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-140">SPAs can support rich client-side functionality that doesn't require reloading the page as users take actions or navigate between areas of the app.</span></span> <span data-ttu-id="6a4ee-141">SPA můžete načítat rychleji, načítání dat na pozadí, a akce jednotlivých uživatelů jsou rychlejšího vzhledem k tomu, že vyskytují jen vzácně zavážky celou stránku.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-141">SPAs can load more quickly, fetching data in the background, and individual user actions are more responsive since full page reloads are rare.</span></span> <span data-ttu-id="6a4ee-142">SPA může podporovat přírůstkové aktualizace, aniž by uživatel musel klikněte na tlačítko pro odeslání formuláře ukládání částečně vyplněné formuláře nebo dokumenty.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-142">SPAs can support incremental updates, saving partially completed forms or documents without the user having to click a button to submit a form.</span></span> <span data-ttu-id="6a4ee-143">Bohaté chování klienta, jako je například přetahování myší, může podporovat SPA mnohem snadněji než tradiční aplikace.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-143">SPAs can support rich client-side behaviors, such as drag-and-drop, much more readily than traditional applications.</span></span> <span data-ttu-id="6a4ee-144">SPA můžete určený ke spouštění v odpojeném režimu, provedení aktualizace na straně klienta model, který se nakonec synchronizují zpět na server, jakmile se znovu navázané připojení.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-144">SPAs can be designed to run in a disconnected mode, making updates to a client-side model that are eventually synchronized back to the server once a connection is re-established.</span></span> <span data-ttu-id="6a4ee-145">Pokud vaše aplikace požadavky zahrnují bohaté funkce, která přesahuje co nabízí typické formuláře HTML, měli byste vybrat k SPA styl aplikaci.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-145">You should choose a SPA style application if your app's requirements include rich functionality that goes beyond what typical HTML forms offer.</span></span>

<span data-ttu-id="6a4ee-146">Všimněte si, že často SPA nutné implementovat funkce, které jsou integrované v tradiční webové aplikace, například zobrazení smysluplný adresy URL na adresu panelu odrážející aktuální operace (a umožní uživatelům záložku nebo přímý odkaz na tuto adresu URL pro návrat do něj).</span><span class="sxs-lookup"><span data-stu-id="6a4ee-146">Note that frequently SPAs need to implement features that are built-in to traditional web apps, such as displaying a meaningful URL in the address bar reflecting the current operation (and allowing users to bookmark or deep link to this URL to return to it).</span></span> <span data-ttu-id="6a4ee-147">SPA také měli povolit uživatelům používat tlačítka vpřed a zpět v prohlížeči s výsledky, které nebudou neohlášeného je.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-147">SPAs also should allow users to use the browser's back and forward buttons with results that won't surprise them.</span></span>

<span data-ttu-id="6a4ee-148">**Je váš tým obeznámeni s vývojem pro JavaScript a TypeScript**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-148">**Your team is familiar with JavaScript and/or TypeScript development**</span></span>

<span data-ttu-id="6a4ee-149">Zápis SPA vyžaduje znalost jazyka JavaScript a TypeScript a způsobů programování na straně klienta a knihovny.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-149">Writing SPAs requires familiarity with JavaScript and/or TypeScript and client-side programming techniques and libraries.</span></span> <span data-ttu-id="6a4ee-150">Váš tým musí být příslušný zápis moderní JavaScriptu pomocí rozhraní SPA jako úhlová.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-150">Your team should be competent in writing modern JavaScript using a SPA framework like Angular.</span></span>

> ### <a name="references--spa-frameworks"></a><span data-ttu-id="6a4ee-151">Odkazy – SPA architektury</span><span class="sxs-lookup"><span data-stu-id="6a4ee-151">References – SPA Frameworks</span></span>
> - <span data-ttu-id="6a4ee-152">**AngularJS**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-152">**AngularJS**</span></span>  
> <span data-ttu-id="6a4ee-153"><https://angularjs.org/></span><span class="sxs-lookup"><span data-stu-id="6a4ee-153"><https://angularjs.org/></span></span>
> - <span data-ttu-id="6a4ee-154">**Porovnání 4 rámci oblíbených jazyka JavaScript**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-154">**Comparison of 4 Popular JavaScript Frameworks**</span></span>  
> <span data-ttu-id="6a4ee-155"><https://www.developereconomics.com/Feature-Comparison-of-4-Popular-js-mV-Frameworks></span><span class="sxs-lookup"><span data-stu-id="6a4ee-155"><https://www.developereconomics.com/feature-comparison-of-4-popular-js-mv-frameworks></span></span>

<span data-ttu-id="6a4ee-156">**Aplikace musí již zveřejňují rozhraní API pro ostatní klienty (interní nebo veřejná)**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-156">**Your application must already expose an API for other (internal or public) clients**</span></span>

<span data-ttu-id="6a4ee-157">Pokud jste již podporujete webové rozhraní API pro ostatní klienty, může vyžadovat méně úsilí pro vytvoření SPA implementace, která využívá tato rozhraní API místo reprodukci logiku ve formuláři na straně serveru.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-157">If you're already supporting a web API for use by other clients, it may require less effort to create a SPA implementation that leverages these APIs rather than reproducing the logic in server-side form.</span></span> <span data-ttu-id="6a4ee-158">SPA zkontrolujte rozsáhlé používání webových rozhraní API pro dotazování a aktualizace dat, jak uživatelé pracují s aplikací.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-158">SPAs make extensive use of web APIs to query and update data as users interact with the application.</span></span>

## <a name="decision-table--traditional-web-or-spa"></a><span data-ttu-id="6a4ee-159">Rozhodovací tabulky – tradiční Web nebo SPA</span><span class="sxs-lookup"><span data-stu-id="6a4ee-159">Decision table – Traditional Web or SPA</span></span>

<span data-ttu-id="6a4ee-160">Následující rozhodnutí tabulka shrnuje některé základní faktorů, které je třeba zvážit při výběru mezi tradiční webové aplikace a SPA.</span><span class="sxs-lookup"><span data-stu-id="6a4ee-160">The following decision table summarizes some of the basic factors to consider when choosing between a traditional web application and a SPA.</span></span>

  | <span data-ttu-id="6a4ee-161">**Koeficient**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-161">**Factor**</span></span> | <span data-ttu-id="6a4ee-162">**Tradiční webové aplikace**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-162">**Traditional Web App**</span></span> | <span data-ttu-id="6a4ee-163">**Jednostránkové aplikace**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-163">**Single Page Application**</span></span> |
  |---|---|---|
  | <span data-ttu-id="6a4ee-164">Požadované Team znalost jazyka JavaScript nebo TypeScript</span><span class="sxs-lookup"><span data-stu-id="6a4ee-164">Required Team Familiarity with JavaScript/TypeScript</span></span> | <span data-ttu-id="6a4ee-165">**Minimální**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-165">**Minimal**</span></span> | <span data-ttu-id="6a4ee-166">**Požadované**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-166">**Required**</span></span> |
  | <span data-ttu-id="6a4ee-167">Podpora prohlížeče bez skriptování</span><span class="sxs-lookup"><span data-stu-id="6a4ee-167">Support Browsers without Scripting</span></span> | <span data-ttu-id="6a4ee-168">**Podporované**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-168">**Supported**</span></span> | <span data-ttu-id="6a4ee-169">**Nepodporuje se**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-169">**Not Supported**</span></span> |
  | <span data-ttu-id="6a4ee-170">Chování minimální aplikace na straně klienta</span><span class="sxs-lookup"><span data-stu-id="6a4ee-170">Minimal Client-Side Application Behavior</span></span> | <span data-ttu-id="6a4ee-171">**Vhodným**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-171">**Well-Suited**</span></span> | <span data-ttu-id="6a4ee-172">**Přehnaně**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-172">**Overkill**</span></span> |
  | <span data-ttu-id="6a4ee-173">Požadavky na bohatou a komplexní uživatelské rozhraní</span><span class="sxs-lookup"><span data-stu-id="6a4ee-173">Rich, Complex User Interface Requirements</span></span> | <span data-ttu-id="6a4ee-174">**Omezené**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-174">**Limited**</span></span> | <span data-ttu-id="6a4ee-175">**Vhodným**</span><span class="sxs-lookup"><span data-stu-id="6a4ee-175">**Well-Suited**</span></span> |

>[!div class="step-by-step"]
<span data-ttu-id="6a4ee-176">[Předchozí] (moderních web aplikace characteristics.md) [další](architectural-principles.md)</span><span class="sxs-lookup"><span data-stu-id="6a4ee-176">[Previous] (modern-web-applications-characteristics.md) [Next](architectural-principles.md)</span></span>