---
title: "Navrhování a implementace vlastních aktivit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d162635a82027d1aaa46545dabad3e103d0f339c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="designing-and-implementing-custom-activities"></a>Navrhování a implementace vlastních aktivit
Vlastní aktivity v [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] vytvářejí buď odlišnými poskytované systémem aktivit do složených aktivity nebo vytvoření nových typů, které jsou odvozeny od <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, nebo <xref:System.Activities.NativeActivity>. Tato část popisuje, jak vytvořit vlastní aktivity pomocí některé z metod.  
  
> [!IMPORTANT]
>  Vlastní aktivity ve výchozím nastavení zobrazí jako jednoduchý obdélníku s názvem aktivity v Návrháři pracovních postupů. Poskytnout vlastní vizuální reprezentace aktivity v pracovním postupu návrháře je nutné také vytvořit vlastní návrháře. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Pomocí Návrháře vlastních aktivit a šablony](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Možnosti při vytváření aktivit](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 Popisuje vytváření stylů, které jsou k dispozici v [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].  
  
 [Použití vlastní aktivity](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 Popisuje, jak přidat vlastní aktivity pracovního postupu projektu.  
  
  [Vytváření asynchronních aktivit](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 Popisuje, jak vytvořit asynchronní aktivity.  
  
 [Konfigurace ověřování aktivit](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 Popisuje, jak aktivita ověřování lze použít k identifikaci a nahlášení chyb v konfiguraci aktivity před jeho spuštění.  
  
 [Vytvoření aktivity za běhu](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 Popisuje, jak vytvořit aktivit v modulu runtime pomocí <xref:System.Activities.DynamicActivity>.  
  
 [Vlastnosti spuštění pracovního postupu](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 Popisuje, jak pomocí vlastnosti spuštění pracovního postupu můžete přidat do prostředí aktivity konkrétních vlastností kontextu  
  
 [Používání delegátů aktivit](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 Popisuje postup vytváření a používání aktivit, které obsahují aktivitu delegáti.  
  
 [Lokalizace aktivity](../../../docs/framework/windows-workflow-foundation/activity-localization.md)  
 Popisuje způsob použití lokalizace řetězcové prostředky v aktivitách.  
  
 [Používání rozšíření aktivit](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 Popisuje postup vytváření a používání rozšíření aktivity.  
  
 [Využití informačních kanálů OData z pracovního postupu](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 Popisuje několik metod pro volání služby WCF Data Service z pracovního postupu.  
  
 [Určení oboru a viditelnosti definice aktivity](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 Popisuje možnosti a pravidla pro definování dat rozsahu a člen viditelnost pro aktivity.
