---
title: "Struktura & č. 39; &lt;%{structurename/&gt;& č. 39; musí obsahovat alespoň jednu instanci členské proměnné nebo deklaraci události alespoň jedna instance nesmí být označený & č. 39; Vlastní & č. 39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords: BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b28dd59271bdaca52072710ea797fae6e9168eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Struktura & č. 39; &lt;%{structurename/&gt;& č. 39; musí obsahovat alespoň jednu instanci členské proměnné nebo deklaraci události alespoň jedna instance nesmí být označený & č. 39; Vlastní & č. 39;
Definice struktury nezahrnuje všechny sdíleném proměnné nebo sdíleném nevlastní události.  
  
 Proměnné nebo událost, která platí pro každou konkrétní instanci místo (sdíleném) na všechny instance souhrnně musí mít každý struktura ([sdílené](../../../visual-basic/language-reference/modifiers/shared.md)). Sdíleném konstanty, vlastnosti a postupů nevyhovují tento požadavek. Kromě toho, pokud nejsou žádné sdíleném proměnné a jenom jedna sdíleném událost, že událost nemůže být `Custom` událostí.  
  
 **ID chyby:** BC30941  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zadejte alespoň jednu proměnnou nebo událost, která není `Shared`. Pokud definujete jen jednu událost, musí být nevlastní, jakož i sdíleném.  
  
## <a name="see-also"></a>Viz také  
 [Struktury](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Postupy: definice struktury](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Structure – příkaz](../../../visual-basic/language-reference/statements/structure-statement.md)
