---
title: /resource (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 858a216873ad9999722388e45d5de28398b27fbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="resource-visual-basic"></a>/resource (Visual Basic)
Vloží spravovaných prostředků v sestavení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Arguments  
  
|Termín|Definice|  
|---|---|  
|`filename`|Požadováno. Název souboru prostředků pro vložení do výstupního souboru. Ve výchozím nastavení `filename` je veřejný v sestavení. Uzavřete název souboru v uvozovkách ("") Pokud obsahuje mezeru.|  
|`identifier`|Volitelné. Logický název prostředku; název, který ho načíst. Výchozí hodnota je název souboru. Volitelně můžete zadat, zda je prostředek veřejné nebo soukromé v manifestu sestavení, stejně jako u následující: `/res:``filename.res`,`myname.res`,`public`|  
  
## <a name="remarks"></a>Poznámky  
 Použití `/linkresource` propojení prostředek k sestavení bez umístění souboru prostředků ve výstupním souboru.  
  
 Pokud `filename` je [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] souboru prostředků vytvořili, například pomocí [Resgen.exe (Generátor zdrojových souborů)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) nebo ve vývojovém prostředí k němu se členy v <xref:System.Resources> obor názvů (viz <xref:System.Resources.ResourceManager> informace). Pro přístup k jiným prostředkům v době běhu, použijte jednu z následujících metod: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, nebo <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 Zkratka pro `/resource` je `/res`.  
  
 Informace o tom, jak nastavit `/resource` v prostředí Visual Studio IDE, naleznete v části [Správa prostředků aplikace (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Příklad  
 Následující kód zkompiluje `In.vb` a připojí zdrojového souboru `Rf.resource`.  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Basic – kompilátor příkazového řádku](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [/ linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Příkazové řádky ukázkové kompilace](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
