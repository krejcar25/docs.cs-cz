---
title: "Postupy: Definování konstant v jazyce C#"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ff12d0b6882289da9ed924f1c7de00edc5dc1e2e
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="7fab5-102">Postupy: Definování konstant v jazyce C#</span><span class="sxs-lookup"><span data-stu-id="7fab5-102">How to: Define Constants in C#</span></span>
<span data-ttu-id="7fab5-103">Konstanty jsou pole, jejichž hodnoty jsou nastaveny na doba kompilace a nelze je změnit.</span><span class="sxs-lookup"><span data-stu-id="7fab5-103">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="7fab5-104">Pomocí konstanty pro zajištění speciální hodnoty smysluplné názvy místo číselné literály ("čísla magic").</span><span class="sxs-lookup"><span data-stu-id="7fab5-104">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fab5-105">V jazyce C# [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) direktivy preprocesoru nelze použít k definování konstant ve způsobu, jakým se obvykle používá v C a C++.</span><span class="sxs-lookup"><span data-stu-id="7fab5-105">In C# the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="7fab5-106">K definování konstantní hodnoty celočíselných typů (`int`, `byte`a tak dále) použít výčtového typu.</span><span class="sxs-lookup"><span data-stu-id="7fab5-106">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="7fab5-107">Další informace najdete v tématu [výčtu](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="7fab5-107">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="7fab5-108">K definování konstant celé číslo, jeden z přístupů je seskupovat je do jedné statické třídy s názvem `Constants`.</span><span class="sxs-lookup"><span data-stu-id="7fab5-108">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="7fab5-109">To bude vyžadovat, aby všechny odkazy na konstanty být uvedena názvu třídy, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="7fab5-109">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fab5-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="7fab5-110">Example</span></span>  
 [!code-csharp[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 <span data-ttu-id="7fab5-111">Použití kvalifikátor název třídy pomáhá uživatelů použijte konstantu jasné, že je konstantní a nemůže být upraven.</span><span class="sxs-lookup"><span data-stu-id="7fab5-111">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fab5-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="7fab5-112">See Also</span></span>  
 [<span data-ttu-id="7fab5-113">Třídy a struktury</span><span class="sxs-lookup"><span data-stu-id="7fab5-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)