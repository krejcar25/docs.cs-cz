---
title: "&lt;Odebrat&gt; Element pro schemeSettings (nastavení Uri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7ab053937587d9cfd9353fe53fa759e58859e3da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-schemesettings-uri-settings"></a>&lt;Odebrat&gt; Element pro schemeSettings (nastavení Uri)
Odebere schéma nastavení pro název schématu.  
  
 \<Konfigurace >  
\<identifikátor URI >  
\<schemeSettings >  
\<Odebrat >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|name|Název schématu, pro kterou platí toto nastavení. Podporované jsou pouze hodnoty name = "http" a name = "https".|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<schemeSettings > – Element (nastavení Uri)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Určuje, jak <xref:System.Uri> bude analyzovat pro konkrétní schémat.|  
  
## <a name="remarks"></a>Poznámky  
 Ve výchozím nastavení <xref:System.Uri?displayProperty=nameWithType> třída zrušení – řídicí sekvence procent kódovaný cesta oddělovače před provedením cesta komprese. Tato možnost byla implementovaná jako vhodný mechanismus zabezpečení před útoky takto:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Pokud tento identifikátor URI předána dolů moduly není zpracování procent kódování znaků správně, to může způsobit vykonáván serveru následující příkaz:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Z tohoto důvodu <xref:System.Uri?displayProperty=nameWithType> třídy první oddělovače zrušení – řídicí sekvence cestu a poté použije cesta komprese. Výsledek předáním škodlivý adresu URL výše na <xref:System.Uri?displayProperty=nameWithType> třídy konstruktor má za následek následující identifikátor URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Toto výchozí chování můžete upravit tak, aby není zrušení řídicí procenta kódovaného cesta oddělovače pomocí možnosti konfigurace schemeSettings pro konkrétní schéma.  
  
## <a name="configuration-files"></a>Konfigurační soubory  
 Tento element lze použít v konfiguračním souboru aplikace nebo v konfiguračním souboru počítače (Machine.config).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje konfigurace používané <xref:System.Uri> třídu, která odebere všechna nastavení schéma pro schéma protokolu http.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [Schéma nastavení sítě](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
