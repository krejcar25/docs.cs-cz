---
title: "Derivované matematické funkce (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5816fa4c8c384eca116fa1512950a3588c6e3392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="derived-math-functions-visual-basic"></a>Derivované matematické funkce (Visual Basic)
V následující tabulce jsou jiné než vnitřní matematické funkce, které může být odvozen od vnitřní matematické funkce <xref:System.Math?displayProperty=nameWithType> objektu. Vnitřní matematické funkce dostanete tak, že přidáte `Imports System.Math` do souboru nebo projektu.  
  
|Funkce|Odvozené ekvivalenty|  
|--------------|-------------------------|  
|Secant – (Sec(x))|1 / Cos(x)|  
|Cosecant – (Csc(x))|1 / Sin(x)|  
|Kotangens (Ctan(x))|1 / Tan(x)|  
|Inverzní sinus (Asin(x))|Atan (x nebo Sqrt (-x * x + 1))|  
|Inverzní kosinus (Acos(x))|Atan (-x nebo Sqrt (-x * x + 1)) + 2 \* Atan(1)|  
|Inverzní secant – (Asec(x))|2 * Atan(1) – Atan(Sign(x) / Sqrt (x \* x – 1))|  
|Inverzní cosecant – (Acsc(x))|Atan(Sign(x) / Sqrt (x * x – 1))|  
|Inverzní kotangens (Acot(x))|2 * Atan(1) - Atan(x)|  
|Hyperbolický sinus (Sinh(x))|(Exp(x) – Exp(-x)) / 2|  
|Hyperbolický kosinus (Cosh(x))|(Exp(x) + Exp(-x)) / 2|  
|Hyperbolický tangens (Tanh(x))|(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))|  
|Secant – hyperbolický (Sech(x))|2 / (Exp(x) + Exp(-x))|  
|Cosecant – hyperbolický (Csch(x))|2 / (Exp(x) – Exp(-x))|  
|Hyperbolický kotangens (Coth(x))|(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))|  
|Inverzní hyperbolický sinus (Asinh(x))|Protokol (x + Sqrt (x * x + 1))|  
|Inverzní hyperbolický kosinus (Acosh(x))|Protokol (x + Sqrt (x * x – 1))|  
|Inverzní hyperbolický tangens (Atanh(x))|Protokol ((1 + x) / (1 – x)) / 2|  
|Inverzní hyperbolický secant – (AsecH(x))|Protokol ((Sqrt (-x * x + 1) + 1) / x)|  
|Inverzní hyperbolický cosecant – (Acsch(x))|Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)|  
|Inverzní hyperbolický kotangens (Acoth(x))|Protokol ((x + 1) / (x – 1)) / 2|  
  
## <a name="see-also"></a>Viz také  
 [Matematické funkce](../../../visual-basic/language-reference/functions/math-functions.md)
