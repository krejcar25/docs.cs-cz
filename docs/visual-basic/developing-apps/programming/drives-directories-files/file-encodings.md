---
title: "Kódování souborů (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- character encodings
- files [Visual Basic], encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: deaab4371ab0d5d15c627bfd6352a7090bf08024
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="file-encodings-visual-basic"></a>Kódování souborů (Visual Basic)
Kódování souborů, také známé jako kódování znaků, určete, jak představují znaky při zpracování textu. Jeden kódování může být vhodnější než oproti jinému z hlediska jazykové symboly může nebo nemůže zpracovat, i když je obvykle upřednostňované kódování Unicode.  
  
 Při čtení nebo zápis do souborů, nesprávně odpovídající kódování souborů může vést k výjimky nebo nesprávné výsledky.  
  
## <a name="types-of-encodings"></a>Typy kódování  
 Unicode je upřednostňované kódování při práci se soubory. Unicode je po celém světě standard kódování znaků, který používá kódu 16bitové hodnoty k reprezentaci všech znaků použitých v moderní computing, včetně technických symbolů a speciální znaky, které jsou používány publikování.  
  
 Předchozí standardy kódování znaků se skládal z tradiční znakových sad, jako je například znakovou sadu Windows ANSI, který používá hodnoty 8bitové kódu nebo kombinace 8bitové hodnoty k reprezentaci znaky použít v určitém jazyce nebo geografické oblasti.  
  
## <a name="encoding-class"></a>Kódování – třída  
 <xref:System.Text.Encoding> Třída představuje kódování znaků. Tato tabulka uvádí typ kódování, které jsou k dispozici a popisuje všechny.  
  
|Název|Popis|
|---|---|    
|<xref:System.Text.ASCIIEncoding>|Představuje kódování znaků ASCII znaky Unicode.|  
|<xref:System.Text.UnicodeEncoding>|Představuje kódování UTF-16 znaků Unicode.|  
|<xref:System.Text.UTF32Encoding>|Představuje kódování znaků Unicode UTF-32.|  
|<xref:System.Text.UTF7Encoding>|Představuje kódování znaků Unicode UTF-7.|  
|<xref:System.Text.UTF8Encoding>|Představuje kódování znaků Unicode UTF-8.|  
  
## <a name="see-also"></a>Viz také  
 [Čtení ze souborů](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [Zápis do souborů](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
