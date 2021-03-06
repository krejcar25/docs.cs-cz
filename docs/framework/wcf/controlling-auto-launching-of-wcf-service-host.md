---
title: "Ovládání automatického spouštění hostitele služeb WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65daceac9b865f3e8224c709d672344606905d9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Ovládání automatického spouštění hostitele služeb WCF
Můžete řídit funkci automatického spouštění systému [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] hostitel služby (WcfSvcHost.exe) pro [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] projektu knihovny služby, při ladění projektu pro jiné ve stejné [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] řešení obsahující více projektů.  
  
 To pokud chcete udělat, klikněte pravým tlačítkem myši [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] projektu služby v **Průzkumníku řešení**, zvolte **vlastnosti**a klikněte na tlačítko **WCF možnosti** kartě. **Spustit hostitel služby WCF při ladění jiného projektu ve stejném řešení** zaškrtávací políčko je dostupné ve výchozím nastavení. Můžete vymazat pole tak, aby [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hostitele služby pro tento konkrétní projekt není spustí, když je ve stejném řešení ladit jiného projektu.  
  
 Toto chování neovlivňuje ladění F5 nebo funkce Přidat odkaz na službu pro tento projekt.  
  
 Tato možnost je dostupná na následujících projektech:  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]Projekt knihovny služby.  
  
-   Projekt knihovny služby sekvenční pracovní postup.  
  
-   Projekt knihovny služby stavu počítače pracovního postupu.  
  
-   Syndikace projektu knihovny služby.  
  
## <a name="see-also"></a>Viz také  
 [Hostitel služby WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
