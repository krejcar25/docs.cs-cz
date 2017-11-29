---
title: "Ověřování složitosti hesla (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdbe5f385c6b7a0898c4907b0d8afabdaed06fa0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="33293-102">Návod: Ověření, že hesla jsou složitá (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="33293-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="33293-103">Tato metoda zkontroluje některé vlastnosti silného hesla a aktualizace parametr řetězce s informacemi o tom, které kontroluje heslo selže.</span><span class="sxs-lookup"><span data-stu-id="33293-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="33293-104">Hesla lze v zabezpečeném systému k autorizaci uživatele.</span><span class="sxs-lookup"><span data-stu-id="33293-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="33293-105">Hesla musí být ale těžko neoprávnění uživatelé tak snadno uhodnout.</span><span class="sxs-lookup"><span data-stu-id="33293-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="33293-106">Útočníci mohou používat *slovníkové útoky* program, který iteruje v rámci všech slova ve slovníku (nebo více slovník v různých jazycích) a kontroluje, zda některé z slova fungovat jako heslo uživatele.</span><span class="sxs-lookup"><span data-stu-id="33293-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="33293-107">Slabé heslo, například "Určitý fotbalový tým" nebo "Mustang" můžete snadno uhodnout.</span><span class="sxs-lookup"><span data-stu-id="33293-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="33293-108">Silnější hesla, jako například "? Můžete seL1N3vaFiNdMeyeP@sSWerd! ", jsou mnohem méně pravděpodobné, že uhodnout.</span><span class="sxs-lookup"><span data-stu-id="33293-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="33293-109">Systém chráněný heslem se ujistěte, že uživatelé vybrat silná hesla.</span><span class="sxs-lookup"><span data-stu-id="33293-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="33293-110">Silné heslo je komplexní (obsahující směs velká písmena, malá písmena, číselné a speciální znaky) a není slova.</span><span class="sxs-lookup"><span data-stu-id="33293-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="33293-111">Tento příklad ukazuje, jak ověřit složitost.</span><span class="sxs-lookup"><span data-stu-id="33293-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33293-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="33293-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="33293-113">Kód</span><span class="sxs-lookup"><span data-stu-id="33293-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="33293-114">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="33293-114">Compiling the Code</span></span>  
 <span data-ttu-id="33293-115">Tuto metodu volejte předáním řetězec, který obsahuje toto heslo.</span><span class="sxs-lookup"><span data-stu-id="33293-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="33293-116">Tento příklad vyžaduje:</span><span class="sxs-lookup"><span data-stu-id="33293-116">This example requires:</span></span>  
  
-   <span data-ttu-id="33293-117">Přístup k členům <xref:System.Text.RegularExpressions> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="33293-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="33293-118">Přidat `Imports` příkaz, pokud jste nejsou kvalifikující plně názvy členů v kódu.</span><span class="sxs-lookup"><span data-stu-id="33293-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="33293-119">Další informace najdete v tématu [příkaz Imports (Namespace .NET a typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="33293-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="33293-120">Zabezpečení</span><span class="sxs-lookup"><span data-stu-id="33293-120">Security</span></span>  
 <span data-ttu-id="33293-121">Pokud přesouváte hesla přes síť, budete muset použít bezpečnou metodu pro přenášení dat.</span><span class="sxs-lookup"><span data-stu-id="33293-121">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="33293-122">Další informace najdete v tématu [zabezpečení webové aplikace ASP.NET](https://msdn.microsoft.com/library/330a99hc).</span><span class="sxs-lookup"><span data-stu-id="33293-122">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="33293-123">Můžete zvýšit jeho přesnost `ValidatePassword` funkce přidáním další složitosti kontroly:</span><span class="sxs-lookup"><span data-stu-id="33293-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="33293-124">Porovnejte heslo a jeho dílčích řetězců proti jméno uživatele, identifikátor uživatele a slovníku definované aplikací.</span><span class="sxs-lookup"><span data-stu-id="33293-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="33293-125">Kromě toho považovat za vizuálně podobné znaky ekvivalentní při provádění porovnání.</span><span class="sxs-lookup"><span data-stu-id="33293-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="33293-126">Například považovat za písmena "l" a "e" ekvivalentní číslice "1" a "3".</span><span class="sxs-lookup"><span data-stu-id="33293-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="33293-127">Pokud je jenom jedno velké písmeno, ujistěte se, že se nejedná o první znak hesla.</span><span class="sxs-lookup"><span data-stu-id="33293-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="33293-128">Zajistěte, aby poslední dva znaky hesla byla písmeno znaků.</span><span class="sxs-lookup"><span data-stu-id="33293-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="33293-129">Nepovolit hesla, ve kterých jsou všechny symboly vstup z klávesnice na horní řádek.</span><span class="sxs-lookup"><span data-stu-id="33293-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33293-130">Viz také</span><span class="sxs-lookup"><span data-stu-id="33293-130">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex>  
 [<span data-ttu-id="33293-131">Zabezpečení webové aplikace ASP.NET</span><span class="sxs-lookup"><span data-stu-id="33293-131">ASP.NET Web Application Security</span></span>](https://msdn.microsoft.com/library/330a99hc)