---
title: "Postupy: Změna hodnoty nastavení mezi relacemi aplikace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c00e61001d9c8877b1fcaa0e938c92249c7915e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Postupy: Změna hodnoty nastavení mezi relacemi aplikace
V některých případech můžete chtít změnit hodnoty nastavení mezi relacemi aplikace po aplikaci byl zkompilován a nasazení. Můžete například změnit připojovací řetězec tak, aby odkazovaly na správné databázi umístění. Vzhledem k tomu, že nástrojů návrhu nejsou k dispozici po aplikaci byl zkompilován a nasazení, je nutné změnit hodnotu nastavení ručně v souboru.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Chcete-li změnit hodnoty nastavení mezi relacemi aplikace  
  
1.  Pomocí Microsoft Notepad nebo některé další text nebo editoru XML, otevřete soubor .config související s vaší aplikací.  
  
2.  Vyhledejte položku s nastavením, které chcete změnit. By měla vypadat podobně jako v příkladu níže uvedené.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Zadejte novou hodnotu pro vaše nastavení a uložte soubor.  
  
## <a name="see-also"></a>Viz také  
 [Použití nastavení aplikace a uživatelských nastavení](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Přehled nastavení aplikace](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
