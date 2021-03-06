---
title: "Postupy: Konfigurace chování při nečinnosti pomocí WorkflowServiceHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1a0d0d4a8b99a6c0536bba8371234f8d46bc1dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a>Postupy: Konfigurace chování při nečinnosti pomocí WorkflowServiceHost
Když narazí záložka, která musí být obnoven, pomocí některé externí podnětem, například při k instanci pracovního postupu se čeká na zprávu, která se dodávají pomocí přejděte nečinnosti pracovních postupů <xref:System.ServiceModel.Activities.Receive> aktivity. <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>je chování, které vám umožní určit čas mezi při přechodu nečinnosti instance služby, a pokud je instance jako trvalý, nebo odpojeno. Obsahuje dvě vlastnosti, které umožňují nastavit tyto časové úseky. <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A>Určuje časový interval mezi při přechodu nečinnosti instance služby pracovního postupu a když je trvalé instance služby pracovního postupu. <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A>Určuje časový interval mezi když pracovní postup služby instance přejde nečinnosti a když instance služby pracovního postupu je odpojen, kde uvolnění znamená uložením instance na ukládání instance a odebere ji z paměti. Toto téma vysvětluje, jak nakonfigurovat <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> v konfiguračním souboru.  
  
### <a name="to-configure-workflowidlebehavior"></a>Ke konfiguraci WorkflowIdleBehavior  
  
1.  Přidat <`workflowIdle`> elementu, který chcete <`behavior`> v rámci <`serviceBehaviors`> elementu, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     `timeToUnload` Atribut určuje časové období mezi při přechodu nečinnosti instance pracovního postupu služby a služby pracovního postupu je odpojen. `timeToPersist` Atribut určuje časové období mezi při přechodu nečinnosti instance služby pracovního postupu a když je trvalé instance služby pracovního postupu. Výchozí hodnota pro `timeToUnload` je 1 minuta. Výchozí hodnota pro `timeToPersist` je <xref:System.TimeSpan.MaxValue>. Pokud chcete do nečinnosti instancí mějte na paměti, ale je uchoval pro odolnost, nastavte hodnoty tak, aby `timeToPersist`  <  `timeToUnload`. Pokud chcete zabránit odpojení nečinnosti instancí, nastavte `timeToUnload` k <xref:System.TimeSpan.MaxValue>. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, najdete v části [rozšíření hostitele služby pracovního postupu](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
  
    > [!NOTE]
    >  V předchozím příkladu konfigurace používá zjednodušená konfigurace. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Zjednodušená konfigurace](../../../../docs/framework/wcf/simplified-configuration.md).  
  
### <a name="to-change-idle-behavior-in-code"></a>Chcete-li změnit chování při nečinnosti v kódu  
  
-   Následující příklad změní dobu čekání před uložením a uvolňování prostřednictvím kódu programu.  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřitelnost hostitele služby pracovního postupu](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [Zjednodušená konfigurace](../../../../docs/framework/wcf/simplified-configuration.md)  
 [Služby pracovních postupů](../../../../docs/framework/wcf/feature-details/workflow-services.md)
