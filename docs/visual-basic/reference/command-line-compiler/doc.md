---
title: /doc
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1f9d4f584f217e6996a499614b97f184b28664f8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/21/2017
---
# <a name="doc"></a>/doc
Zpracuje dokumentační komentáře do souboru XML.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## <a name="arguments"></a>Arguments  
  
|Termín|Definice|  
|---|---|  
|`+` &#124; `-`|Volitelné. Určení +, nebo jenom `/doc`, způsobí, že kompilátor generovat informace o dokumentaci a umístěte jej do souboru XML. Určení `-` je ekvivalentem není zadávání `/doc`, způsobuje žádné informace dokumentaci, který se má vytvořit.|  
|`file`|Požadováno pokud `/doc:` se používá. Určuje výstupního souboru XML, který se zobrazí v komentářů ze souborů zdrojového kódu kompilace. Pokud název souboru obsahuje mezery, uzavřete název uvozovek nahoře ("").|  
  
## <a name="remarks"></a>Poznámky  
 `/doc` Možnost ovládací prvky, zda kompilátor vygeneruje soubor XML obsahující dokumentační komentáře. Pokud použijete `/doc:``file` syntaxi, která `file` parametr určuje název souboru XML. Pokud používáte `/doc` nebo `/doc+`, kompilátor použije název souboru XML z spustitelný soubor nebo knihovny, který vytváří kompilátoru. Pokud používáte `/doc-` nebo nezadávejte `/doc` možnost kompilátor nevytváří soubor XML.  
  
 V souborech zdrojového kódu lze předcházet dokumentační komentáře následující definice:  
  
-   Uživatelem definované typy, jako například [třída](../../../visual-basic/language-reference/statements/class-statement.md) nebo [rozhraní](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Členové, jako je například pole, [událostí](../../../visual-basic/language-reference/statements/event-statement.md), [vlastnost](../../../visual-basic/language-reference/statements/property-statement.md), [funkce](../../../visual-basic/language-reference/statements/function-statement.md), nebo [podprogramu](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Použít generovaný soubor XML s [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) funkci, ponechte název souboru XML být stejný jako sestavení, které chcete podporovat. Zkontrolujte, zda je soubor XML ve stejném adresáři jako sestavení tak, aby při sestavení odkazuje [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] projektu soubor .xml nalezen také. Soubory dokumentace XML nejsou potřeba pro technologii IntelliSense, která pracují pro kódu v rámci projektu nebo projekty odkazuje na projekt.  
  
 Pokud je kompilovat s `/target:module`, soubor XML obsahuje značek `<assembly></assembly>`. Tyto značky zadejte název souboru, který obsahuje manifest sestavení pro výstupní soubor kompilace.  
  
 V tématu [značky pro komentáře XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) pro způsoby, jak generovat dokumentaci z komentářů v kódu.  
  
|Chcete-li nastavit/doc v sadě Visual Studio integrované vývojové prostředí|  
|---|  
|1.  Máte projekt vybraný v **Průzkumníku řešení**. Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. <br />2.  Klikněte **zkompilovat** kartě.<br />3.  Nastavte hodnotu v **souborů dokumentace XML vygenerovat** pole.|  
  
## <a name="example"></a>Příklad  
 V tématu [dokumentace kódu s XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) pro ukázku.  
  
## <a name="see-also"></a>Viz také  
 [Visual Basic – kompilátor příkazového řádku](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Dokumentace kódu s XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
