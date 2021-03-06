---
title: '&lt;bindingExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58392fc71508c3cf6ad7178396a927cf0e84c98f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltbindingextensionsgt"></a>&lt;bindingExtensions&gt;
Tato část umožňuje použití definované uživatelem vazby z počítače nebo konfiguračního souboru aplikace. Můžete přidat definované uživatelem vazby k této kolekci pomocí `add` – klíčové slovo a nastavení `type` atribut elementu uživatelem definované vazby, společně s `name` vazby definován atribut na jméno uživatele.  
  
 Vazba rozšíření umožňují uživatelům vytvořit uživatelem definované vazby pro použití v rámci konfigurace koncového bodu. Prostřednictvím kódu programu, rozšíření vazby je typ, který implementuje abstraktní třídu <xref:System.ServiceModel.Channels.Binding>.  
  
 Následující příklad používá `add` elementu, společně s `name` přidat příponu vazby do atribut `bindingElementExtensions` oddílu konfiguračního souboru.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingExtensions>  
           <add name="MyBinding" type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 Přidat konfiguraci dalo k elementu, uživatel musí k zápisu a zaregistrovat `bindingSection` elementu. Další informace najdete v tématu <xref:System.Configuration> dokumentaci.  
  
 Po elementu a jeho typ konfigurace jsou definovány, rozšíření lze použít jako součást koncový bod, jak je znázorněno v následujícím příkladu.  
  
```xml  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
```  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření vazeb](../../../../../docs/framework/wcf/extending/extending-bindings.md)
