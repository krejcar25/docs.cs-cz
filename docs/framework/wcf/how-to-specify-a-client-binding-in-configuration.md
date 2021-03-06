---
title: "Postupy: Zadání klientské vazby v konfiguraci"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 08cbf0145a2ac3f19e51a065acf97e3cf23b7986
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a>Postupy: Zadání klientské vazby v konfiguraci
V tomto příkladu aplikace konzoly klienta se vytvoří pomocí kalkulačky služby a vazby pro tohoto klienta je deklarativně zadaný v konfiguraci. Klient přistupuje k `CalculatorService`, který implementuje `ICalculator` rozhraní a jak službu a klienta použít <xref:System.ServiceModel.BasicHttpBinding> třídy.  
  
 Podle uvedeného postupu předpokládá, že je spuštěna služba kalkulačky. Informace o tom, jak sestavit službu najdete v tématu [postupy: zadání vazby služby v konfiguraci](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md). Používá také [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] poskytuje k automatickému generování součásti klienta. Nástroj generuje kód klienta a konfigurace přístupu ke službě.  
  
 Klient je součástí dvě části. Generuje svcutil.exe `ClientCalculator` , která implementuje `ICalculator` rozhraní. Tuto aplikaci klienta je pak vytvořený vytvořením instance `ClientCalculator`.  
  
 Obvykle je osvědčeným postupem zadejte vazby a informace o adrese deklarativně v konfiguraci, nikoli imperativní v kódu. Definování koncové body v kódu obvykle není praktické protože jsou obvykle liší od těch, které používá při služby je vyvíjen vazeb a adresy pro v nasazené službě. Obecně platí udržování vazby a adresování informace mimo kód jim umožňuje změnit bez nutnosti znovu zkompiluje nebo znovu nasadit aplikaci.  
  
 Všechny tyto kroky konfigurace můžete provádět pomocí [nástroj Configuration Editor (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Zdroj kopírování tohoto příkladu, najdete v článku [základní vazby](../../../docs/framework/wcf/samples/basicbinding.md) ukázka.  
  
### <a name="specifying-a-client-binding-in-configuration"></a>Určení vazby v konfiguraci klienta  
  
1.  Generování kódu z metadat služby pomocí Svcutil.exe z příkazového řádku.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  Obsahuje klienta, který se generuje `ICalculator` rozhraní, které definuje kontrakt služby, které musí splňovat implementace klienta.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3.  Generovaného klienta obsahuje také provádění `ClientCalculator`.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4.  Svcutil.exe také generuje konfiguraci pro klienta, který používá <xref:System.ServiceModel.BasicHttpBinding> třídy. Při použití [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], název tohoto souboru App.config. Všimněte si, že adresu a informace o vazbě nejsou zadat kdekoli v rámci implementace služby. Kód také nemá k zapsání k načtení těchto informací z konfiguračního souboru.  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]   
            
5.  Vytvoření instance `ClientCalculator` v aplikaci a pak volání operací služby.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6.  Zkompilování a spuštění klienta.  
  
## <a name="see-also"></a>Viz také  
 [Používání vazeb ke konfiguraci služeb a klientů](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
