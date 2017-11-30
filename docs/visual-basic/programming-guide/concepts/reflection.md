---
title: Reflexe (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b7b94e25d2ca9563cd50f454c94092f18e295863
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="reflection-visual-basic"></a><span data-ttu-id="53a66-102">Reflexe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53a66-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="53a66-103">Reflexe poskytuje objekty (typu <xref:System.Type>) popisují sestavení, moduly a typy.</span><span class="sxs-lookup"><span data-stu-id="53a66-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="53a66-104">Reflexe můžete dynamicky vytvořit instanci typu, typ vazby s existujícím objektem, nebo z existujícího objektu získat typ a volat její metody nebo přístup k jeho polí a vlastností.</span><span class="sxs-lookup"><span data-stu-id="53a66-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="53a66-105">Pokud používáte atributy ve vašem kódu, reflexe umožňuje přistupovat k nim.</span><span class="sxs-lookup"><span data-stu-id="53a66-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="53a66-106">Další informace najdete v tématu [atributy](https://msdn.microsoft.com/library/5x6cd29c).</span><span class="sxs-lookup"><span data-stu-id="53a66-106">For more information, see [Attributes](https://msdn.microsoft.com/library/5x6cd29c).</span></span>  
  
 <span data-ttu-id="53a66-107">Zde je jednoduchý příklad použití statické metody reflexe `GetType` – zděděné z pro všechny typy `Object` základní třída - získat požadovaný typ proměnné:</span><span class="sxs-lookup"><span data-stu-id="53a66-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="53a66-108">Výstup je:</span><span class="sxs-lookup"><span data-stu-id="53a66-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="53a66-109">Následující příklad používá reflexe získat úplný název načíst sestavení.</span><span class="sxs-lookup"><span data-stu-id="53a66-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="53a66-110">Výstup je:</span><span class="sxs-lookup"><span data-stu-id="53a66-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="53a66-111">Přehled reflexe</span><span class="sxs-lookup"><span data-stu-id="53a66-111">Reflection Overview</span></span>  
 <span data-ttu-id="53a66-112">Reflexe je užitečné v následujících situacích:</span><span class="sxs-lookup"><span data-stu-id="53a66-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="53a66-113">Pokud máte přístup k atributům v metadatech vašeho programu.</span><span class="sxs-lookup"><span data-stu-id="53a66-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="53a66-114">Další informace najdete v tématu [načítání informace uložené v atributech](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="53a66-114">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="53a66-115">Pro zkoumání a vytváření instancí typy v sestavení.</span><span class="sxs-lookup"><span data-stu-id="53a66-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="53a66-116">Pro vytváření nových typů za běhu.</span><span class="sxs-lookup"><span data-stu-id="53a66-116">For building new types at runtime.</span></span> <span data-ttu-id="53a66-117">Použití třídy v <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="53a66-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="53a66-118">K provedení pozdní vazba, přístup k metody pro typy vytvořené v době běhu.</span><span class="sxs-lookup"><span data-stu-id="53a66-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="53a66-119">Podívejte se na téma [dynamické načtení a použití typů](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="53a66-119">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="53a66-120">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="53a66-120">Related Sections</span></span>  
 <span data-ttu-id="53a66-121">Další informace:</span><span class="sxs-lookup"><span data-stu-id="53a66-121">For more information:</span></span>  
  
-   [<span data-ttu-id="53a66-122">Reflexe</span><span class="sxs-lookup"><span data-stu-id="53a66-122">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="53a66-123">Zobrazení informací o typu</span><span class="sxs-lookup"><span data-stu-id="53a66-123">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="53a66-124">Reflexe a obecné typy</span><span class="sxs-lookup"><span data-stu-id="53a66-124">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="53a66-125">Načítání informací uložených v atributech</span><span class="sxs-lookup"><span data-stu-id="53a66-125">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="53a66-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="53a66-126">See Also</span></span>  
 [<span data-ttu-id="53a66-127">Průvodce programováním v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53a66-127">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="53a66-128">Sestavení v modulu Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="53a66-128">Assemblies in the Common Language Runtime</span></span>](https://msdn.microsoft.com/library/k3677y81)