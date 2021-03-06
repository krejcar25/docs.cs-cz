---
title: "&lt;NetFx40_LegacySecurityPolicy –&gt; – Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 636b7020a8728978ea13529382a822d99cd36f74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetfx40legacysecuritypolicygt-element"></a>&lt;NetFx40_LegacySecurityPolicy –&gt; – Element
Určuje, zda modul runtime používá zásady zabezpečení (CA) přístupu starší verze kódu.  
  
 \<Konfigurace >  
\<modul runtime >  
< NetFx40_LegacySecurityPolicy – >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`enabled`|Požadovaný atribut.<br /><br /> Určuje, zda modul runtime používá starší zásadu CAS.|  
  
## <a name="enabled-attribute"></a>Atribut enabled  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`false`|Modul runtime nepoužívá starší zásadu CAS. Toto nastavení je výchozí.|  
|`true`|Modul runtime používá starší zásadu CAS.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|`configuration`|Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.|  
|`runtime`|Obsahuje informace o možnostech inicializace modulu runtime.|  
  
## <a name="remarks"></a>Poznámky  
 V rozhraní .NET Framework verze 3.5 a starší verze je zásadu CAS vždy v platnost. V [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], musí být povolené zásady CAS.  
  
 Zásady CAS jsou specifické pro verzi. Vlastní zásady certifikačních Autorit, které existují v dřívějších verzích rozhraní .NET Framework musí být zadány znovu v [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Použití `<NetFx40_LegacySecurityPolicy>` elementu, který chcete [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] sestavení nemá vliv na [kód transparentní pro zabezpečení](../../../../../docs/framework/misc/security-transparent-code.md); pravidla transparentnosti platit stále.  
  
> [!IMPORTANT]
>  Použití `<NetFx40_LegacySecurityPolicy>` element může vést k postihy významně zvýšit výkon u nativních bitových kopií sestavení vytvořené [generátor (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) které nejsou nainstalovány v [globální mezipaměť sestavení ](../../../../../docs/framework/app-domains/gac.md). Snížení výkonu je způsobena nemožnost modulu runtime k načtení sestavení jako nativní bitové kopie, když se použije atribut, což vede k jejich se načíst sestavení jako v běhu.  
  
> [!NOTE]
>  Pokud zadáte cílové verze rozhraní .NET Framework, která je starší než [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] v nastavení projektu pro projektu sady Visual Studio, bude možné povolit certifikační Autority zásad, včetně všechny vlastní zásady certifikační Autority, který jste zadali pro tuto verzi. Ale nebudete moci používat nový [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] typy a členy. Můžete také zadat dřívější verzi rozhraní .NET Framework pomocí [ \<supportedRuntime > element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) ve schématu nastavení spuštění ve vaší [konfiguračního souboru aplikace](../../../../../docs/framework/configure-apps/index.md).  
  
> [!NOTE]
>  Syntaxe souboru konfigurace je malá a velká písmena. Jak je uvedené v oddílech syntaxe a příklad, měli byste použít syntaxi.  
  
## <a name="configuration-file"></a>Konfigurační soubor  
 Tento element může použít pouze v konfiguračním souboru aplikace.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak povolte starší zásadu CAS pro aplikaci.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také  
 [Schéma nastavení běhového prostředí](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schéma konfiguračního souboru](../../../../../docs/framework/configure-apps/file-schema/index.md)
