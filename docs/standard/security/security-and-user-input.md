---
title: "Zabezpečení a uživatelský vstup"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [.NET Framework], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 804b91cdda1316bc0a3081c8353493faf8869b4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-user-input"></a><span data-ttu-id="3a247-102">Zabezpečení a uživatelský vstup</span><span class="sxs-lookup"><span data-stu-id="3a247-102">Security and User Input</span></span>
<span data-ttu-id="3a247-103">Uživatelská data, která je jakýkoli druh vstupních (datových z webové žádosti nebo adresa URL, zadejte do ovládacích prvků formulářové aplikace Windows, a tak dále), může nepříznivě ovlivnit kód, protože často se budou používat přímo jako parametry pro volání jiného kódu.</span><span class="sxs-lookup"><span data-stu-id="3a247-103">User data, which is any kind of input (data from a Web request or URL, input to controls of a Microsoft Windows Forms application, and so on), can adversely influence code because often that data is used directly as parameters to call other code.</span></span> <span data-ttu-id="3a247-104">Tato situace je obdobou škodlivý kód volání kódu s neobvyklé parametry a stejná opatření by měla být provedena.</span><span class="sxs-lookup"><span data-stu-id="3a247-104">This situation is analogous to malicious code calling your code with strange parameters, and the same precautions should be taken.</span></span> <span data-ttu-id="3a247-105">Uživatelský vstup je ve skutečnosti těžší zabezpečit, protože neexistuje žádný rámec zásobníku pro sledování přítomnost potenciálně nedůvěryhodné data.</span><span class="sxs-lookup"><span data-stu-id="3a247-105">User input is actually harder to make safe because there is no stack frame to trace the presence of the potentially untrusted data.</span></span>  
  
 <span data-ttu-id="3a247-106">Toto jsou mezi chyby zabezpečení nejdelikátnější a nejtěžší najít, protože mohou existovat v kódu, který je zdánlivě nesouvisí se zabezpečením, jsou bránu chybná data prostřednictvím předat jiný kód.</span><span class="sxs-lookup"><span data-stu-id="3a247-106">These are among the subtlest and hardest security bugs to find because, although they can exist in code that is seemingly unrelated to security, they are a gateway to pass bad data through to other code.</span></span> <span data-ttu-id="3a247-107">Chcete-li vyhledat tyto chyby, postupujte podle jakýkoli druh vstupních dat, představte si, co rozsahu možných hodnot může být a zvažte, zda kód zobrazuje tato data můžete zpracovat všechny tyto případy.</span><span class="sxs-lookup"><span data-stu-id="3a247-107">To look for these bugs, follow any kind of input data, imagine what the range of possible values might be, and consider whether the code seeing this data can handle all those cases.</span></span> <span data-ttu-id="3a247-108">Můžete je vyřešit tyto chyby prostřednictvím rozsah kontroly a odmítat všechny vstupní kód nelze zpracovat.</span><span class="sxs-lookup"><span data-stu-id="3a247-108">You can fix these bugs through range checking and rejecting any input the code cannot handle.</span></span>  
  
 <span data-ttu-id="3a247-109">Některé důležité aspekty zahrnující uživatelská data zahrnují následující:</span><span class="sxs-lookup"><span data-stu-id="3a247-109">Some important considerations involving user data include the following:</span></span>  
  
-   <span data-ttu-id="3a247-110">Žádná data uživatelů v odpovědi serveru běží v kontextu serveru lokality na straně klienta.</span><span class="sxs-lookup"><span data-stu-id="3a247-110">Any user data in a server response runs in the context of the server's site on the client.</span></span> <span data-ttu-id="3a247-111">Pokud váš webový server zpracovává uživatelská data a vloží ho do vrácené webové stránky, může například obsahovat  **\<skriptu >** značky a spustit jako, pokud ze serveru.</span><span class="sxs-lookup"><span data-stu-id="3a247-111">If your Web server takes user data and inserts it into the returned Web page, it might, for example, include a **\<script>** tag and run as if from the server.</span></span>  
  
-   <span data-ttu-id="3a247-112">Mějte na paměti, že klient může vyžadovat libovolná adresa URL.</span><span class="sxs-lookup"><span data-stu-id="3a247-112">Remember that the client can request any URL.</span></span>  
  
-   <span data-ttu-id="3a247-113">Vezměte v úvahu podvodné nebo neplatné cesty:</span><span class="sxs-lookup"><span data-stu-id="3a247-113">Consider tricky or invalid paths:</span></span>  
  
    -   <span data-ttu-id="3a247-114">.. \, extrémně dlouhé cesty.</span><span class="sxs-lookup"><span data-stu-id="3a247-114">..\ , extremely long paths.</span></span>  
  
    -   <span data-ttu-id="3a247-115">Použití zástupných znaků (*).</span><span class="sxs-lookup"><span data-stu-id="3a247-115">Use of wild card characters (*).</span></span>  
  
    -   <span data-ttu-id="3a247-116">Rozšíření tokenu (% token %).</span><span class="sxs-lookup"><span data-stu-id="3a247-116">Token expansion (%token%).</span></span>  
  
    -   <span data-ttu-id="3a247-117">Neobvyklé formy cesty se zvláštní význam.</span><span class="sxs-lookup"><span data-stu-id="3a247-117">Strange forms of paths with special meaning.</span></span>  
  
    -   <span data-ttu-id="3a247-118">Alternativní názvy datového proudu systému souborů, jako například `filename::$DATA`.</span><span class="sxs-lookup"><span data-stu-id="3a247-118">Alternate file system stream names such as `filename::$DATA`.</span></span>  
  
    -   <span data-ttu-id="3a247-119">Krátké verze názvů souborů, například `longfi~1` pro `longfilename`.</span><span class="sxs-lookup"><span data-stu-id="3a247-119">Short versions of file names such as `longfi~1` for `longfilename`.</span></span>  
  
-   <span data-ttu-id="3a247-120">Mějte na paměti, že Eval(userdata) může udělat nic.</span><span class="sxs-lookup"><span data-stu-id="3a247-120">Remember that Eval(userdata) can do anything.</span></span>  
  
-   <span data-ttu-id="3a247-121">Buďte opatrní, dynamické vazby název, který obsahuje některá uživatelská data.</span><span class="sxs-lookup"><span data-stu-id="3a247-121">Be wary of late binding to a name that includes some user data.</span></span>  
  
-   <span data-ttu-id="3a247-122">Pokud chcete pracovat s daty Web, zvažte různé formy řídicí sekvence, které jsou přípustné, včetně:</span><span class="sxs-lookup"><span data-stu-id="3a247-122">If you are dealing with Web data, consider the various forms of escapes that are permissible, including:</span></span>  
  
    -   <span data-ttu-id="3a247-123">Šestnáctková řídicí sekvence (% nn).</span><span class="sxs-lookup"><span data-stu-id="3a247-123">Hexadecimal escapes (%nn).</span></span>  
  
    -   <span data-ttu-id="3a247-124">Řídicí sekvence Unicode (% nnn).</span><span class="sxs-lookup"><span data-stu-id="3a247-124">Unicode escapes (%nnn).</span></span>  
  
    -   <span data-ttu-id="3a247-125">Příliš dlouhého UTF-8 řídicí sekvence (% nn % nn).</span><span class="sxs-lookup"><span data-stu-id="3a247-125">Overlong UTF-8 escapes (%nn%nn).</span></span>  
  
    -   <span data-ttu-id="3a247-126">Dvojité řídicí sekvence (% nn stane mmnn %, kde % mm je řídicí pro '%').</span><span class="sxs-lookup"><span data-stu-id="3a247-126">Double escapes (%nn becomes %mmnn, where %mm is the escape for '%').</span></span>  
  
-   <span data-ttu-id="3a247-127">Věnujte pozornost uživatelská jména, která může mít více než jeden kanonický formát.</span><span class="sxs-lookup"><span data-stu-id="3a247-127">Be wary of user names that might have more than one canonical format.</span></span> <span data-ttu-id="3a247-128">Například můžete často použít buď MOJEDOMÉNA\\*uživatelské jméno* formuláře nebo *uživatelské jméno* @mydomain.example.com formuláře.</span><span class="sxs-lookup"><span data-stu-id="3a247-128">For example, you can often use either the MYDOMAIN\\*username* form or the *username*@mydomain.example.com form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a247-129">Viz také</span><span class="sxs-lookup"><span data-stu-id="3a247-129">See Also</span></span>  
 [<span data-ttu-id="3a247-130">Pokyny pro zabezpečené kódování</span><span class="sxs-lookup"><span data-stu-id="3a247-130">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)