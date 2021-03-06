---
title: "Postupy: Zápis uživatelských nastavení při běhu pomocí C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 274a104d194c9db13d69d2024dc54595690c2ce3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Postupy: Zápis uživatelských nastavení při běhu pomocí C# #
Nastavení, které jsou s rozsahem aplikace jsou jen pro čtení a lze změnit pouze v době návrhu nebo změnou souboru .config mezi relacemi aplikace. Nastavení, které jsou zaměřené na uživatele, ale může být napsán v době běhu stejně, jako by měnit všechny hodnoty vlastnosti. Nová hodnota trvá po dobu trvání relace aplikace. Můžete zachovat změny nastavení mezi relacemi aplikace pomocí volání metody uložit.  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Postupy: Zápis a zachovaly uživatelská nastavení v době běhu pomocí C#  
  
1.  Přístup k nastavení a přiřaďte ho novou hodnotu, jak je uvedeno v následujícím příkladu:  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  Pokud chcete zachovat změny nastavení mezi relacemi aplikace, zavolejte metodu uložit, jak je uvedeno v následujícím příkladu:  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     Uživatelská nastavení se ukládají do souboru v rámci podsložkou složky data místní skrytá aplikace uživatele.  
  
## <a name="see-also"></a>Viz také  
 [Použití nastavení aplikace a uživatelských nastavení](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Postupy: Čtení uživatelských nastavení při běhu pomocí C#](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [Přehled nastavení aplikace](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
