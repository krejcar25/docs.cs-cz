---
title: "219 – ServiceException"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fceff5c748076c75c942f515e2621edff5106f4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="219---serviceexception"></a>219 – ServiceException
## <a name="properties"></a>Vlastnosti  
  
|||  
|-|-|  
|ID|219|  
|Klíčová slova|EndToEndMonitoring, HealthMonitoring, řešení potíží s ServiceModel|  
|úroveň|Chyba|  
|Kanál|Aplikaci Microsoft Windows Server – aplikace nebo analytické|  
  
## <a name="description"></a>Popis  
 Tato událost je vygenerované, když dojde k neošetřené výjimce služby WCF. To zahrnuje neošetřené výjimky během aktivace, při zpracování zprávy a v uživatelském kódu.  
  
## <a name="message"></a>Zpráva  
 Při zpracování zprávy došlo k neošetřené výjimce typu '%2'. ToString – Úplná výjimka: %1.  
  
## <a name="details"></a>Podrobnosti  
  
|Název položky dat|Datová položka – Typ|Popis|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|Výsledek volání `ToString`() na výjimky CLR.|  
|ExceptionTypeName|`xs:string`|Položka FullName CLR v výjimky typu.|  
|HostReference|`xs:string`|Pro hostované webové služby v tomto poli jednoznačně identifikuje v hierarchii webové služby. Formát je definovaný jako "virtuální cesta aplikace název webu &#124; Virtuální cesta služby &#124; ServiceName}. Příklad: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|Domény aplikace|`xs:string`|Řetězec vrácený AppDomain.CurrentDomain.FriendlyName.|
