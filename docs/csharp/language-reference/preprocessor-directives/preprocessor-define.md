---
title: "#<a name=\"define-c-reference\"></a>definování (referenční dokumentace jazyka C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#define'
helpviewer_keywords: '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ae72a1b6c19421c51348a0d93691ba3fe29a191c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="define-c-reference"></a>#define (referenční dokumentace jazyka C#)
Používáte `#define` k definování symbol. Při použití symbol jako výraz, který je předán [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) direktivy, výraz vyhodnotí jako `true`, jak ukazuje následující příklad:  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a>Poznámky  
  
> [!NOTE]
>  `#define` – Direktiva nelze použít k deklarace konstantní hodnoty, což se většinou děje jazyka C a C++. Konstanty v jazyku C# jsou nejlépe definované jako statické členy třídě nebo struktuře. Pokud máte několik takové konstanty, zvažte vytvoření samostatné třídy "Konstanty" k jejich umístění.  
  
 Symboly můžete použít k určení podmínek pro kompilaci. Můžete otestovat pro symbol s buď [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) nebo [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md). Můžete také `conditional` atribut provést Podmíněná kompilace.  
  
 Můžete definovat symbol, ale nelze přiřadit hodnotu symbol. `#define` – Direktiva musí být v souboru dříve, než použijete žádné pokyny, které nejsou také preprocesor – direktivy.  
  
 Můžete také definovat symbol s [/ define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) – možnost kompilátoru. Můžete nedefinované symbol s [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
 Symbol, který definujete s `/define` nebo s `#define` není v konfliktu s proměnné se stejným názvem. To znamená název proměnné nesmí být předaný direktivy preprocesoru a symbol lze vyhodnotit pouze direktivy preprocesoru.  
  
 Rozsah symbol, který byl vytvořen pomocí `#define` je soubor, ve které byla definována symbolu.  
  
 Jak ukazuje následující příklad, musíte umístit `#define` direktivy v horní části souboru.  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 Příklad toho, jak nedefinované symbol, naleznete v části [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace jazyka C#](../../../csharp/language-reference/index.md)  
 [Průvodce programováním v C#](../../../csharp/programming-guide/index.md)  
 [C# direktivy preprocesoru](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [Const](../../../csharp/language-reference/keywords/const.md)  
 [Postupy: Podmíněná kompilace pomocí trasování a ladění](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)  
 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
