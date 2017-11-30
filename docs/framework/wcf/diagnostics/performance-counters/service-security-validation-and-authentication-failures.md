---
title: "Služba: Počet chyb ověřování zabezpečení"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 808c0d648043df6c5a3dda4646e45ba1492345a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="4a1e4-102">Služba: Počet chyb ověřování zabezpečení</span><span class="sxs-lookup"><span data-stu-id="4a1e4-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="4a1e4-103">Název čítače: počet chyb ověření zabezpečení</span><span class="sxs-lookup"><span data-stu-id="4a1e4-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="4a1e4-104">Popis</span><span class="sxs-lookup"><span data-stu-id="4a1e4-104">Description</span></span>  
 <span data-ttu-id="4a1e4-105">Tento čítač se navyšuje vždy, když zprávu byl odmítnut z důvodu problému zabezpečení nejsou pokryty čítač "Zabezpečení volání není oprávněn".</span><span class="sxs-lookup"><span data-stu-id="4a1e4-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="4a1e4-106">Mezi tyto problémy patří:</span><span class="sxs-lookup"><span data-stu-id="4a1e4-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="4a1e4-107">Token klienta nelze číst ze zprávy.</span><span class="sxs-lookup"><span data-stu-id="4a1e4-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="4a1e4-108">Token klienta se nezdařilo ověření (například,, nesprávné heslo).</span><span class="sxs-lookup"><span data-stu-id="4a1e4-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
-   <span data-ttu-id="4a1e4-109">Ověření podpisu se nezdařila (například,, zprávu s ní bylo neoprávněně).</span><span class="sxs-lookup"><span data-stu-id="4a1e4-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="4a1e4-110">Zpráva je duplicitní z předchozí jeden, který může dojít při útoku formou opakovaného přehrávání.</span><span class="sxs-lookup"><span data-stu-id="4a1e4-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="4a1e4-111">Došlo k selhání dešifrování.</span><span class="sxs-lookup"><span data-stu-id="4a1e4-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="4a1e4-112">Některé elementy (například,, chybějící časové razítko nebo šifrovaná data blokovat) chybí požadované ze zprávy.</span><span class="sxs-lookup"><span data-stu-id="4a1e4-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="4a1e4-113">Během TLSNEGO/SPNEGO metody handshake došlo k chybám.</span><span class="sxs-lookup"><span data-stu-id="4a1e4-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>